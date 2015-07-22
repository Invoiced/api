Invoices
====

Invoices can be marked paid by adding payments via [Transactions](Transactions.md).

* [List Invoices](#list-invoices)
* [Creating an Invoice](#creating-an-invoice)
* [Fetch an Invoice](#fetch-an-invoice)
* [Editing an Invoice](#editing-an-invoice)
* [Sending an Invoice](#sending-an-invoice)
* [Deleting a Customer](#deleting-an-invoice)

### List Invoices

  GET /invoices

#### Parameters

Name | Type | Description
-----|------|-------------
`sort`|`string`|Column to sort by, i.e. `name asc`
`filter`|`object`|[Filter](../README.md#filter)
`status`|`string`|Can be `paid`, `sent`, `overdue`, or `not_sent`

#### Response

```
Status: 200 OK
Link: <https://api.invoiced.com/invoices?page=1&per_page=10>; rel="self",
    <https://api.invoiced.com/invoices?page=1&per_page=10>; rel="first",
    <https://api.invoiced.com/invoices?page=2&per_page=10>; rel="next",
    <https://api.invoiced.com/invoices?page=3&per_page=10>; rel="last"
X-Total-Count: 10
```

```json
{
    "invoices": [
        ...,
        {
          "created_at": 1415229884,
          "updated_at": 1416291302,
          "id": 46225,
          "customer": 15444,
          "name": "Monthly Paper Delivery",
          "currency": "usd",
          "draft": false,
          "sent": false,
          "closed": false,
          "paid": false,
          "status": "not_sent",
          "chase": false,
          "next_chase_on": null,
          "collection_mode": "manual",
          "attempt_count": 0,
          "next_payment_attempt": null,
          "theme": null,
          "disabled_payment_methods": {
            "paypal": true
          },
          "estimate": null,
          "subscription": 410,
          "number": "INV-0016",
          "date": 1416290400,
          "due_date": 1416549600,
          "payment_terms": null,
          "purchase_order": null,
          "items": [
            {
              "id": 7,
              "item": 79,
              "plan": null,
              "type": "product",
              "name": "Copy Paper, Case",
              "description": "20 lb., 92 US / 104 Euro Bright, Ideal for toner-based copiers, plain-paper fax machines,and printers",
              "quantity": 1,
              "unit_cost": 45,
              "amount": 45,
              "discounts": [],
              "taxes": []
            },
            {
              "id": 8,
              "item": 83,
              "plan": null,
              "type": "service",
              "name": "Delivery",
              "description": "",
              "quantity": 1,
              "unit_cost": 10,
              "amount": 10,
              "discounts": [],
              "taxes": []
            }
          ],
          "terms": null,
          "notes": null,
          "subtotal": 55,
          "discounts": [],
          "taxes": [
            {
              "id": 2084,
              "amount": 3.85,
              "rate": {
                "id": 304,
                "name": "Sales Tax",
                "number": "FI-8200",
                "is_percent": true,
                "value": 7
              }
            }
          ],
          "shipping": [],
          "total": 51.15,
          "amount_paid": 0,
          "amount_adjusted": 0,
          "balance": 51.15,
          "url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY",
          "pdf_url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
          "csv_url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY/csv"
        },
        ...
    ]
}
```

### Creating an Invoice

  POST /invoices

#### Input

```json
{
  "customer": 15444,
  "name": null,
  "currency": "usd",
  "theme": 432,
  "number": "INV-0016",
  "date": 1416290400,
  "due_date": 1416549600,
  "payment_terms": null,
  "purchase_order": null,
  "items": [
    {
      "item": 79,
      "type": "product",
      "name": "Copy Paper, Case",
      "description": "20 lb., 92 US / 104 Euro Bright, Ideal for toner-based copiers, plain-paper fax machines,and printers",
      "quantity": 1,
      "unit_cost": 45,
      "discounts": [],
      "taxes": []
    },
    {
      "item": 83,
      "type": "service",
      "name": "Delivery",
      "description": "",
      "quantity": 1,
      "unit_cost": 10,
      "discounts": [],
      "taxes": []
    }
  ],
  "discounts": [],
  "taxes": [
    {
      "rate": 304
    }
  ],
  "shipping": [],
  "terms": null,
  "notes": null,
  "disabled_payment_methods": {
    "paypal": true
  },
  "chase": false
}
```

#### Response

  Status: 201 Created

```json
{
  "invoice": {
      "created_at": 1415229884,
      "updated_at": 1416291302,
      "id": 46225,
      "customer": 15444,
      "name": "Monthly Paper Delivery",
      "currency": "usd",
      "draft": false,
      "sent": false,
      "closed": false,
      "paid": false,
      "status": "not_sent",
      "chase": false,
      "next_chase_on": null,
      "collection_mode": "manual",
      "attempt_count": 0,
      "next_payment_attempt": null,
      "theme": null,
      "disabled_payment_methods": {
        "paypal": true
      },
      "estimate": null,
      "subscription": 410,
      "number": "INV-0016",
      "date": 1416290400,
      "due_date": 1416549600,
      "payment_terms": null,
      "purchase_order": null,
      "items": [
        {
          "id": 7,
          "item": 79,
          "plan": null,
          "type": "product",
          "name": "Copy Paper, Case",
          "description": "20 lb., 92 US / 104 Euro Bright, Ideal for toner-based copiers, plain-paper fax machines,and printers",
          "quantity": 1,
          "unit_cost": 45,
          "amount": 45,
          "discounts": [],
          "taxes": []
        },
        {
          "id": 8,
          "item": 83,
          "plan": null,
          "type": "service",
          "name": "Delivery",
          "description": "",
          "quantity": 1,
          "unit_cost": 10,
          "amount": 10,
          "discounts": [],
          "taxes": []
        }
      ],
      "terms": null,
      "notes": null,
      "subtotal": 55,
      "discounts": [],
      "taxes": [
        {
          "id": 2084,
          "amount": 3.85,
          "rate": {
            "id": 304,
            "name": "Sales Tax",
            "number": "FI-8200",
            "is_percent": true,
            "value": 7
          }
        }
      ],
      "shipping": [],
      "total": 51.15,
      "amount_paid": 0,
      "amount_adjusted": 0,
      "balance": 51.15,
      "url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY",
      "pdf_url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
      "csv_url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY/csv"
  }
}
```

### Fetch an Invoice
  
  GET /invoices/:id

#### Response

  Status: 200 OK

```json
{
  "invoice": {
      "created_at": 1415229884,
      "updated_at": 1416291302,
      "id": 46225,
      "customer": 15444,
      "name": "Monthly Paper Delivery",
      "currency": "usd",
      "draft": false,
      "sent": false,
      "closed": false,
      "paid": false,
      "status": "not_sent",
      "chase": false,
      "next_chase_on": null,
      "collection_mode": "manual",
      "attempt_count": 0,
      "next_payment_attempt": null,
      "theme": null,
      "disabled_payment_methods": {
        "paypal": true
      },
      "estimate": null,
      "subscription": 410,
      "number": "INV-0016",
      "date": 1416290400,
      "due_date": 1416549600,
      "payment_terms": null,
      "purchase_order": null,
      "items": [
        {
          "id": 7,
          "item": 79,
          "plan": null,
          "type": "product",
          "name": "Copy Paper, Case",
          "description": "20 lb., 92 US / 104 Euro Bright, Ideal for toner-based copiers, plain-paper fax machines,and printers",
          "quantity": 1,
          "unit_cost": 45,
          "amount": 45,
          "discounts": [],
          "taxes": []
        },
        {
          "id": 8,
          "item": 83,
          "plan": null,
          "type": "service",
          "name": "Delivery",
          "description": "",
          "quantity": 1,
          "unit_cost": 10,
          "amount": 10,
          "discounts": [],
          "taxes": []
        }
      ],
      "terms": null,
      "notes": null,
      "subtotal": 55,
      "discounts": [],
      "taxes": [
        {
          "id": 2084,
          "amount": 3.85,
          "rate": {
            "id": 304,
            "name": "Sales Tax",
            "number": "FI-8200",
            "is_percent": true,
            "value": 7
          }
        }
      ],
      "shipping": [],
      "total": 51.15,
      "amount_paid": 0,
      "amount_adjusted": 0,
      "balance": 51.15,
      "url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY",
      "pdf_url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
      "csv_url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY/csv"
  }
}
```

### Editing an Invoice

  PATCH /invoices/:id

#### Input

```json
{
  "draft": false,
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

### Sending an Invoice

  POST /invoices/:id/emails

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
  "subject": "optional subject...",
  "message": "optional message...",
  "attach_pdf": false
}
```

#### Response

  Status: 201 Created

```json
{
  "success": true
}
```

### Deleting an Invoice

  DELETE /invoices/:id

#### Response

  Status: 204 No Content