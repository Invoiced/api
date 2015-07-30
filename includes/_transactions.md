# Transactions

Transactions can represent a `charge`, `payment`, `refund`, or `adjustment`.

We record `charge` and `refund` transactions for you that happen through Invoiced. The `payment` transaction type is designated for recording offline payments like checks. Finally, an `adjustment` transaction represents any additional credit or debits to a customer's balance.

Most transactions will be associated with an invoice, however, not all. For example, if you wanted to credit your customer for $20 you would create an `adjustment` transaction for -$20 using the customer ID only instead of the invoice ID.

We currently support the following payment methods on transactions:

- `credit_card`
- `ach`
- `bitcoin`
- `paypal`
- `wire_transfer`
- `check`
- `cash`
- `other`

## Transaction Object

### Attributes

```shell
{
	"id": 20939,
	"customer": 15460,
	"invoice": 44648,
	"theme": null,
	"date": 1410843600,
	"type": "payment",
	"method": "check",
	"status": "succeeded",
	"gateway": null,
	"gateway_id": null,
	"currency": "usd",
	"amount": 800,
	"fee": 0,
	"notes": null,
	"sent": false,
	"failure_reason": null,
	"parent_transaction": null,
	"pdf_url": "https://dundermifflin.invoiced.com/payments/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
	"created_at": 1415228628
}
```

```ruby
#<Invoiced::Transaction:0x3fdbf95e4d08 id=20939> JSON: {
	"id": 20939,
	"customer": 15460,
	"invoice": 44648,
	"theme": null,
	"date": 1410843600,
	"type": "payment",
	"method": "check",
	"status": "succeeded",
	"gateway": null,
	"gateway_id": null,
	"currency": "usd",
	"amount": 800,
	"fee": 0,
	"notes": null,
	"sent": false,
	"failure_reason": null,
	"parent_transaction": null,
	"pdf_url": "https://dundermifflin.invoiced.com/payments/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
	"created_at": 1415228628
}
```

Parameter | Type | Description
--------- | ---- | -----------
**id** | *integer* | The transaction's unique ID
**customer** | *integer* | Associated Customer
**invoice** | *integer* | Associated Invoice, if any
**theme** | *integer* | Theme ID for rendering with custom themes
**date** | *timestamp* | Transaction date
**type** | *string* | Transaction type, `charge`, `payment`, `refund`, or `adjustment`
**method** | *string* | Payment instrument used to facilitate transaction
**status** | *string* | Transaction status, one of `succeeded`, `pending`, or `failed`
**gateway** | *string* | Payment gateway that processed the transaction, if any
**gateway_id** | *string* | Transaction ID from the payment gateway
**currency** | *string* | 3-digit ISO 4217 currency code
**amount** | *number* | Transaction amount
**fee** | *number* | Processing fees
**notes** | *string* | Internal notes
**sent** | *boolean* | Indicates if the transaction receipt has been sent'
**parent_transaction** | *integer* | ID of the original transaction for refunds
**pdf_url** | *string* | URL to download the invoice as a PDF
**created_at** | *timestamp* | Timestamp when created

## Create a transaction

```shell
curl "https://api.invoiced.com/transaction" \
  -u {API_KEY}: \
  -d invoice=44648 \
  -d method="check" \
  -d gateway_id="1450" \
  -d amount=800
```

```ruby
invoiced.Transaction.create(
  :invoice => 44648,
  :method => "check",
  :gateway_id => "1450",
  :amount => 800
)
```

> The above command returns JSON structured like this:

```shell
{
	"id": 20939,
	"customer": 15460,
	"invoice": 44648,
	"theme": null,
	"date": 1410843600,
	"type": "payment",
	"method": "check",
	"status": "succeeded",
	"gateway": null,
	"gateway_id": "1450",
	"currency": "usd",
	"amount": 800,
	"fee": 0,
	"notes": null,
	"sent": false,
	"failure_reason": null,
	"parent_transaction": null,
	"pdf_url": "https://dundermifflin.invoiced.com/payments/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
	"created_at": 1415228628
}
```

