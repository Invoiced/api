# Payments

On Invoiced we use the Transaction concept to represent any monetary value that is transferred between a merchant and customer. In our world, if an invoice describes a balance owed by a customer then a transaction represents the payment of that balance. Transactions can also describe other types of value transfer beyond payments, like refunds and credits.

A transaction can be one of these types:

- `charge`: an electronic charge or payment
- `payment`: offline payment received from the customer, i.e. a check
- `refund`: money refunded to the customer
- `adjustment`: a debit or credit to the customer's credit balance

We automatically record `charge` and `refund` transactions that happen through Invoiced for you. Transactions can be associated with a document, like an invoice or credit note, however not all transactions will reference a document.

We currently support the following payment methods on transactions:

- `credit_card`
- `ach`
- `paypal`
- `wire_transfer`
- `check`
- `cash`
- `other`

`adjustment` transactions will always use the `balance` payment method. Since our system is designed from the perspective of the merchant, a negative adjustment represents a credit to the customer and a positive adjustment represents a charge to the customer. For example, if you wanted to credit your customer for $20 then you would create an `adjustment` transaction for -$20. Furthermore, adjustments can have a credit note associated.

## Transaction Object

### Attributes

```shell
{
	"id": 20939,
	"object": "transaction",
	"customer": 15460,
	"invoice": 44648,
	"credit_note": null,
	"date": 1410843600,
	"type": "payment",
	"method": "check",
	"status": "succeeded",
	"gateway": null,
	"gateway_id": null,
	"payment_source": null,
	"currency": "usd",
	"amount": 800,
	"notes": null,
	"parent_transaction": null,
	"pdf_url": "https://dundermifflin.invoiced.com/payments/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
	"created_at": 1415228628,
    "metadata": {}
}
```

```ruby
#<Invoiced::Transaction:0x3fdbf95e4d08 id=20939> JSON: {
	"id": 20939,
	"object": "transaction",
	"customer": 15460,
	"invoice": 44648,
	"credit_note": null,
	"date": 1410843600,
	"type": "payment",
	"method": "check",
	"status": "succeeded",
	"gateway": null,
	"gateway_id": null,
	"payment_source": null,
	"currency": "usd",
	"amount": 800,
	"notes": null,
	"parent_transaction": null,
	"pdf_url": "https://dundermifflin.invoiced.com/payments/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
	"created_at": 1415228628,
    "metadata": {}
}
```

```php
Invoiced\Transaction JSON: {
	"id": 20939,
	"object": "transaction",
	"customer": 15460,
	"invoice": 44648,
	"credit_note": null,
	"date": 1410843600,
	"type": "payment",
	"method": "check",
	"status": "succeeded",
	"gateway": null,
	"gateway_id": null,
	"payment_source": null,
	"currency": "usd",
	"amount": 800,
	"notes": null,
	"parent_transaction": null,
	"pdf_url": "https://dundermifflin.invoiced.com/payments/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
	"created_at": 1415228628,
    "metadata": {}
}
```

```python
<Transaction id=20939 at 0x3fdbf95e4d08> JSON: {
	"id": 20939,
	"object": "transaction",
	"customer": 15460,
	"invoice": 44648,
	"credit_note": null,
	"date": 1410843600,
	"type": "payment",
	"method": "check",
	"status": "succeeded",
	"gateway": null,
	"gateway_id": null,
	"payment_source": null,
	"currency": "usd",
	"amount": 800,
	"notes": null,
	"parent_transaction": null,
	"pdf_url": "https://dundermifflin.invoiced.com/payments/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
	"created_at": 1415228628,
    "metadata": {}
}
```

