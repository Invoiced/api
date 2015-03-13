Estimates
====

* [List Estimates](#list-estimates)
* [Creating an Estimate](#creating-an-estimate)
* [Fetch an Estimate](#fetch-an-estimate)
* [Sending an Estimate](#sending-an-estimate)
* [Converting an Estimate into an Invoice](#converting-an-estimate-into-an-invoice)
* [Editing an Estimate](#editing-an-estimate)
* [Deleting an Estimate](#deleting-an-estimate)

### List Estimates

  GET /estimates

#### Parameters

Name | Type | Description
-----|------|-------------
`sort`|`string`|Column to sort by, i.e. `name asc`
`filter`|`object`|[Filter](../README.md#filter)

#### Response

```
Status: 200 OK
Link: <https://api.invoiced.com/estimates?page=1&per_page=10>; rel="self",
    <https://api.invoiced.com/estimates?page=1&per_page=10>; rel="first",
    <https://api.invoiced.com/estimates?page=2&per_page=10>; rel="next",
    <https://api.invoiced.com/estimates?page=3&per_page=10>; rel="last"
X-Total-Count: 30
```

```json
{
  "estimates": [
    {
      "created_at": 1415223825,
      "updated_at": 1415223841,
      "id": 1410,
      "company": 3694,
      "customer": 15453,
      "name": "Estimate # EST-0002",
      "currency": "USD",
      "date_format": "M j, Y",
      "template": null,
      "number": "EST-0002",
      "date": 1415223417,
      "purchase_order": null,
      "items": [
        {
          "id": 1,
          "item": 79,
          "type": "product",
          "name": "Copy Paper, Case",
          "description": "20 lb., 92 US / 104 Euro Bright, Ideal for toner-based copiers, plain-paper fax machines,and printers",
          "quantity": 10,
          "unit_cost": 45,
          "amount": 450,
          "fields": []
        },
        {
          "id": 2,
          "item": 82,
          "type": "product",
          "name": "Jumbo Paper Clips, Box",
          "description": "1,000 pack",
          "quantity": 2,
          "unit_cost": 9,
          "amount": 18,
          "fields": []
        },
        {
          "id": 3,
          "item": 83,
          "type": "service",
          "name": "Delivery",
          "description": "",
          "quantity": 1,
          "unit_cost": 10,
          "amount": 10,
          "fields": []
        }
      ],
      "terms": "Net 30",
      "notes": "Thank you for your business!",
      "subtotal": 478,
      "total": 478,
      "fields": [],
      "sent": false,
      "url": "https://dundermifflin.invoiced.com/estimates/ZZmXbVOPyvfD3GPBmyd6FwXY",
      "pdf_url": "https://dundermifflin.invoiced.com/estimates/ZZmXbVOPyvfD3GPBmyd6FwXY/pdf",
      "status": "invoiced"
    },
    {...}
  ]
}
```

### Creating an Estimate

  POST /estimates

#### Input

```json
{
  "customer": 15453,
  "name": null,
  "currency": "USD",
  "template": null,
  "number": "EST-0002",
  "date": 1415223417,
  "purchase_order": null,
  "items": [
    {
      "item": 79,
      "type": "product",
      "name": "Copy Paper, Case",
      "description": "20 lb., 92 US / 104 Euro Bright, Ideal for toner-based copiers, plain-paper fax machines,and printers",
      "quantity": 10,
      "unit_cost": 45,
      "amount": 450,
      "fields": []
    },
    {
      "item": 82,
      "type": "product",
      "name": "Jumbo Paper Clips, Box",
      "description": "1,000 pack",
      "quantity": 2,
      "unit_cost": 9,
      "amount": 18,
      "fields": []
    },
    {
      "item": 83,
      "type": "service",
      "name": "Delivery",
      "description": "",
      "quantity": 1,
      "unit_cost": 10,
      "amount": 10,
      "fields": []
    }
  ],
  "terms": "Net 30",
  "notes": "Thank you for your business!",
  "fields": [],
  "sent": false
}
```

#### Response

  Status: 201 Created

```json
{
  "estimate": {
    "created_at": 1415223825,
    "updated_at": null,
    "id": 1410,
    "company": 3694,
    "customer": 15453,
    "name": "Estimate # EST-0002",
    "currency": "USD",
    "date_format": "M j, Y",
    "template": null,
    "number": "EST-0002",
    "date": 1415223417,
    "purchase_order": null,
    "items": [
      {
        "id": 1,
        "item": 79,
        "type": "product",
        "name": "Copy Paper, Case",
        "description": "20 lb., 92 US / 104 Euro Bright, Ideal for toner-based copiers, plain-paper fax machines,and printers",
        "quantity": 10,
        "unit_cost": 45,
        "amount": 450,
        "fields": []
      },
      {
        "id": 2,
        "item": 82,
        "type": "product",
        "name": "Jumbo Paper Clips, Box",
        "description": "1,000 pack",
        "quantity": 2,
        "unit_cost": 9,
        "amount": 18,
        "fields": []
      },
      {
        "id": 3,
        "item": 83,
        "type": "service",
        "name": "Delivery",
        "description": "",
        "quantity": 1,
        "unit_cost": 10,
        "amount": 10,
        "fields": []
      }
    ],
    "terms": "Net 30",
    "notes": "Thank you for your business!",
    "subtotal": 478,
    "total": 478,       
    "fields": [],
    "sent": false,
    "url": "https://dundermifflin.invoiced.com/estimates/ZZmXbVOPyvfD3GPBmyd6FwXY",
    "pdf_url": "https://dundermifflin.invoiced.com/estimates/ZZmXbVOPyvfD3GPBmyd6FwXY/pdf",
    "status": "invoiced"
  }
}
```

### Fetch an Estimate

  GET /estimates/:id

#### Response

  Status: 200 OK

```json
{
  "estimate": {
    "created_at": 1415223825,
    "updated_at": 1415223841,
    "id": 1410,
    "company": 3694,
    "name": "Estimate # EST-0002",
    "customer": 15453,
    "currency": "USD",
    "date_format": "M j, Y",
    "template": null,
    "number": "EST-0002",
    "date": 1415223417,
    "purchase_order": null,
    "items": [
      {
        "id": 1,
        "item": 79,
        "type": "product",
        "name": "Copy Paper, Case",
        "description": "20 lb., 92 US / 104 Euro Bright, Ideal for toner-based copiers, plain-paper fax machines,and printers",
        "quantity": 10,
        "unit_cost": 45,
        "amount": 450,
        "fields": []
      },
      {
        "id": 2,
        "item": 82,
        "type": "product",
        "name": "Jumbo Paper Clips, Box",
        "description": "1,000 pack",
        "quantity": 2,
        "unit_cost": 9,
        "amount": 18,
        "fields": []
      },
      {
        "id": 3,
        "item": 83,
        "type": "service",
        "name": "Delivery",
        "description": "",
        "quantity": 1,
        "unit_cost": 10,
        "amount": 10,
        "fields": []
      }
    ],
    "terms": "Net 30",
    "notes": "Thank you for your business!",
    "subtotal": 478,
    "total": 478,
    "fields": [],
    "sent": false,
    "url": "https://dundermifflin.invoiced.com/estimates/ZZmXbVOPyvfD3GPBmyd6FwXY",
    "pdf_url": "https://dundermifflin.invoiced.com/estimates/ZZmXbVOPyvfD3GPBmyd6FwXY/pdf",
    "status": "invoiced"
  }
}
```

### Editing an Estimate

  PATCH /estimates/:id

#### Input

```json
{
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

### Sending an Estimate

  POST /estimates/:id/emails

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

### Converting an Estimate into an Invoice

  POST /estimates/:id/invoice

#### Response

  Status: 201 Created

```json
{
  "invoice": {
    "created_at": 1415229884,
    "updated_at": 1416291302,
    "id": 4522,
    "company": 3694,
    "customer": 15453,
    "name": "Invoice # INV-0015",
    "currency": "USD",
    "date_format": "M j, Y",
    "late_payment_reminders_disabled": false,
    "template": null,
    "estimate": 1410,
    "subscription": null,
    "number": "INV-0015",
    "date": 1415223417,
    "due_date": null,
    "purchase_order": null,
    "items": [
      {
        "id": 4,
        "item": 79,
        "type": "product",
        "name": "Copy Paper, Case",
        "description": "20 lb., 92 US / 104 Euro Bright, Ideal for toner-based copiers, plain-paper fax machines,and printers",
        "quantity": 10,
        "unit_cost": 45,
        "amount": 450,
        "fields": []
      },
      {
        "id": 5,
        "item": 82,
        "type": "product",
        "name": "Jumbo Paper Clips, Box",
        "description": "1,000 pack",
        "quantity": 2,
        "unit_cost": 9,
        "amount": 18,
        "fields": []
      },
      {
        "id": 6,
        "item": 83,
        "type": "service",
        "name": "Delivery",
        "description": "",
        "quantity": 1,
        "unit_cost": 10,
        "amount": 10,
        "fields": []
      }
    ],
    "notes": "Thank you for your business!",
    "terms": "Net 30",
    "subtotal": 478,
    "total": 478,
    "amount_paid": 0,
    "balance": 478,
    "fields": [],
    "sent": false,
    "closed": false,
    "paid": false,
    "url": "https://dundermifflin.invoiced.com/estimates/ZZmXbVOPyvfD3GPBmyd6FwXY",
    "pdf_url": "https://dundermifflin.invoiced.com/estimates/ZZmXbVOPyvfD3GPBmyd6FwXY/pdf",
    "status": "overdue"
  }
}
```

### Deleting an Estimate

  DELETE /estimates/:id

#### Response

  Status: 204 No Content