```ruby
#<Invoiced::Transaction:0x3fdbf95e4d08 id=30939> JSON: {
	"id": 20939,
	"customer": 15460,
	"invoice": 44648,
	"theme": null,
	"date": 1410843600,
	"type": "payment",
	"method": "check",
	"status": "succeeded",
	"gateway": null,
	"gateway_id": null,
	"currency": "usd",
	"amount": 800,
	"fee": 0,
	"notes": null,
	"sent": false,
	"failure_reason": null,
	"parent_transaction": null,
	"pdf_url": "https://dundermifflin.invoiced.com/payments/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
	"created_at": 1415228628
}
```

Create a new transaction with this endpoint.

### Attributes

Parameter | Type | Description
--------- | ---- | -----------
**customer** | *integer* | Customer ID, required if invoice ID is not supplied
**invoice** | *integer* | Invoice ID, if any
**type** | *string* | Transaction type, `charge`, `payment`, `refund`, or `adjustment` - **required**
**date** | *timestamp* | Transaction date, defaults to current timestamp
**theme** | *integer* | Theme ID for rendering with custom themes
**method** | *string* | Payment instrument used to facilitate transaction, defaults to `other`
**status** | *string* | Transaction status, one of `succeeded`, `pending`, or `failed`, defaults to `succeeded`
**gateway** | *string* | Payment gateway that processed the transaction, if any
**gateway_id** | *string* | Transaction ID from the payment gateway, or check # if method is `check`
**currency** | *string* | 3-digit ISO 4217 currency code
**amount** | *number* | Transaction amount
**fee** | *number* | Processing fees
**notes** | *string* | Internal notes

## Retrieve a transaction

```shell
curl "https://api.invoiced.com/transactions/:id" \
  -u {API_KEY}:
```

```ruby
transaction = invoiced.Transaction.retrieve("{TRANSACTION_ID}")
```

> The above command returns JSON structured like this:

```shell
{
	"id": 20939,
	"customer": 15460,
	"invoice": 44648,
	"theme": null,
	"date": 1410843600,
	"type": "payment",
	"method": "check",
	"status": "succeeded",
	"gateway": null,
	"gateway_id": null,
	"currency": "usd",
	"amount": 800,
	"fee": 0,
	"notes": null,
	"sent": false,
	"failure_reason": null,
	"parent_transaction": null,
	"pdf_url": "https://dundermifflin.invoiced.com/payments/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
	"created_at": 1415228628
}
```

```ruby
#<Invoiced::Transaction:0x3fdbf95e4d08 id=20939> JSON: {
	"id": 20939,
	"customer": 15460,
	"invoice": 44648,
	"theme": null,
	"date": 1410843600,
	"type": "payment",
	"method": "check",
	"status": "succeeded",
	"gateway": null,
	"gateway_id": null,
	"currency": "usd",
	"amount": 800,
	"fee": 0,
	"notes": null,
	"sent": false,
	"failure_reason": null,
	"parent_transaction": null,
	"pdf_url": "https://dundermifflin.invoiced.com/payments/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
	"created_at": 1415228628
}
```

This endpoint retrieves a specific transaction.

### HTTP Request

`GET /transactions/:id`

## Update a transaction

```shell
curl "https://api.invoiced.com/transactions/:id" \
  -u {API_KEY}: \
  -d notes="Check was received by Jan" \
  -X PATCH
```

```ruby
transaction.notes = "Check was received by Jan"
transaction.save
```

> The above command returns JSON structured like this:

```shell
{
	"id": 20939,
	"customer": 15460,
	"invoice": 44648,
	"theme": null,
	"date": 1410843600,
	"type": "payment",
	"method": "check",
	"status": "succeeded",
	"gateway": null,
	"gateway_id": null,
	"currency": "usd",
	"amount": 800,
	"fee": 0,
	"notes": "Check was received by Jan",
	"sent": false,
	"failure_reason": null,
	"parent_transaction": null,
	"pdf_url": "https://dundermifflin.invoiced.com/payments/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
	"created_at": 1415228628
}
```

