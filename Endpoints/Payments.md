Payments
====

* [List Payments](#list-payments)
* [Creating a Payment](#creating-a-payment)
* [Fetch a Payment](#fetch-a-payment)
* [Editing a Payment](#editing-a-payment)
* [Sending a Payment Receipt](#sending-a-payment-receipt)
* [Deleting a Payment](#deleting-a-payment)

### List Payments

  GET /payments

#### Parameters

Name | Type | Description
-----|------|-------------
`sort`|`string`|Column to sort by, i.e. `name asc`
`filter`|`object`|[Filter](../README.md#filter)

#### Response

```
Status: 200 OK
Link: <https://api.invoiced.com/payments?page=1&per_page=10>; rel="self",
    <https://api.invoiced.com/payments?page=1&per_page=10>; rel="first",
    <https://api.invoiced.com/payments?page=2&per_page=10>; rel="next",
    <https://api.invoiced.com/payments?page=3&per_page=10>; rel="last"
X-Total-Count: 30
```

```json
payments: [
  {
    "created_at": 1415228628,
    "updated_at": 1415228642,
    "id": 20939,
    "customer": 15460,
    "invoice": 44648,
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
  {...}
   ]
```

### Creating a Payment

  POST /payments

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
  "payment": {
    "created_at": 1415228628,
    "updated_at": 1415228642,
    "id": 20939,
    "customer": 15460,
    "invoice": 44648,
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

### Fetch a Payment

  GET /payments/:id

#### Response

  Status: 200 OK

```json
{
  "payment": {
    "created_at": 1415228628,
    "updated_at": 1415228642,
    "id": 20939,
    "customer": 15460,
    "invoice": 44648,
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

### Editing a Payment

  PATCH /payments/:id

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

  POST /payments/:id/emails

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

### Deleting a Payment

  DELETE /payments/:id

#### Response

  Status: 204 No Content