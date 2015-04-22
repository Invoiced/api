Transactions
====

Transactions can represent a `charge`, `payment`, `refund`, or `adjustment`.

* [Intro](#intro)
* [List Transactions](#list-transactions)
* [Creating a Transaction](#creating-a-transaction)
* [Fetch a Transaction](#fetch-a-transaction)
* [Editing a Transaction](#editing-a-transaction)
* [Sending a Payment Receipt](#sending-a-payment-receipt)
* [Deleting a Transaction](#deleting-a-transaction)

### Intro

We record `charge` and `refund` transactions automatically. The `payment` transaction type is designated for recording offline payments like checks. Finally, an `adjustment` transaction can represent any additional credit or debits to a customer's balance.

The `method` property specifies the instrument the transaction was performed with. For more information about supported payment methods please see the [Payment Methods](PaymentMethods.md) section.

### List Transactions

  GET /transactions

#### Parameters

Name | Type | Description
-----|------|-------------
`sort`|`string`|Column to sort by, i.e. `name asc`
`filter`|`object`|[Filter](../README.md#filter)

#### Response

```
Status: 200 OK
Link: <https://api.invoiced.com/transactions?page=1&per_page=10>; rel="self",
    <https://api.invoiced.com/transactions?page=1&per_page=10>; rel="first",
    <https://api.invoiced.com/transactions?page=2&per_page=10>; rel="next",
    <https://api.invoiced.com/transactions?page=3&per_page=10>; rel="last"
X-Total-Count: 30
```

```json
{
  "transactions": [
    ...,
    {
      "created_at": 1415228628,
      "updated_at": 1415228642,
      "id": 20939,
      "customer": 15460,
      "invoice": 44648,
      "theme": null,
      "date": 1410843600,
      "transaction_type": "payment",
      "method": "check",
      "status": "succeeded",
      "gateway": null,
      "gateway_id": null,
      "currency": "usd",
      "amount": 800,
      "fee": 0,
      "net": 800,
      "notes": null,
      "sent": false,
      "pdf_url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY/20939/pdf"
    },
    ...
  ]
}
```

### Creating a Transaction

  POST /transactions

#### Input

```json
{
  "invoice": 44648,
  "date": 1410843600,
  "method": "check",
  "currency": "usd",
  "amount": 800,
  "notes": "Extra notes about the payment for the customer",
  "gateway_id": "Optional check # goes here"
}
```

#### Response

  Status: 201 Created

```json
{
  "transaction": {
    "created_at": 1415228628,
    "updated_at": 1415228642,
    "id": 20939,
    "customer": 15460,
    "invoice": 44648,
    "theme": null,
    "date": 1410843600,
    "transaction_type": "payment",
    "method": "check",
    "status": "succeeded",
    "gateway": null,
    "gateway_id": null,
    "currency": "usd",
    "amount": 800,
    "fee": 0,
    "net": 800,
    "notes": null,
    "sent": false,
    "pdf_url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY/20939/pdf"
  }
}
```

### Fetch a Transaction

  GET /transactions/:id

#### Response

  Status: 200 OK

```json
{
  "transaction": {
    "created_at": 1415228628,
    "updated_at": 1415228642,
    "id": 20939,
    "customer": 15460,
    "invoice": 44648,
    "theme": null,
    "date": 1410843600,
    "transaction_type": "payment",
    "method": "check",
    "status": "succeeded",
    "gateway": null,
    "gateway_id": null,
    "currency": "usd",
    "amount": 800,
    "fee": 0,
    "net": 800,
    "notes": null,
    "sent": false,
    "pdf_url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY/20939/pdf"
  }
}
```

### Editing a Transaction

  PATCH /transactions/:id

#### Input

```json
{
  "notes": "Received by Jan",
  "sent": true
}
```

#### Response

  Status: 200 OK

```json
{
  "success": true
}
```

### Sending a Payment Receipt

  POST /transactions/:id/emails

#### Input

```json
{
  "to": [
    {
      "name": "Client",
      "email": "client@example.com"
    }
  ],
  "bcc": "billing@acmecorp.com,jan@acmecorp.com",
  "subject": "subject...",
  "message": "message...",
  "attach_pdf": true
}
```

#### Response

  Status: 201 Created

```json
{
  "success": true
}
```

### Deleting a Transaction

  DELETE /transactions/:id

#### Response

  Status: 204 No Content