```ruby
#<Invoiced::Transaction:0x3fdbf95e4d08 id=20939> JSON: {
	"id": 20939,
	"customer": 15460,
	"invoice": 44648,
	"theme": null,
	"date": 1410843600,
	"type": "payment",
	"method": "check",
	"status": "succeeded",
	"gateway": null,
	"gateway_id": null,
	"currency": "usd",
	"amount": 800,
	"fee": 0,
	"notes": "Check was received by Jan",
	"sent": false,
	"failure_reason": null,
	"parent_transaction": null,
	"pdf_url": "https://dundermifflin.invoiced.com/payments/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
	"created_at": 1415228628
}
```

Use this endpoint to update a transaction.

### HTTP Request

`PATCH /transactions/:id`

### Request Parameters

Parameter | Type | Description
--------- | ---- | -----------
**date** | *timestamp* | Transaction date, defaults to current timestamp
**theme** | *integer* | Theme ID for rendering with custom themes
**method** | *string* | Payment instrument used to facilitate transaction, defaults to `other`
**status** | *string* | Transaction status, one of `succeeded`, `pending`, or `failed`, defaults to `succeeded`
**gateway** | *string* | Payment gateway that processed the transaction, if any
**gateway_id** | *string* | Transaction ID from the payment gateway, or check # if method is `check`
**currency** | *string* | 3-digit ISO 4217 currency code
**amount** | *number* | Transaction amount
**fee** | *number* | Processing fees
**notes** | *string* | Internal notes

## Send a receipt

```shell
curl "https://api.invoiced.com/transactions/:id/emails" \
  -u {API_KEY}: \
  -X POST
```

```ruby
emails, metadata = transaction.send
```

> The above command returns JSON structured like this:

```shell
[
  {
    "id": "f45382c6fbc44d44aa7f9a55eb2ce731",
    "state": "sent",
    "reject_reason": null,
    "email": "client@example.com",
    "template": "payment_receipt_email",
    "subject": "Receipt for your recent payment to Dunder Mifflin, Inc.",
    "message": "Dear Client, we have attached a receipt for your most recent payment. Thank you!",
    "opens": 0,
    "opens_detail": [],
    "clicks": 0,
    "clicks_detail": [],
    "created_at": 1436890047
  },
  { ... },
  { ... }
]
```

```ruby
[
  #<Invoiced::Email:0x3fdbf95e4d08 id="f45382c6fbc44d44aa7f9a55eb2ce731"> JSON: {
    "id": "f45382c6fbc44d44aa7f9a55eb2ce731",
    "state": "sent",
    "reject_reason": null,
    "email": "client@example.com",
    "template": "payment_receipt_email",
    "subject": "Receipt for your recent payment to Dunder Mifflin, Inc.",
    "message": "Dear Client, we have attached a receipt for your most recent payment. Thank you!",
    "opens": 0,
    "opens_detail": [],
    "clicks": 0,
    "clicks_detail": [],
    "created_at": 1436890047
  },
  #<Invoiced::Email:0x3fdasdf95e09 id="a0s36fbc44d44aa7f9a55easdfi8ce731"> JSON: { ... },
  #<Invoiced::Email:0x3fdbffge4d10 id="s90f2c6fbc44sdfj8aa7f9a55eb2ce731"> JSON: { ... }
]
```

This endpoint sends a PDF receipt to the customer.

### HTTP Request

`POST /transactions/:id/emails`

### Request Parameters

Parameter | Type | Description
--------- | ---- | -----------
**to** | *array* | Optional array of recipients like:<br/>`[{"name": "Client", "email": "client@example.com"}]`
**bcc** | *string* | Optional comma-separated list of email addresses to be blind carbon copied
**subject** | *string* | Optional subject
**message** | *string* | Optional message body, otherwise the *Payment Receipt Email* template is used

<aside class="info">
A successful response means that your email has been added to the send queue.
</aside>

## Refund a transaction

```shell
curl "https://api.invoiced.com/transactions/:id/emails" \
  -u {API_KEY}: \
  -X POST
```

```ruby
emails, metadata = transaction.refund(400)
```

> The above command returns JSON structured like this:

```shell
{
"id": 20952,
"customer": 15460,
"invoice": 44648,
"theme": null,
"date": 1410843600,
"type": "refund",
"method": "check",
"status": "succeeded",
"gateway": null,
"gateway_id": null,
"currency": "usd",
"amount": 400,
"fee": 0,
"notes": null,
"sent": false,
"failure_reason": null,
"parent_transaction": 20939,
"pdf_url": "https://dundermifflin.invoiced.com/payments/IZmXbVOPyvfD3GPBmyd6FwXY/20939pdf",
"created_at": 1415228628
}
```

```ruby
#<Invoiced::Transaction:0x3fdbf95e4d08 id=20952> JSON: {
"id": 20952,
"customer": 15460,
"invoice": 44648,
"theme": null,
"date": 1410843600,
"type": "refund",
"method": "check",
"status": "succeeded",
"gateway": null,
"gateway_id": null,
"currency": "usd",
"amount": 400,
"fee": 0,
"notes": null,
"sent": false,
"failure_reason": null,
"parent_transaction": 20939,
"pdf_url": "https://dundermifflin.invoiced.com/payments/IZmXbVOPyvfD3GPBmyd6FwXY/20939pdf",
"created_at": 1415228628
}
```

You can issue a refund for `charge` and `payment` transactions. When a refund is issued for a `charge` transaction we will attempt to initiate the refund over the payment gateway it happened on.

Of course, when refunding `payment` transactions you would have to return the money to your customer. This endpoint simply provides a means to track any refunds that you issue for offline payments.

Partial refunds are allowed, however, the total amount refunded cannot exceed the original transaction amount.

### HTTP Request

`POST /transactions/:id/refunds`

### Request Parameters

Parameter | Type | Description
--------- | ---- | -----------
**amount** | *number* | Amount to refund - **required**

<aside class="notice">
We will initiate the refund through the payment gateway for <code>charge</code> transactions that have a valid payment gateway attached.
</aside>

## Delete a transaction

```shell
curl "https://api.invoiced.com/transactions/:id" \
  -u {API_KEY}: \
  -X DELETE
```

```ruby
transaction.delete
```

> The above command returns `204 No Content`

This endpoint deletes a specific transaction.

### HTTP Request

`DELETE /transactions/:id`

## List all transactions

```shell
curl "https://api.invoiced.com/transactions" \
  -u {API_KEY}:
```

```ruby
transactions, metadata = invoiced.Transaction.list(:per_page => 3)
```

> The above command returns JSON structured like this:

```shell
[
  {
	"id": 20939,
	"customer": 15460,
	"invoice": 44648,
	"theme": null,
	"date": 1410843600,
	"type": "payment",
	"method": "check",
	"status": "succeeded",
	"gateway": null,
	"gateway_id": null,
	"currency": "usd",
	"amount": 800,
	"fee": 0,
	"notes": null,
	"sent": false,
	"failure_reason": null,
	"parent_transaction": null,
	"pdf_url": "https://dundermifflin.invoiced.com/payments/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
	"created_at": 1415228628
  },
  { ... },
  { ... }
]
```

```ruby
[
  #<Invoiced::Transaction:0x3fdbf95e4d08 id=20939> JSON: {
	"id": 20939,
	"customer": 15460,
	"invoice": 44648,
	"theme": null,
	"date": 1410843600,
	"type": "payment",
	"method": "check",
	"status": "succeeded",
	"gateway": null,
	"gateway_id": null,
	"currency": "usd",
	"amount": 800,
	"fee": 0,
	"notes": null,
	"sent": false,
	"failure_reason": null,
	"parent_transaction": null,
	"pdf_url": "https://dundermifflin.invoiced.com/payments/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
	"created_at": 1415228628
  },
  #<Invoiced::Transaction:0x3fdbf95e4d09 id=20940> JSON: { ... },
  #<Invoiced::Transaction:0x3fdbf95e4d10 id=20941> JSON: { ... }
]
```

This endpoint retrieves all transactions.

### HTTP Request

`GET /transactions`

### Query Parameters

Parameter | Description
--------- | -----------
**sort** *string* | Column to sort by, i.e. `name asc`
**filter** *object* | Filter object