```java
com.invoiced.entity.Transaction@4ed0a875 JSON: {
	"id": 20939,
	"object": "transaction",
	"customer": 15460,
	"invoice": 44648,
	"credit_note": null,
	"date": 1410843600,
	"type": "payment",
	"method": "check",
	"status": "succeeded",
	"gateway": null,
	"gateway_id": null,
	"payment_source": null,
	"currency": "usd",
	"amount": 800,
	"notes": null,
	"parent_transaction": null,
	"pdf_url": "https://dundermifflin.invoiced.com/payments/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
	"created_at": 1415228628,
    "metadata": {}
}
```

Parameter | Type | Description
--------- | ---- | -----------
**id** | *integer* | The transaction's unique ID
**object** | *string* | Object type, `transaction`
**customer** | *integer* | Associated Customer
**invoice** | *integer* | Associated Invoice, if any
**credit_note** | *integer* | Associated Credit Note, if any
**date** | *timestamp* | Transaction date
**type** | *string* | Transaction type, `charge`, `payment`, `refund`, or `adjustment`
**method** | *string* | Payment instrument used to facilitate transaction
**status** | *string* | Transaction status, one of `succeeded`, `pending`, or `failed`
**gateway** | *string* | Payment gateway that processed the transaction, if any
**gateway_id** | *string* | Transaction ID from the payment gateway
**payment_source** | *object* | Payment source used for transaction, if any
**currency** | *string* | [3-letter ISO code](https://en.wikipedia.org/wiki/ISO_4217)
**amount** | *number* | Transaction amount
**notes** | *string* | Internal notes
**failure_reason** | *string* | Failure message from the payment gateway (only available when `status` = `failed`)
**parent_transaction** | *integer* | ID of the original transaction for refunds
**pdf_url** | *string* | URL to download the invoice as a PDF
**created_at** | *timestamp* | Timestamp when created
**metadata** | *object* | A hash of key/value pairs that can store additional information about this object.

## Create a transaction

```shell
curl "https://api.invoiced.com/transactions" \
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

```php
<?php

$invoiced->Transaction->create([
  'invoice' => 44648,
  'method' => "check",
  'gateway_id' => "1450",
  'amount' => 800
]);
```

```python
client.Transaction.create(
  invoice=44648,
  method="check",
  gateway_id="1450",
  amount=800
)
```

```java
Transaction transaction = invoiced.newTransaction();
transaction.invoice = 44648;
transaction.method = "check";
transaction.gatewayId = "1450";
transaction.amount = 800;
transaction.create();
```

> The above command returns JSON structured like this:

```shell
{
	"id": 20939,
	"object": "transaction",
	"customer": 15460,
	"invoice": 44648,
	"credit_note": null,
	"date": 1410843600,
	"type": "payment",
	"method": "check",
	"status": "succeeded",
	"gateway": null,
	"gateway_id": "1450",
	"payment_source": null,
	"currency": "usd",
	"amount": 800,
	"notes": null,
	"parent_transaction": null,
	"pdf_url": "https://dundermifflin.invoiced.com/payments/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
	"created_at": 1415228628,
    "metadata": {}
}
```

```ruby
#<Invoiced::Transaction:0x3fdbf95e4d08 id=30939> JSON: {
	"id": 20939,
	"object": "transaction",
	"customer": 15460,
	"invoice": 44648,
	"credit_note": null,
	"date": 1410843600,
	"type": "payment",
	"method": "check",
	"status": "succeeded",
	"gateway": null,
	"gateway_id": "1450",
	"payment_source": null,
	"currency": "usd",
	"amount": 800,
	"notes": null,
	"parent_transaction": null,
	"pdf_url": "https://dundermifflin.invoiced.com/payments/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
	"created_at": 1415228628,
    "metadata": {}
}
```

```php
Invoiced\Transaction JSON: {
	"id": 20939,
	"object": "transaction",
	"customer": 15460,
	"invoice": 44648,
	"credit_note": null,
	"date": 1410843600,
	"type": "payment",
	"method": "check",
	"status": "succeeded",
	"gateway": null,
	"gateway_id": "1450",
	"payment_source": null,
	"currency": "usd",
	"amount": 800,
	"notes": null,
	"parent_transaction": null,
	"pdf_url": "https://dundermifflin.invoiced.com/payments/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
	"created_at": 1415228628,
    "metadata": {}
}
```

```python
<Transaction id=20939 at 0x3fdbf95e4d08> JSON: {
	"id": 20939,
	"object": "transaction",
	"customer": 15460,
	"invoice": 44648,
	"credit_note": null,
	"date": 1410843600,
	"type": "payment",
	"method": "check",
	"status": "succeeded",
	"gateway": null,
	"gateway_id": "1450",
	"payment_source": null,
	"currency": "usd",
	"amount": 800,
	"notes": null,
	"parent_transaction": null,
	"pdf_url": "https://dundermifflin.invoiced.com/payments/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
	"created_at": 1415228628,
    "metadata": {}
}
```

```java
com.invoiced.entity.Transaction@4ed0a875 JSON: {
	"id": 20939,
	"object": "transaction",
	"customer": 15460,
	"invoice": 44648,
	"credit_note": null,
	"date": 1410843600,
	"type": "payment",
	"method": "check",
	"status": "succeeded",
	"gateway": null,
	"gateway_id": "1450",
	"payment_source": null,
	"currency": "usd",
	"amount": 800,
	"notes": null,
	"parent_transaction": null,
	"pdf_url": "https://dundermifflin.invoiced.com/payments/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
	"created_at": 1415228628,
    "metadata": {}
}
```

Create a new transaction with this endpoint.

### HTTP Request

`POST /transactions`

### Attributes

Parameter | Type | Description
--------- | ---- | -----------
**customer** | *integer* | Customer ID, required if invoice ID is not supplied
**invoice** | *integer* | Invoice ID, if any
**credit_note** | *integer* | Associated Credit Note, if any
**type** | *string* | Transaction type, `charge`, `payment`, `refund`, or `adjustment` - **required**
**date** | *timestamp* | Transaction date, defaults to current timestamp
**method** | *string* | Payment instrument used to facilitate transaction, defaults to `other`
**status** | *string* | Transaction status, one of `succeeded`, `pending`, or `failed`, defaults to `succeeded`
**gateway** | *string* | Payment gateway that processed the transaction, if any
**gateway_id** | *string* | Transaction ID from the payment gateway, or check # if method is `check`
**currency** | *string* | [3-letter ISO code](https://en.wikipedia.org/wiki/ISO_4217)
**amount** | *number* | Transaction amount
**notes** | *string* | Internal notes
**metadata** | *object* | A hash of key/value pairs that can store additional information about this object.

## Retrieve a transaction

```shell
curl "https://api.invoiced.com/transactions/:id" \
  -u {API_KEY}:
```

```ruby
transaction = invoiced.Transaction.retrieve("{TRANSACTION_ID}")
```

```php
<?php

$transaction = $invoiced->Transaction->retrieve("{TRANSACTION_ID}");
```

```python
transaction = client.Transaction.retrieve("{TRANSACTION_ID}")
```

```java
Transaction transaction = invoiced.newTransaction().retrieve({TRANSACTION_ID});
```

> The above command returns JSON structured like this:

```shell
{
	"id": 20939,
	"object": "transaction",
	"customer": 15460,
	"invoice": 44648,
	"credit_note": null,
	"date": 1410843600,
	"type": "payment",
	"method": "check",
	"status": "succeeded",
	"gateway": null,
	"gateway_id": null,
	"payment_source": null,
	"currency": "usd",
	"amount": 800,
	"notes": null,
	"parent_transaction": null,
	"pdf_url": "https://dundermifflin.invoiced.com/payments/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
	"created_at": 1415228628,
    "metadata": {}
}
```

```ruby
#<Invoiced::Transaction:0x3fdbf95e4d08 id=20939> JSON: {
	"id": 20939,
	"object": "transaction",
	"customer": 15460,
	"invoice": 44648,
	"credit_note": null,
	"date": 1410843600,
	"type": "payment",
	"method": "check",
	"status": "succeeded",
	"gateway": null,
	"gateway_id": null,
	"payment_source": null,
	"currency": "usd",
	"amount": 800,
	"notes": null,
	"parent_transaction": null,
	"pdf_url": "https://dundermifflin.invoiced.com/payments/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
	"created_at": 1415228628,
    "metadata": {}
}
```

```php
Invoiced\Transaction JSON: {
	"id": 20939,
	"object": "transaction",
	"customer": 15460,
	"invoice": 44648,
	"credit_note": null,
	"date": 1410843600,
	"type": "payment",
	"method": "check",
	"status": "succeeded",
	"gateway": null,
	"gateway_id": null,
	"payment_source": null,
	"currency": "usd",
	"amount": 800,
	"notes": null,
	"parent_transaction": null,
	"pdf_url": "https://dundermifflin.invoiced.com/payments/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
	"created_at": 1415228628,
    "metadata": {}
}
```

```python
<Transaction id=20939 at 0x3fdbf95e4d08> JSON: {
	"id": 20939,
	"object": "transaction",
	"customer": 15460,
	"invoice": 44648,
	"credit_note": null,
	"date": 1410843600,
	"type": "payment",
	"method": "check",
	"status": "succeeded",
	"gateway": null,
	"gateway_id": null,
	"payment_source": null,
	"currency": "usd",
	"amount": 800,
	"notes": null,
	"parent_transaction": null,
	"pdf_url": "https://dundermifflin.invoiced.com/payments/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
	"created_at": 1415228628,
    "metadata": {}
}
```

```java
com.invoiced.entity.Transaction@4ed0a875 JSON: {
	"id": 20939,
	"object": "transaction",
	"customer": 15460,
	"invoice": 44648,
	"credit_note": null,
	"date": 1410843600,
	"type": "payment",
	"method": "check",
	"status": "succeeded",
	"gateway": null,
	"gateway_id": null,
	"payment_source": null,
	"currency": "usd",
	"amount": 800,
	"notes": null,
	"parent_transaction": null,
	"pdf_url": "https://dundermifflin.invoiced.com/payments/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
	"created_at": 1415228628,
    "metadata": {}
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

```php
<?php

$transaction->notes = "Check was received by Jan";
$transaction->save();
```

```python
transaction.notes = "Check was received by Jan"
transaction.save()
```

```java
transaction.notes = "Check was received by Jan";
transaction.save();
```

> The above command returns JSON structured like this:

```shell
{
	"id": 20939,
	"object": "transaction",
	"customer": 15460,
	"invoice": 44648,
	"credit_note": null,
	"date": 1410843600,
	"type": "payment",
	"method": "check",
	"status": "succeeded",
	"gateway": null,
	"gateway_id": null,
	"payment_source": null,
	"currency": "usd",
	"amount": 800,
	"notes": "Check was received by Jan",
	"parent_transaction": null,
	"pdf_url": "https://dundermifflin.invoiced.com/payments/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
	"created_at": 1415228628,
    "metadata": {}
}
```

```ruby
#<Invoiced::Transaction:0x3fdbf95e4d08 id=20939> JSON: {
	"id": 20939,
	"object": "transaction",
	"customer": 15460,
	"invoice": 44648,
	"credit_note": null,
	"date": 1410843600,
	"type": "payment",
	"method": "check",
	"status": "succeeded",
	"gateway": null,
	"gateway_id": null,
	"payment_source": null,
	"currency": "usd",
	"amount": 800,
	"notes": "Check was received by Jan",
	"parent_transaction": null,
	"pdf_url": "https://dundermifflin.invoiced.com/payments/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
	"created_at": 1415228628,
    "metadata": {}
}
```

```php
Invoiced\Transaction JSON: {
	"id": 20939,
	"object": "transaction",
	"customer": 15460,
	"invoice": 44648,
	"credit_note": null,
	"date": 1410843600,
	"type": "payment",
	"method": "check",
	"status": "succeeded",
	"gateway": null,
	"gateway_id": null,
	"payment_source": null,
	"currency": "usd",
	"amount": 800,
	"notes": "Check was received by Jan",
	"parent_transaction": null,
	"pdf_url": "https://dundermifflin.invoiced.com/payments/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
	"created_at": 1415228628,
    "metadata": {}
}
```

```python
<Transaction id=20939 at 0x3fdbf95e4d08> JSON: {
	"id": 20939,
	"object": "transaction",
	"customer": 15460,
	"invoice": 44648,
	"credit_note": null,
	"date": 1410843600,
	"type": "payment",
	"method": "check",
	"status": "succeeded",
	"gateway": null,
	"gateway_id": null,
	"payment_source": null,
	"currency": "usd",
	"amount": 800,
	"notes": "Check was received by Jan",
	"parent_transaction": null,
	"pdf_url": "https://dundermifflin.invoiced.com/payments/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
	"created_at": 1415228628,
    "metadata": {}
}
```
```java
com.invoiced.entity.Transaction@4ed0a875 JSON: {
	"id": 20939,
	"object": "transaction",
	"customer": 15460,
	"invoice": 44648,
	"credit_note": null,
	"date": 1410843600,
	"type": "payment",
	"method": "check",
	"status": "succeeded",
	"gateway": null,
	"gateway_id": null,
	"payment_source": null,
	"currency": "usd",
	"amount": 800,
	"notes": "Check was received by Jan",
	"parent_transaction": null,
	"pdf_url": "https://dundermifflin.invoiced.com/payments/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
	"created_at": 1415228628,
    "metadata": {}
}
```

Use this endpoint to update a transaction.

### HTTP Request

`PATCH /transactions/:id`

### Request Parameters

Parameter | Type | Description
--------- | ---- | -----------
**date** | *timestamp* | Transaction date, defaults to current timestamp
**method** | *string* | Payment instrument used to facilitate transaction, defaults to `other`
**status** | *string* | Transaction status, one of `succeeded`, `pending`, or `failed`, defaults to `succeeded`
**gateway** | *string* | Payment gateway that processed the transaction, if any
**gateway_id** | *string* | Transaction ID from the payment gateway, or check # if method is `check`
**currency** | *string* | [3-letter ISO code](https://en.wikipedia.org/wiki/ISO_4217)
**amount** | *number* | Transaction amount
**notes** | *string* | Internal notes
**metadata** | *object* | A hash of key/value pairs that can store additional information about this object.

## Send a receipt

```shell
curl "https://api.invoiced.com/transactions/:id/emails" \
  -u {API_KEY}: \
  -X POST
```

```ruby
emails = transaction.send
```

```php
<?php

$emails = $transaction->send();
```

```python
emails = transaction.send()
```

```java
EmailRequest emailRequest = new EmailRequest();
EmailRecipient[] emailRecipients = new EmailRecipient[1];
emailRecipients[0] = new EmailRecipient();
emailRecipients[0].name = "Client";
emailRecipients[0].email = "client@example.com";
emailRequest.to = emailRecipients;
emailRequest.subject = "Receipt for your recent payment to Dunder Mifflin, Inc.";
emailRequest.message = "Dear Client, we have attached a receipt for your most recent payment. Thank you!";
Email[] emails = transaction.send(emailRequest);
```

> The above command returns JSON structured like this:

```shell
[
  {
    "id": "f45382c6fbc44d44aa7f9a55eb2ce731",
    "object": "email",
    "state": "sent",
    "reject_reason": null,
    "email": "client@example.com",
    "template": "payment_receipt_email",
    "subject": "Receipt for your recent payment to Dunder Mifflin, Inc.",
    "message": "Dear Client, we have attached a receipt for your most recent payment. Thank you!",
    "opens": 0,
    "opens_detail": [],
    "created_at": 1436890047
  },
  { ... },
  { ... }
]
```

```ruby
[
  #<Invoiced::Email:0x3fdbf95e4d08 id=f45382c6fbc44d44aa7f9a55eb2ce731> JSON: {
    "id": "f45382c6fbc44d44aa7f9a55eb2ce731",
    "object": "email",
    "state": "sent",
    "reject_reason": null,
    "email": "client@example.com",
    "template": "payment_receipt_email",
    "subject": "Receipt for your recent payment to Dunder Mifflin, Inc.",
    "message": "Dear Client, we have attached a receipt for your most recent payment. Thank you!",
    "opens": 0,
    "opens_detail": [],
    "created_at": 1436890047
  },
  #<Invoiced::Email:0x3fdasdf95e09 id=a0s36fbc44d44aa7f9a55easdfi8ce731> JSON: { ... },
  #<Invoiced::Email:0x3fdbffge4d10 id=s90f2c6fbc44sdfj8aa7f9a55eb2ce731> JSON: { ... }
]
```

```php
[
  Invoiced\Email JSON: {
    "id": "f45382c6fbc44d44aa7f9a55eb2ce731",
    "object": "email",
    "state": "sent",
    "reject_reason": null,
    "email": "client@example.com",
    "template": "payment_receipt_email",
    "subject": "Receipt for your recent payment to Dunder Mifflin, Inc.",
    "message": "Dear Client, we have attached a receipt for your most recent payment. Thank you!",
    "opens": 0,
    "opens_detail": [],
    "created_at": 1436890047
  },
  Invoiced\Email JSON: { ... },
  Invoiced\Email JSON: { ... }
]
```

```python
[
  <Email id=f45382c6fbc44d44aa7f9a55eb2ce731 at 0x3fdbf95e4d08> JSON: {
    "id": "f45382c6fbc44d44aa7f9a55eb2ce731",
    "object": "email",
    "state": "sent",
    "reject_reason": null,
    "email": "client@example.com",
    "template": "payment_receipt_email",
    "subject": "Receipt for your recent payment to Dunder Mifflin, Inc.",
    "message": "Dear Client, we have attached a receipt for your most recent payment. Thank you!",
    "opens": 0,
    "opens_detail": [],
    "created_at": 1436890047
  },
  <Email id=a0s36fbc44d44aa7f9a55easdfi8ce731 at 0x3fdbffge4d10> JSON: { ... },
  <Email id=s90f2c6fbc44sdfj8aa7f9a55eb2ce731 at 0x3fdbffge4d10> JSON: { ... }
]
```

```java
//To pretty print a array of Objects use Arrays.toString(Object[]);
[
  com.invoiced.entity.Email@12497547 JSON: {
    "id": "f45382c6fbc44d44aa7f9a55eb2ce731",
    "object": "email",
    "state": "sent",
    "reject_reason": null,
    "email": "client@example.com",
    "template": "payment_receipt_email",
    "subject": "Receipt for your recent payment to Dunder Mifflin, Inc.",
    "message": "Dear Client, we have attached a receipt for your most recent payment. Thank you!",
    "opens": 0,
    "opens_detail": [],
    "created_at": 1436890047
  },
  com.invoiced.entity.Email@12497547 JSON: {...},
  com.invoiced.entity.Email@12497547 JSON: {...}
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
curl "https://api.invoiced.com/transactions/:id/refunds" \
  -u {API_KEY}: \
  -X POST
```

```ruby
refund = transaction.refund(:amount => 400)
```

```php
<?php

$refund = $transaction->refund(['amount' => 400]);
```

```python
refund = transaction.refund(amount=400)
```

```java
Transaction refund = transaction.refund(400);
```

> The above command returns JSON structured like this:

```shell
{
	"id": 20952,
	"object": "transaction",
	"customer": 15460,
	"invoice": 44648,
	"credit_note": null,
	"date": 1410843600,
	"type": "refund",
	"method": "check",
	"status": "succeeded",
	"gateway": null,
	"gateway_id": null,
	"payment_source": null,
	"currency": "usd",
	"amount": 400,
	"notes": null,
	"parent_transaction": 20939,
	"pdf_url": "https://dundermifflin.invoiced.com/payments/IZmXbVOPyvfD3GPBmyd6FwXY/20939pdf",
	"created_at": 1415228628,
    "metadata": {}
}
```

```ruby
#<Invoiced::Transaction:0x3fdbf95e4d08 id=20952> JSON: {
	"id": 20952,
	"object": "transaction",
	"customer": 15460,
	"invoice": 44648,
	"credit_note": null,
	"date": 1410843600,
	"type": "refund",
	"method": "check",
	"status": "succeeded",
	"gateway": null,
	"gateway_id": null,
	"payment_source": null,
	"currency": "usd",
	"amount": 400,
	"notes": null,
	"parent_transaction": 20939,
	"pdf_url": "https://dundermifflin.invoiced.com/payments/IZmXbVOPyvfD3GPBmyd6FwXY/20939pdf",
	"created_at": 1415228628,
    "metadata": {}
}
```

```php
Invoiced\Transaction JSON: {
	"id": 20952,
	"object": "transaction",
	"customer": 15460,
	"invoice": 44648,
	"credit_note": null,
	"date": 1410843600,
	"type": "refund",
	"method": "check",
	"status": "succeeded",
	"gateway": null,
	"gateway_id": null,
	"payment_source": null,
	"currency": "usd",
	"amount": 400,
	"notes": null,
	"parent_transaction": 20939,
	"pdf_url": "https://dundermifflin.invoiced.com/payments/IZmXbVOPyvfD3GPBmyd6FwXY/20939pdf",
	"created_at": 1415228628,
    "metadata": {}
}
```

```python
<Transaction id=20952 at 0x3fdbf95e4d08> JSON: {
	"id": 20952,
	"object": "transaction",
	"customer": 15460,
	"invoice": 44648,
	"credit_note": null,
	"date": 1410843600,
	"type": "refund",
	"method": "check",
	"status": "succeeded",
	"gateway": null,
	"gateway_id": null,
	"payment_source": null,
	"currency": "usd",
	"amount": 400,
	"notes": null,
	"parent_transaction": 20939,
	"pdf_url": "https://dundermifflin.invoiced.com/payments/IZmXbVOPyvfD3GPBmyd6FwXY/20939pdf",
	"created_at": 1415228628,
    "metadata": {}
}
```

```java
com.invoiced.entity.Transaction@424ba398 JSON: {
	"id": 20952,
	"object": "transaction",
	"customer": 15460,
	"invoice": 44648,
	"credit_note": null,
	"date": 1410843600,
	"type": "refund",
	"method": "check",
	"status": "succeeded",
	"gateway": null,
	"gateway_id": null,
	"payment_source": null,
	"currency": "usd",
	"amount": 400,
	"notes": null,
	"parent_transaction": 20939,
	"pdf_url": "https://dundermifflin.invoiced.com/payments/IZmXbVOPyvfD3GPBmyd6FwXY/20939pdf",
	"created_at": 1415228628,
    "metadata": {}
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

```php
<?php

$transaction->delete();
```

```python
transaction.delete()
```

```java
transaction.delete();
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

```php
<?php

list($transactions, $metadata) = $invoiced->Transaction->all(['per_page' => 3]);
```

```python
transactions, metadata = invoiced.Transaction.list(per_page=3)
```

```java
EntityList<Transaction> transactions = invoiced.newTransaction().listAll();
```

> The above command returns JSON structured like this:

```shell
[
  {
	"id": 20939,
	"object": "transaction",
	"customer": 15460,
	"invoice": 44648,
	"credit_note": null,
	"date": 1410843600,
	"type": "payment",
	"method": "check",
	"status": "succeeded",
	"gateway": null,
	"gateway_id": null,
	"payment_source": null,
	"currency": "usd",
	"amount": 800,
	"notes": null,
	"parent_transaction": null,
	"pdf_url": "https://dundermifflin.invoiced.com/payments/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
	"created_at": 1415228628,
    "metadata": {}
  },
  { ... },
  { ... }
]
```

```ruby
[
  #<Invoiced::Transaction:0x3fdbf95e4d08 id=20939> JSON: {
	"id": 20939,
	"object": "transaction",
	"customer": 15460,
	"invoice": 44648,
	"credit_note": null,
	"date": 1410843600,
	"type": "payment",
	"method": "check",
	"status": "succeeded",
	"gateway": null,
	"gateway_id": null,
	"payment_source": null,
	"currency": "usd",
	"amount": 800,
	"notes": null,
	"parent_transaction": null,
	"pdf_url": "https://dundermifflin.invoiced.com/payments/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
	"created_at": 1415228628,
    "metadata": {}
  },
  #<Invoiced::Transaction:0x3fdbf95e4d09 id=20940> JSON: { ... },
  #<Invoiced::Transaction:0x3fdbf95e4d10 id=20941> JSON: { ... }
]
```

```php
[
  Invoiced\Transaction JSON: {
	"id": 20939,
	"object": "transaction",
	"customer": 15460,
	"invoice": 44648,
	"credit_note": null,
	"date": 1410843600,
	"type": "payment",
	"method": "check",
	"status": "succeeded",
	"gateway": null,
	"gateway_id": null,
	"payment_source": null,
	"currency": "usd",
	"amount": 800,
	"notes": null,
	"parent_transaction": null,
	"pdf_url": "https://dundermifflin.invoiced.com/payments/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
	"created_at": 1415228628,
    "metadata": {}
  },
  Invoiced\Transaction JSON: { ... },
  Invoiced\Transaction JSON: { ... }
]
```

```python
[
  <Transaction id=20939 at 0x3fdbf95e4d08> JSON: {
	"id": 20939,
	"object": "transaction",
	"customer": 15460,
	"invoice": 44648,
	"credit_note": null,
	"date": 1410843600,
	"type": "payment",
	"method": "check",
	"status": "succeeded",
	"gateway": null,
	"gateway_id": null,
	"payment_source": null,
	"currency": "usd",
	"amount": 800,
	"notes": null,
	"parent_transaction": null,
	"pdf_url": "https://dundermifflin.invoiced.com/payments/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
	"created_at": 1415228628,
    "metadata": {}
  },
  <Transaction id=20940 at 0x3fdbf95e4d08> JSON: { ... },
  <Transaction id=20941 at 0x3fdbf95e4d08> JSON: { ... }
]
```

```java
[
  com.invoiced.entity.Transaction@52638766 JSON: {
	"id": 20939,
	"object": "transaction",
	"customer": 15460,
	"invoice": 44648,
	"credit_note": null,
	"date": 1410843600,
	"type": "payment",
	"method": "check",
	"status": "succeeded",
	"gateway": null,
	"gateway_id": null,
	"payment_source": null,
	"currency": "usd",
	"amount": 800,
	"notes": null,
	"parent_transaction": null,
	"pdf_url": "https://dundermifflin.invoiced.com/payments/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
	"created_at": 1415228628,
    "metadata": {}
  },
  com.invoiced.entity.Transaction@5c01c09f JSON: {...},
  com.invoiced.entity.Transaction@5c01a09f JSON: {...}
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
**metadata** *object* | Metadata filter object
**start_date** *timestamp* | Restricts the results to transactions *on or after* the given timestamp
**end_date** *timestamp* | Restricts the results to transactions *on or before* the given timestamp
**updated_after** *timestamp* | Only gets records updated after the given timestamp
