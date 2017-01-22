# Credit Notes

A credit note represents a balance you owe to a [Customer](#customer-object). Like invoices, each credit note has a collection of line items that detail the products or services that are being credited to the customer. You can think of credit notes as negative invoices, however, all of the amounts should be positive.

Credit notes must be issued against an existing invoice. The credit note will be applied to the balance on the invoice first. Any remaining balance should be credited to the customer.

Credit notes with a balance can be marked as paid by issuing a credit for the credit note using [Transactions](#transaction-object). Once the sum of all transactions for a credit note is greater than or equal to the total then the credit note will be considered paid in full.

## Credit Note Object

### Attributes

```shell
{
  "id": 2048,
  "object": "credit_note",
  "customer": 15444,
  "invoice": 46225,
  "name": null,
  "currency": "usd",
  "draft": false,
  "closed": false,
  "paid": false,
  "status": "open",
  "number": "CN-0016",
  "date": 1416290400,
  "items": [
    {
      "id": 7,
      "object": "line_item",
      "catalog_item": null,
      "type": "product",
      "name": "Copy Paper, Case",
      "description": null,
      "quantity": 1,
      "unit_cost": 45,
      "amount": 45,
      "discountable": true,
      "discounts": [],
      "taxable": true,
      "taxes": [],
      "metadata": {}
    },
    {
      "id": 8,
      "object": "line_item",
      "catalog_item": "delivery",
      "type": "service",
      "name": "Delivery",
      "description": null,
      "quantity": 1,
      "unit_cost": 10,
      "amount": 10,
      "discountable": true,
      "discounts": [],
      "taxable": true,
      "taxes": [],
      "metadata": {}
    }
  ],
  "notes": null,
  "subtotal": 55,
  "discounts": [],
  "taxes": [
    {
      "id": 20554,
      "object": "tax",
      "amount": 3.85,
      "tax_rate": null
    }
  ],
  "total": 51.15,
  "balance": 51.15,
  "url": "https://dundermifflin.invoiced.com/credit_notes/IZmXbVOPyvfD3GPBmyd6FwXY",
  "pdf_url": "https://dundermifflin.invoiced.com/credit_notes/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
  "created_at": 1415229884,
  "metadata": {}
}
```

```ruby
#<Invoiced::CreditNote:0x3fdbf95e4d08 id=2048> JSON: {
  "id": 2048,
  "object": "credit_note",
  "customer": 15444,
  "invoice": 46225,
  "name": null,
  "currency": "usd",
  "draft": false,
  "closed": false,
  "paid": false,
  "status": "open",
  "number": "CN-0016",
  "date": 1416290400,
  "items": [
    {
      "id": 7,
      "object": "line_item",
      "catalog_item": null,
      "type": "product",
      "name": "Copy Paper, Case",
      "description": null,
      "quantity": 1,
      "unit_cost": 45,
      "amount": 45,
      "discountable": true,
      "discounts": [],
      "taxable": true,
      "taxes": [],
      "metadata": {}
    },
    {
      "id": 8,
      "object": "line_item",
      "catalog_item": "delivery",
      "type": "service",
      "name": "Delivery",
      "description": null,
      "quantity": 1,
      "unit_cost": 10,
      "amount": 10,
      "discountable": true,
      "discounts": [],
      "taxable": true,
      "taxes": [],
      "metadata": {}
    }
  ],
  "notes": null,
  "subtotal": 55,
  "discounts": [],
  "taxes": [
    {
      "id": 20554,
      "object": "tax",
      "amount": 3.85,
      "tax_rate": null
    }
  ],
  "total": 51.15,
  "balance": 51.15,
  "url": "https://dundermifflin.invoiced.com/credit_notes/IZmXbVOPyvfD3GPBmyd6FwXY",
  "pdf_url": "https://dundermifflin.invoiced.com/credit_notes/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
  "created_at": 1415229884,
  "metadata": {}
}
```

```php
Invoiced\CreditNote JSON: {
  "id": 2048,
  "object": "credit_note",
  "customer": 15444,
  "invoice": 46225,
  "name": null,
  "currency": "usd",
  "draft": false,
  "closed": false,
  "paid": false,
  "status": "open",
  "number": "CN-0016",
  "date": 1416290400,
  "items": [
    {
      "id": 7,
      "object": "line_item",
      "catalog_item": null,
      "type": "product",
      "name": "Copy Paper, Case",
      "description": null,
      "quantity": 1,
      "unit_cost": 45,
      "amount": 45,
      "discountable": true,
      "discounts": [],
      "taxable": true,
      "taxes": [],
      "metadata": {}
    },
    {
      "id": 8,
      "object": "line_item",
      "catalog_item": "delivery",
      "type": "service",
      "name": "Delivery",
      "description": null,
      "quantity": 1,
      "unit_cost": 10,
      "amount": 10,
      "discountable": true,
      "discounts": [],
      "taxable": true,
      "taxes": [],
      "metadata": {}
    }
  ],
  "notes": null,
  "subtotal": 55,
  "discounts": [],
  "taxes": [
    {
      "id": 20554,
      "object": "tax",
      "amount": 3.85,
      "tax_rate": null
    }
  ],
  "total": 51.15,
  "balance": 51.15,
  "url": "https://dundermifflin.invoiced.com/credit_notes/IZmXbVOPyvfD3GPBmyd6FwXY",
  "pdf_url": "https://dundermifflin.invoiced.com/credit_notes/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
  "created_at": 1415229884,
  "metadata": {}
}
```

```python
<CreditNote id=2048 at 0x3fdbf95e4d08> JSON: {
  "id": 2048,
  "object": "credit_note",
  "customer": 15444,
  "invoice": 46225,
  "name": null,
  "currency": "usd",
  "draft": false,
  "closed": false,
  "paid": false,
  "status": "open",
  "number": "CN-0016",
  "date": 1416290400,
  "items": [
    {
      "id": 7,
      "object": "line_item",
      "catalog_item": null,
      "type": "product",
      "name": "Copy Paper, Case",
      "description": null,
      "quantity": 1,
      "unit_cost": 45,
      "amount": 45,
      "discountable": true,
      "discounts": [],
      "taxable": true,
      "taxes": [],
      "metadata": {}
    },
    {
      "id": 8,
      "object": "line_item",
      "catalog_item": "delivery",
      "type": "service",
      "name": "Delivery",
      "description": null,
      "quantity": 1,
      "unit_cost": 10,
      "amount": 10,
      "discountable": true,
      "discounts": [],
      "taxable": true,
      "taxes": [],
      "metadata": {}
    }
  ],
  "notes": null,
  "subtotal": 55,
  "discounts": [],
  "taxes": [
    {
      "id": 20554,
      "object": "tax",
      "amount": 3.85,
      "tax_rate": null
    }
  ],
  "total": 51.15,
  "balance": 51.15,
  "url": "https://dundermifflin.invoiced.com/credit_notes/IZmXbVOPyvfD3GPBmyd6FwXY",
  "pdf_url": "https://dundermifflin.invoiced.com/credit_notes/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
  "created_at": 1415229884,
  "metadata": {}
}
```

```java
com.invoiced.entity.CreditNote@e48fa2a JSON: {
  "id": 2048,
  "object": "credit_note",
  "customer": 15444,
  "invoice": 46225,
  "name": null,
  "currency": "usd",
  "draft": false,
  "closed": false,
  "paid": false,
  "status": "open",
  "number": "CN-0016",
  "date": 1416290400,
  "items": [
    {
      "id": 7,
      "object": "line_item",
      "catalog_item": null,
      "type": "product",
      "name": "Copy Paper, Case",
      "description": null,
      "quantity": 1,
      "unit_cost": 45,
      "amount": 45,
      "discountable": true,
      "discounts": [],
      "taxable": true,
      "taxes": [],
      "metadata": {}
    },
    {
      "id": 8,
      "object": "line_item",
      "catalog_item": "delivery",
      "type": "service",
      "name": "Delivery",
      "description": null,
      "quantity": 1,
      "unit_cost": 10,
      "amount": 10,
      "discountable": true,
      "discounts": [],
      "taxable": true,
      "taxes": [],
      "metadata": {}
    }
  ],
  "notes": null,
  "subtotal": 55,
  "discounts": [],
  "taxes": [
    {
      "id": 20554,
      "object": "tax",
      "amount": 3.85,
      "tax_rate": null
    }
  ],
  "total": 51.15,
  "balance": 51.15,
  "url": "https://dundermifflin.invoiced.com/credit_notes/IZmXbVOPyvfD3GPBmyd6FwXY",
  "pdf_url": "https://dundermifflin.invoiced.com/credit_notes/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
  "created_at": 1415229884,
  "metadata": {}
}
```

Parameter | Type | Description
--------- | ---- | -----------
**id** | *integer* | The credit note's unique ID
**object** | *string* | Object type, `credit_note`
**customer** | *integer* | Customer ID
**invoice** | *integer* | Invoice ID
**name** | *string* | Credit note name for internal use, defaults to "Credit Note"
**number** | *string* | The reference number assigned to the credit note for use in the dashboard
**currency** | *string* | [3-letter ISO code](https://en.wikipedia.org/wiki/ISO_4217)
**draft** | *boolean* | When false, the credit note is considered outstanding, or when true, the credit note is a draft
**closed** | *boolean* | When true, a credit note is closed and considered bad debt. No further payments are allowed.
**paid** | *boolean* | Indicates whether a credit note has been paid in full
**status** | *string* | Credit note state, one of `draft`, `open`, `paid`, `closed`
**date** | *timestamp* | Credit note date
**items** | *array* | Collection of Line Items
**notes** | *string* | Additional notes displayed on credit note
**subtotal** | *number* | Subtotal
**discounts** | *array* | Collection of Discounts
**taxes** | *array* | Collection of Taxes
**total** | *number* | Total
**balance** | *number* | Balance owed
**url** | *string* | URL to view the credit note in the billing portal
**pdf_url** | *string* | URL to download the credit note as a PDF
**created_at** | *timestamp* | Timestamp when created
**metadata** | *object* | A hash of key/value pairs that can store additional information about this object.

## Create a credit note

```shell
curl "https://api.invoiced.com/credit_notes" \
  -u {API_KEY}: \
  -d customer=15444 \
  -d invoice=46225 \
  -d items[0][name]="Copy paper, Case" \
  -d items[0][quantity]=1 \
  -d items[0][unit_cost]=45 \
  -d items[1][catalog_item]="delivery" \
  -d items[1][quantity]=1 \
  -d taxes[0][amount]=3.85
```

```ruby
invoiced.CreditNote.create(
  :customer => 15444,
  :invoice => 46225,
  :items => [
    {
      :name => "Copy paper, Case",
      :quantity => 1,
      :unit_cost => 45
    },
    {
      :catalog_item => "delivery",
      :quantity => 1
    }
  ],
  :taxes => [
    {
      :amount => 3.85
    }
  ]
)
```

```php
<?php

$creditNote = $invoiced->CreditNote->create([
  'customer' => 15444,
  'invoice' => 46225,
  'items' => [
    [
      'name' => "Copy paper, Case",
      'quantity' => 1,
      'unit_cost' => 45
    ],
    [
      'catalog_item' => "delivery",
      'quantity' => 1
    ]
  ],
  'taxes' => [
    [
      'amount' => 3.85
    ]
  ]
]);
```

```python
client.CreditNote.create(
  customer=15444,
  invoice=46225,
  items=[
    {
      'name': "Copy paper, Case",
      'quantity': 1,
      'unit_cost': 45
    },
    {
      'catalog_item': "delivery",
      'quantity': 1
    }
  ],
  taxes=[
    {
      'amount': 3.85
    }
  ]
)
```

```java
CreditNote creditNote = invoiced.newCreditNote();
creditNote.customer = 15444L;
creditNote.invoice = 46225L;
LineItem[] items = new LineItem[2];
items[0] = new LineItem();
items[0].name = "Copy paper, Case";
items[0].quantity = 1D;
items[0].unitCost = 45D;
items[1] = new LineItem();
items[1].catalogItem = "delivery";
items[1].quantity = 1D;
Tax[] taxes = new Tax[1];
taxes[0] = new Tax();
taxes[0].amount = 3.85D;
creditNote.items = items;
creditNote.taxes = taxes;
creditNote.create();
```

> The above command returns JSON structured like this:

```shell
{
  "id": 2048,
  "object": "credit_note",
  "customer": 15444,
  "invoice": 46225,
  "name": null,
  "currency": "usd",
  "draft": false,
  "closed": false,
  "paid": false,
  "status": "open",
  "number": "CN-0016",
  "date": 1416290400,
  "items": [
    {
      "id": 7,
      "object": "line_item",
      "catalog_item": null,
      "type": "product",
      "name": "Copy Paper, Case",
      "description": null,
      "quantity": 1,
      "unit_cost": 45,
      "amount": 45,
      "discountable": true,
      "discounts": [],
      "taxable": true,
      "taxes": [],
      "metadata": {}
    },
    {
      "id": 8,
      "object": "line_item",
      "catalog_item": "delivery",
      "type": "service",
      "name": "Delivery",
      "description": null,
      "quantity": 1,
      "unit_cost": 10,
      "amount": 10,
      "discountable": true,
      "discounts": [],
      "taxable": true,
      "taxes": [],
      "metadata": {}
    }
  ],
  "notes": null,
  "subtotal": 55,
  "discounts": [],
  "taxes": [
    {
      "id": 20554,
      "object": "tax",
      "amount": 3.85,
      "tax_rate": null
    }
  ],
  "total": 51.15,
  "balance": 51.15,
  "url": "https://dundermifflin.invoiced.com/credit_notes/IZmXbVOPyvfD3GPBmyd6FwXY",
  "pdf_url": "https://dundermifflin.invoiced.com/credit_notes/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
  "created_at": 1415229884,
  "metadata": {}
}
```

```ruby
#<Invoiced::CreditNote:0x3fdbf95e4d08 id=2048> JSON: {
  "id": 2048,
  "object": "credit_note",
  "customer": 15444,
  "invoice": 46225,
  "name": null,
  "currency": "usd",
  "draft": false,
  "closed": false,
  "paid": false,
  "status": "open",
  "number": "CN-0016",
  "date": 1416290400,
  "items": [
    {
      "id": 7,
      "object": "line_item",
      "catalog_item": null,
      "type": "product",
      "name": "Copy Paper, Case",
      "description": null,
      "quantity": 1,
      "unit_cost": 45,
      "amount": 45,
      "discountable": true,
      "discounts": [],
      "taxable": true,
      "taxes": [],
      "metadata": {}
    },
    {
      "id": 8,
      "object": "line_item",
      "catalog_item": "delivery",
      "type": "service",
      "name": "Delivery",
      "description": null,
      "quantity": 1,
      "unit_cost": 10,
      "amount": 10,
      "discountable": true,
      "discounts": [],
      "taxable": true,
      "taxes": [],
      "metadata": {}
    }
  ],
  "notes": null,
  "subtotal": 55,
  "discounts": [],
  "taxes": [
    {
      "id": 20554,
      "object": "tax",
      "amount": 3.85,
      "tax_rate": null
    }
  ],
  "total": 51.15,
  "balance": 51.15,
  "url": "https://dundermifflin.invoiced.com/credit_notes/IZmXbVOPyvfD3GPBmyd6FwXY",
  "pdf_url": "https://dundermifflin.invoiced.com/credit_notes/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
  "created_at": 1415229884,
  "metadata": {}
}
```

```php
Invoiced\CreditNote JSON: {
  "id": 2048,
  "object": "credit_note",
  "customer": 15444,
  "invoice": 46225,
  "name": null,
  "currency": "usd",
  "draft": false,
  "closed": false,
  "paid": false,
  "status": "open",
  "number": "CN-0016",
  "date": 1416290400,
  "items": [
    {
      "id": 7,
      "object": "line_item",
      "catalog_item": null,
      "type": "product",
      "name": "Copy Paper, Case",
      "description": null,
      "quantity": 1,
      "unit_cost": 45,
      "amount": 45,
      "discountable": true,
      "discounts": [],
      "taxable": true,
      "taxes": [],
      "metadata": {}
    },
    {
      "id": 8,
      "object": "line_item",
      "catalog_item": "delivery",
      "type": "service",
      "name": "Delivery",
      "description": null,
      "quantity": 1,
      "unit_cost": 10,
      "amount": 10,
      "discountable": true,
      "discounts": [],
      "taxable": true,
      "taxes": [],
      "metadata": {}
    }
  ],
  "notes": null,
  "subtotal": 55,
  "discounts": [],
  "taxes": [
    {
      "id": 20554,
      "object": "tax",
      "amount": 3.85,
      "tax_rate": null
    }
  ],
  "total": 51.15,
  "balance": 51.15,
  "url": "https://dundermifflin.invoiced.com/credit_notes/IZmXbVOPyvfD3GPBmyd6FwXY",
  "pdf_url": "https://dundermifflin.invoiced.com/credit_notes/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
  "created_at": 1415229884,
  "metadata": {}
}
```

```python
<CreditNote id=2048 at 0x3fdbf95e4d08> JSON: {
  "id": 2048,
  "object": "credit_note",
  "customer": 15444,
  "invoice": 46225,
  "name": null,
  "currency": "usd",
  "draft": false,
  "closed": false,
  "paid": false,
  "status": "open",
  "number": "CN-0016",
  "date": 1416290400,
  "items": [
    {
      "id": 7,
      "object": "line_item",
      "catalog_item": null,
      "type": "product",
      "name": "Copy Paper, Case",
      "description": null,
      "quantity": 1,
      "unit_cost": 45,
      "amount": 45,
      "discountable": true,
      "discounts": [],
      "taxable": true,
      "taxes": [],
      "metadata": {}
    },
    {
      "id": 8,
      "object": "line_item",
      "catalog_item": "delivery",
      "type": "service",
      "name": "Delivery",
      "description": null,
      "quantity": 1,
      "unit_cost": 10,
      "amount": 10,
      "discountable": true,
      "discounts": [],
      "taxable": true,
      "taxes": [],
      "metadata": {}
    }
  ],
  "notes": null,
  "subtotal": 55,
  "discounts": [],
  "taxes": [
    {
      "id": 20554,
      "object": "tax",
      "amount": 3.85,
      "tax_rate": null
    }
  ],
  "total": 51.15,
  "balance": 51.15,
  "url": "https://dundermifflin.invoiced.com/credit_notes/IZmXbVOPyvfD3GPBmyd6FwXY",
  "pdf_url": "https://dundermifflin.invoiced.com/credit_notes/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
  "created_at": 1415229884,
  "metadata": {}
}
```

```java
com.invoiced.entity.CreditNote@e48fa2a JSON: {
  "id": 2048,
  "object": "credit_note",
  "customer": 15444,
  "invoice": 46225,
  "name": null,
  "currency": "usd",
  "draft": false,
  "closed": false,
  "paid": false,
  "status": "open",
  "number": "CN-0016",
  "date": 1416290400,
  "items": [
    {
      "id": 7,
      "object": "line_item",
      "catalog_item": null,
      "type": "product",
      "name": "Copy Paper, Case",
      "description": null,
      "quantity": 1,
      "unit_cost": 45,
      "amount": 45,
      "discountable": true,
      "discounts": [],
      "taxable": true,
      "taxes": [],
      "metadata": {}
    },
    {
      "id": 8,
      "object": "line_item",
      "catalog_item": "delivery",
      "type": "service",
      "name": "Delivery",
      "description": null,
      "quantity": 1,
      "unit_cost": 10,
      "amount": 10,
      "discountable": true,
      "discounts": [],
      "taxable": true,
      "taxes": [],
      "metadata": {}
    }
  ],
  "notes": null,
  "subtotal": 55,
  "discounts": [],
  "taxes": [
    {
      "id": 20554,
      "object": "tax",
      "amount": 3.85,
      "tax_rate": null
    }
  ],
  "total": 51.15,
  "balance": 51.15,
  "url": "https://dundermifflin.invoiced.com/credit_notes/IZmXbVOPyvfD3GPBmyd6FwXY",
  "pdf_url": "https://dundermifflin.invoiced.com/credit_notes/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
  "created_at": 1415229884,
  "metadata": {}
}
```

Create a new credit note with this endpoint.

### HTTP Request

`POST /credit_notes`

### Attributes

Parameter | Type | Description
--------- | ---- | -----------
**customer** | *integer* | Customer ID - **required**
**invoice** | *integer* | Invoice ID
**name** | *string* | Credit note name for internal use, defaults to "Credit Note"
**number** | *string* | The reference number assigned to the credit note, defaults to next # in auto-numbering sequence
**currency** | *string* | [3-letter ISO code](https://en.wikipedia.org/wiki/ISO_4217) - defaults to account currency
**date** | *timestamp* | Credit note date - defaults to current timestamp
**draft** | *boolean* | When false, the credit note is considered outstanding, or when true, the credit note is a draft
**closed** | *boolean* | Marks a credit note as closed
**items** | *array* | Collection of Line Items
**notes** | *string* | Additional notes displayed on credit note
**discounts** | *array* | Collection of Discounts
**taxes** | *array* | Collection of Taxes
**metadata** | *object* | A hash of key/value pairs that can store additional information about this object.
**attachments** | *array* | A list of [File](#file-object) IDs to attach to the credit note

## Retrieve a credit note

```shell
curl "https://api.invoiced.com/credit_notes/:id" \
  -u {API_KEY}:
```

```ruby
creditNote = invoiced.CreditNote.retrieve("{CNOICE_ID}")
```

```php
<?php

$creditNote = $invoiced->CreditNote->retrieve("{CNOICE_ID}");
```

```python
creditNote = client.CreditNote.retrieve("{CNOICE_ID}")
```

```java
CreditNote creditNote = invoiced.newCreditNote().retrieve({CNOICE_ID});
```

> The above command returns JSON structured like this:

```shell
{
  "id": 2048,
  "object": "credit_note",
  "customer": 15444,
  "invoice": 46225,
  "name": null,
  "currency": "usd",
  "draft": false,
  "closed": false,
  "paid": false,
  "status": "open",
  "number": "CN-0016",
  "date": 1416290400,
  "items": [
    {
      "id": 7,
      "object": "line_item",
      "catalog_item": null,
      "type": "product",
      "name": "Copy Paper, Case",
      "description": null,
      "quantity": 1,
      "unit_cost": 45,
      "amount": 45,
      "discountable": true,
      "discounts": [],
      "taxable": true,
      "taxes": [],
      "metadata": {}
    },
    {
      "id": 8,
      "object": "line_item",
      "catalog_item": "delivery",
      "type": "service",
      "name": "Delivery",
      "description": null,
      "quantity": 1,
      "unit_cost": 10,
      "amount": 10,
      "discountable": true,
      "discounts": [],
      "taxable": true,
      "taxes": [],
      "metadata": {}
    }
  ],
  "notes": null,
  "subtotal": 55,
  "discounts": [],
  "taxes": [
    {
      "id": 20554,
      "object": "tax",
      "amount": 3.85,
      "tax_rate": null
    }
  ],
  "total": 51.15,
  "balance": 51.15,
  "url": "https://dundermifflin.invoiced.com/credit_notes/IZmXbVOPyvfD3GPBmyd6FwXY",
  "pdf_url": "https://dundermifflin.invoiced.com/credit_notes/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
  "created_at": 1415229884,
  "metadata": {}
}
```

```ruby
#<Invoiced::CreditNote:0x3fdbf95e4d08 id=2048> JSON: {
  "id": 2048,
  "object": "credit_note",
  "customer": 15444,
  "invoice": 46225,
  "name": null,
  "currency": "usd",
  "draft": false,
  "closed": false,
  "paid": false,
  "status": "open",
  "number": "CN-0016",
  "date": 1416290400,
  "items": [
    {
      "id": 7,
      "object": "line_item",
      "catalog_item": null,
      "type": "product",
      "name": "Copy Paper, Case",
      "description": null,
      "quantity": 1,
      "unit_cost": 45,
      "amount": 45,
      "discountable": true,
      "discounts": [],
      "taxable": true,
      "taxes": [],
      "metadata": {}
    },
    {
      "id": 8,
      "object": "line_item",
      "catalog_item": "delivery",
      "type": "service",
      "name": "Delivery",
      "description": null,
      "quantity": 1,
      "unit_cost": 10,
      "amount": 10,
      "discountable": true,
      "discounts": [],
      "taxable": true,
      "taxes": [],
      "metadata": {}
    }
  ],
  "notes": null,
  "subtotal": 55,
  "discounts": [],
  "taxes": [
    {
      "id": 20554,
      "object": "tax",
      "amount": 3.85,
      "tax_rate": null
    }
  ],
  "total": 51.15,
  "balance": 51.15,
  "url": "https://dundermifflin.invoiced.com/credit_notes/IZmXbVOPyvfD3GPBmyd6FwXY",
  "pdf_url": "https://dundermifflin.invoiced.com/credit_notes/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
  "created_at": 1415229884,
  "metadata": {}
}
```

```php
Invoiced\CreditNote JSON: {
  "id": 2048,
  "object": "credit_note",
  "customer": 15444,
  "invoice": 46225,
  "name": null,
  "currency": "usd",
  "draft": false,
  "closed": false,
  "paid": false,
  "status": "open",
  "number": "CN-0016",
  "date": 1416290400,
  "items": [
    {
      "id": 7,
      "object": "line_item",
      "catalog_item": null,
      "type": "product",
      "name": "Copy Paper, Case",
      "description": null,
      "quantity": 1,
      "unit_cost": 45,
      "amount": 45,
      "discountable": true,
      "discounts": [],
      "taxable": true,
      "taxes": [],
      "metadata": {}
    },
    {
      "id": 8,
      "object": "line_item",
      "catalog_item": "delivery",
      "type": "service",
      "name": "Delivery",
      "description": null,
      "quantity": 1,
      "unit_cost": 10,
      "amount": 10,
      "discountable": true,
      "discounts": [],
      "taxable": true,
      "taxes": [],
      "metadata": {}
    }
  ],
  "notes": null,
  "subtotal": 55,
  "discounts": [],
  "taxes": [
    {
      "id": 20554,
      "object": "tax",
      "amount": 3.85,
      "tax_rate": null
    }
  ],
  "total": 51.15,
  "balance": 51.15,
  "url": "https://dundermifflin.invoiced.com/credit_notes/IZmXbVOPyvfD3GPBmyd6FwXY",
  "pdf_url": "https://dundermifflin.invoiced.com/credit_notes/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
  "created_at": 1415229884,
  "metadata": {}
}
```

```python
<CreditNote id=2048 at 0x3fdbf95e4d08> JSON: {
  "id": 2048,
  "object": "credit_note",
  "customer": 15444,
  "invoice": 46225,
  "name": null,
  "currency": "usd",
  "draft": false,
  "closed": false,
  "paid": false,
  "status": "open",
  "number": "CN-0016",
  "date": 1416290400,
  "items": [
    {
      "id": 7,
      "object": "line_item",
      "catalog_item": null,
      "type": "product",
      "name": "Copy Paper, Case",
      "description": null,
      "quantity": 1,
      "unit_cost": 45,
      "amount": 45,
      "discountable": true,
      "discounts": [],
      "taxable": true,
      "taxes": [],
      "metadata": {}
    },
    {
      "id": 8,
      "object": "line_item",
      "catalog_item": "delivery",
      "type": "service",
      "name": "Delivery",
      "description": null,
      "quantity": 1,
      "unit_cost": 10,
      "amount": 10,
      "discountable": true,
      "discounts": [],
      "taxable": true,
      "taxes": [],
      "metadata": {}
    }
  ],
  "notes": null,
  "subtotal": 55,
  "discounts": [],
  "taxes": [
    {
      "id": 20554,
      "object": "tax",
      "amount": 3.85,
      "tax_rate": null
    }
  ],
  "total": 51.15,
  "balance": 51.15,
  "url": "https://dundermifflin.invoiced.com/credit_notes/IZmXbVOPyvfD3GPBmyd6FwXY",
  "pdf_url": "https://dundermifflin.invoiced.com/credit_notes/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
  "created_at": 1415229884,
  "metadata": {}
}
```

```java
com.invoiced.entity.CreditNote@e48fa2a JSON: {
  "id": 2048,
  "object": "credit_note",
  "customer": 15444,
  "invoice": 46225,
  "name": null,
  "currency": "usd",
  "draft": false,
  "closed": false,
  "paid": false,
  "status": "open",
  "number": "CN-0016",
  "date": 1416290400,
  "items": [
    {
      "id": 7,
      "object": "line_item",
      "catalog_item": null,
      "type": "product",
      "name": "Copy Paper, Case",
      "description": null,
      "quantity": 1,
      "unit_cost": 45,
      "amount": 45,
      "discountable": true,
      "discounts": [],
      "taxable": true,
      "taxes": [],
      "metadata": {}
    },
    {
      "id": 8,
      "object": "line_item",
      "catalog_item": "delivery",
      "type": "service",
      "name": "Delivery",
      "description": null,
      "quantity": 1,
      "unit_cost": 10,
      "amount": 10,
      "discountable": true,
      "discounts": [],
      "taxable": true,
      "taxes": [],
      "metadata": {}
    }
  ],
  "notes": null,
  "subtotal": 55,
  "discounts": [],
  "taxes": [
    {
      "id": 20554,
      "object": "tax",
      "amount": 3.85,
      "tax_rate": null
    }
  ],
  "total": 51.15,
  "balance": 51.15,
  "url": "https://dundermifflin.invoiced.com/credit_notes/IZmXbVOPyvfD3GPBmyd6FwXY",
  "pdf_url": "https://dundermifflin.invoiced.com/credit_notes/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
  "created_at": 1415229884,
  "metadata": {}
}
```

This endpoint retrieves a specific credit note.

### HTTP Request

`GET /credit_notes/:id`

### Query Parameters

Parameter | Type | Description
--------- | ---- | -----------
**expand** | *string* | Properties to expand

## Update a credit note

```shell
curl "https://api.invoiced.com/credit_notes/:id" \
  -u {API_KEY}: \
  -X PATCH \
  -d sent=1 \
  -d chase=1
```

```ruby
creditNote.name = "July Paper Delivery"
creditNote.notes = "The order was delivered on Jul 20, 2015"
creditNote.sent = true
creditNote.save
```

```php
<?php

$creditNote->name = "July Paper Delivery";
$creditNote->notes = "The order was delivered on Jul 20, 2015";
$creditNote->sent = true;
$creditNote->save();
```

```python
creditNote.name = "July Paper Delivery"
creditNote.notes = "The order was delivered on Jul 20, 2015"
creditNote.sent = True
creditNote.save()
```

```java
creditNote.name =  "July Paper Delivery";
creditNote.notes = "The order was delivered on Jul 20, 2015";
creditNote.sent = true;
creditNote.save();
```

> The above command returns JSON structured like this:

```shell
{
  "id": 2048,
  "object": "credit_note",
  "customer": 15444,
  "invoice": 46225,
  "name": "July Paper Delivery",
  "currency": "usd",
  "draft": false,
  "closed": false,
  "paid": false,
  "status": "sent",
  "number": "CN-0016",
  "date": 1416290400,
  "items": [
    {
      "id": 7,
      "object": "line_item",
      "catalog_item": null,
      "type": "product",
      "name": "Copy Paper, Case",
      "description": null,
      "quantity": 1,
      "unit_cost": 45,
      "amount": 45,
      "discountable": true,
      "discounts": [],
      "taxable": true,
      "taxes": [],
      "metadata": {}
    },
    {
      "id": 8,
      "object": "line_item",
      "catalog_item": "delivery",
      "type": "service",
      "name": "Delivery",
      "description": null,
      "quantity": 1,
      "unit_cost": 10,
      "amount": 10,
      "discountable": true,
      "discounts": [],
      "taxable": true,
      "taxes": [],
      "metadata": {}
    }
  ],
  "notes": "The order was delivered on Jul 20, 2015",
  "subtotal": 55,
  "discounts": [],
  "taxes": [
    {
      "id": 20554,
      "object": "tax",
      "amount": 3.85,
      "tax_rate": null
    }
  ],
  "total": 51.15,
  "balance": 51.15,
  "url": "https://dundermifflin.invoiced.com/credit_notes/IZmXbVOPyvfD3GPBmyd6FwXY",
  "pdf_url": "https://dundermifflin.invoiced.com/credit_notes/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
  "created_at": 1415229884,
  "metadata": {}
}
```

```ruby
#<Invoiced::CreditNote:0x3fdbf95e4d08 id=2048> JSON: {
  "id": 2048,
  "object": "credit_note",
  "customer": 15444,
  "invoice": 46225,
  "name": "July Paper Delivery",
  "currency": "usd",
  "draft": false,
  "closed": false,
  "paid": false,
  "status": "sent",
  "number": "CN-0016",
  "date": 1416290400,
  "items": [
    {
      "id": 7,
      "object": "line_item",
      "catalog_item": null,
      "type": "product",
      "name": "Copy Paper, Case",
      "description": null,
      "quantity": 1,
      "unit_cost": 45,
      "amount": 45,
      "discountable": true,
      "discounts": [],
      "taxable": true,
      "taxes": [],
      "metadata": {}
    },
    {
      "id": 8,
      "object": "line_item",
      "catalog_item": "delivery",
      "type": "service",
      "name": "Delivery",
      "description": null,
      "quantity": 1,
      "unit_cost": 10,
      "amount": 10,
      "discountable": true,
      "discounts": [],
      "taxable": true,
      "taxes": [],
      "metadata": {}
    }
  ],
  "notes": "The order was delivered on Jul 20, 2015",
  "subtotal": 55,
  "discounts": [],
  "taxes": [
    {
      "id": 20554,
      "object": "tax",
      "amount": 3.85,
      "tax_rate": null
    }
  ],
  "total": 51.15,
  "balance": 51.15,
  "url": "https://dundermifflin.invoiced.com/credit_notes/IZmXbVOPyvfD3GPBmyd6FwXY",
  "pdf_url": "https://dundermifflin.invoiced.com/credit_notes/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
  "created_at": 1415229884,
  "metadata": {}
}
```

```php
Invoiced\CreditNote JSON: {
  "id": 2048,
  "object": "credit_note",
  "customer": 15444,
  "invoice": 46225,
  "name": "July Paper Delivery",
  "currency": "usd",
  "draft": false,
  "closed": false,
  "paid": false,
  "status": "sent",
  "number": "CN-0016",
  "date": 1416290400,
  "items": [
    {
      "id": 7,
      "object": "line_item",
      "catalog_item": null,
      "type": "product",
      "name": "Copy Paper, Case",
      "description": null,
      "quantity": 1,
      "unit_cost": 45,
      "amount": 45,
      "discountable": true,
      "discounts": [],
      "taxable": true,
      "taxes": [],
      "metadata": {}
    },
    {
      "id": 8,
      "object": "line_item",
      "catalog_item": "delivery",
      "type": "service",
      "name": "Delivery",
      "description": null,
      "quantity": 1,
      "unit_cost": 10,
      "amount": 10,
      "discountable": true,
      "discounts": [],
      "taxable": true,
      "taxes": [],
      "metadata": {}
    }
  ],
  "notes": "The order was delivered on Jul 20, 2015",
  "subtotal": 55,
  "discounts": [],
  "taxes": [
    {
      "id": 20554,
      "object": "tax",
      "amount": 3.85,
      "tax_rate": null
    }
  ],
  "total": 51.15,
  "balance": 51.15,
  "url": "https://dundermifflin.invoiced.com/credit_notes/IZmXbVOPyvfD3GPBmyd6FwXY",
  "pdf_url": "https://dundermifflin.invoiced.com/credit_notes/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
  "created_at": 1415229884,
  "metadata": {}
}
```

```python
<CreditNote id=2048 at 0x3fdbf95e4d08> JSON: {
  "id": 2048,
  "object": "credit_note",
  "customer": 15444,
  "invoice": 46225,
  "name": "July Paper Delivery",
  "currency": "usd",
  "draft": false,
  "closed": false,
  "paid": false,
  "status": "sent",
  "number": "CN-0016",
  "date": 1416290400,
  "items": [
    {
      "id": 7,
      "object": "line_item",
      "catalog_item": null,
      "type": "product",
      "name": "Copy Paper, Case",
      "description": null,
      "quantity": 1,
      "unit_cost": 45,
      "amount": 45,
      "discountable": true,
      "discounts": [],
      "taxable": true,
      "taxes": [],
      "metadata": {}
    },
    {
      "id": 8,
      "object": "line_item",
      "catalog_item": "delivery",
      "type": "service",
      "name": "Delivery",
      "description": null,
      "quantity": 1,
      "unit_cost": 10,
      "amount": 10,
      "discountable": true,
      "discounts": [],
      "taxable": true,
      "taxes": [],
      "metadata": {}
    }
  ],
  "notes": "The order was delivered on Jul 20, 2015",
  "subtotal": 55,
  "discounts": [],
  "taxes": [
    {
      "id": 20554,
      "object": "tax",
      "amount": 3.85,
      "tax_rate": null
    }
  ],
  "total": 51.15,
  "balance": 51.15,
  "url": "https://dundermifflin.invoiced.com/credit_notes/IZmXbVOPyvfD3GPBmyd6FwXY",
  "pdf_url": "https://dundermifflin.invoiced.com/credit_notes/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
  "created_at": 1415229884,
  "metadata": {}
}
```

```java
com.invoiced.entity.CreditNote@e48fa2a JSON: {
  "id": 2048,
  "object": "credit_note",
  "customer": 15444,
  "invoice": 46225,
  "name": "July Paper Delivery",
  "currency": "usd",
  "draft": false,
  "closed": false,
  "paid": false,
  "status": "sent",
  "number": "CN-0016",
  "date": 1416290400,
  "items": [
    {
      "id": 7,
      "object": "line_item",
      "catalog_item": null,
      "type": "product",
      "name": "Copy Paper, Case",
      "description": null,
      "quantity": 1,
      "unit_cost": 45,
      "amount": 45,
      "discountable": true,
      "discounts": [],
      "taxable": true,
      "taxes": [],
      "metadata": {}
    },
    {
      "id": 8,
      "object": "line_item",
      "catalog_item": "delivery",
      "type": "service",
      "name": "Delivery",
      "description": null,
      "quantity": 1,
      "unit_cost": 10,
      "amount": 10,
      "discountable": true,
      "discounts": [],
      "taxable": true,
      "taxes": [],
      "metadata": {}
    }
  ],
  "notes": "The order was delivered on Jul 20, 2015",
  "subtotal": 55,
  "discounts": [],
  "taxes": [
    {
      "id": 20554,
      "object": "tax",
      "amount": 3.85,
      "tax_rate": null
    }
  ],
  "total": 51.15,
  "balance": 51.15,
  "url": "https://dundermifflin.invoiced.com/credit_notes/IZmXbVOPyvfD3GPBmyd6FwXY",
  "pdf_url": "https://dundermifflin.invoiced.com/credit_notes/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
  "created_at": 1415229884,
  "metadata": {}
}
```

Use this endpoint to update a credit note.

### HTTP Request

`PATCH /credit_notes/:id`

### Attributes

Parameter | Type | Description
--------- | ---- | -----------
**name** | *string* | Credit note name for internal use, defaults to "Credit Note"
**number** | *string* | The reference number assigned to the credit note, defaults to next # in auto-numbering sequence
**currency** | *string* | [3-letter ISO code](https://en.wikipedia.org/wiki/ISO_4217) - defaults to account currency
**date** | *timestamp* | Credit note date - defaults to current timestamp
**draft** | *boolean* | When false, the credit note is considered outstanding, or when true, the invoice is a draft
**closed** | *boolean* | Marks a credit note as closed
**items** | *array* | Collection of Line Items
**notes** | *string* | Additional notes displayed on credit note
**discounts** | *array* | Collection of Discounts
**taxes** | *array* | Collection of Taxes
**metadata** | *object* | A hash of key/value pairs that can store additional information about this object.
**attachments** | *array* | A list of [File](#file-object) IDs to attach to the credit note. Replaces existing attachments. Not providing this keeps existing attachments.

## Send a credit note

```shell
curl "https://api.invoiced.com/credit_notes/:id/emails" \
  -u {API_KEY}: \
  -X POST
```

```ruby
emails = creditNote.send
```

```php
<?php

$emails = $creditNote->send();
```

```python
emails = creditNote.send()
```

```java
EmailRequest emailRequest = new EmailRequest();
EmailRecipient[] emailRecipients = new EmailRecipient[1];
emailRecipients[0] = new EmailRecipient();
emailRecipients[0].name = "Client";
emailRecipients[0].email = "client@example.com";

emailRequest.to = emailRecipients;
emailRequest.subject = "New Credit Note from Dunder Mifflin, Inc.: CN-0016";
emailRequest.message = "Dear Client, a new credite note for $51.15 has been created on your account. Thank you!";

Email[] emails = creditNote.send(emailRequest);
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
    "template": "credit_note_email",
    "subject": "New Credit Note from Dunder Mifflin, Inc.: CN-0016",
    "message": "Dear Client, a new credit note for $51.15 has been created on your account. Thank you!",
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
    "template": "credit_note_email",
    "subject": "New Credit Note from Dunder Mifflin, Inc.: CN-0016",
    "message": "Dear Client, a new credit note for $51.15 has been created on your account. Thank you!",
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
    "template": "credit_note_email",
    "subject": "New Credit Note from Dunder Mifflin, Inc.: CN-0016",
    "message": "Dear Client, a new credit note for $51.15 has been created on your account. Thank you!",
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
    "template": "credit_note_email",
    "subject": "New Credit Note from Dunder Mifflin, Inc.: CN-0016",
    "message": "Dear Client, a new credit note for $51.15 has been created on your account. Thank you!",
    "opens": 0,
    "opens_detail": [],
    "created_at": 1436890047
  },
  <Email id=f45382c6fbc44d44aa7f9a55eb2ce731 at 0x3fdbf95e4d08> JSON: { ... },
  <Email id=f45382c6fbc44d44aa7f9a55eb2ce731 at 0x3fdbf95e4d08> JSON: { ... }
]
```

```java
[
  com.invoiced.entity.Email@2ce1cfd8 JSON: {
    "id": "f45382c6fbc44d44aa7f9a55eb2ce731",
    "object": "email",
    "state": "sent",
    "reject_reason": null,
    "email": "client@example.com",
    "template": "credit_note_email",
    "subject": "New Credit Note from Dunder Mifflin, Inc.: CN-0016",
    "message": "Dear Client, a new credit note for $51.15 has been created on your account. Thank you!",
    "opens": 0,
    "opens_detail": [],
    "created_at": 1436890047
  },
  com.invoiced.entity.Email@3ce1cfd8 JSON: {...},
  com.invoiced.entity.Email@4ce1cfd8 JSON: {...}
]
```

This endpoint sends a credit note to your customer.

### HTTP Request

`POST /credit_notes/:id/emails`

### Request Parameters

Parameter | Type | Description
--------- | ---- | -----------
**to** | *array* | Optional array of recipients like:<br/>`[{"name": "Client", "email": "client@example.com"}]`
**bcc** | *string* | Optional comma-separated list of email addresses to be blind carbon copied
**subject** | *string* | Optional subject
**message** | *string* | Optional message body, otherwise the appropriate credit note template is used

<aside class="info">
A successful response means that your email has been added to the send queue.
</aside>

## List credit note attachments

```shell
curl "https://api.invoiced.com/credit_notes/:id/attachments" \
  -u {API_KEY}:
```

```ruby
attachments, metadata = creditNote.attachments
```

```php
<?php

list($attachments, $metadata) = $creditNote->attachments();
```

```python
attachments, metadata = creditNote.attachments()
```

```java
Attachment[] attachments = creditNote.listAttachments();
```

> The above command returns JSON structured like this:

```shell
[
  {
    "id": 13,
    "object": "attachment",
    "file": {
      "id": 13,
      "object": "file",
      "name": "logo-invoice.png",
      "size": 6936,
      "type": "image/png",
      "url": "https://invoiced.com/img/logo-invoice.png",
      "created_at": 1464625855
    },
    "created_at": 1464625855
  }
]
```

```ruby
[
  #<Invoiced::Attachment:0x3ff10dd39db4 id=13> JSON: {
    "id": 13,
    "object": "attachment",
    "file": {
      "id": 13,
      "object": "file",
      "name": "logo-invoice.png",
      "size": 6936,
      "type": "image/png",
      "url": "https://invoiced.com/img/logo-invoice.png",
      "created_at": 1464625855
    },
    "created_at": 1464625855
  }
]
```

```php
[
  Invoiced\Attachment JSON: {
    "id": 13,
    "object": "attachment",
    "file": {
      "id": 13,
      "object": "file",
      "name": "logo-invoice.png",
      "size": 6936,
      "type": "image/png",
      "url": "https://invoiced.com/img/logo-invoice.png",
      "created_at": 1464625855
    },
    "created_at": 1464625855
  }
]
```

```python
[
  <Attachment id=13 at 0x3ff10dd39db4> JSON: {
    "id": 13,
    "object": "attachment",
    "file": {
      "id": 13,
      "object": "file",
      "name": "logo-invoice.png",
      "size": 6936,
      "type": "image/png",
      "url": "https://invoiced.com/img/logo-invoice.png",
      "created_at": 1464625855
    },
    "created_at": 1464625855
  }
]
```

```java
[
  com.invoiced.entity.Attachment@1759eafd JSON: {
    "id": 13,
    "object": "attachment",
    "file": {
      "id": 13,
      "object": "file",
      "name": "logo-invoice.png",
      "size": 6936,
      "type": "image/png",
      "url": "https://invoiced.com/img/logo-invoice.png",
      "created_at": 1464625855
    },
    "created_at": 1464625855
  },
  com.invoiced.entity.Attachment@1759eafd JSON: {...},
  com.invoiced.entity.Attachment@1759eafd JSON: {...}
]
```

This endpoint retrieves a list of files attached to a specific credit note.

### HTTP Request

`GET /credit_notes/:id/attachments`

## Delete a credit note

```shell
curl "https://api.invoiced.com/credit_notes/:id" \
  -u {API_KEY}: \
  -X DELETE
```

```ruby
creditNote.delete
```

```php
<?php

$creditNote->delete();
```

```python
creditNote.delete()
```

```java
creditNote.delete();
```

> The above command returns `204 No Content`

This endpoint deletes a specific credit note.

### HTTP Request

`DELETE /credit_notes/:id`

## List all credit notes

```shell
curl "https://api.invoiced.com/credit_notes" \
  -u {API_KEY}:
```

```ruby
creditNotes, metadata = invoiced.CreditNote.list(:per_page => 3)
```

```php
<?php

list($creditNotes, $metadata) = $invoiced->CreditNote->all(['per_page' => 3]);
```

```python
creditNotes, metadata = invoiced.CreditNote.list(per_page=3)
```

```java
EntityList<CreditNote> creditNotes = conn.newCreditNote().listAll();
```

> The above command returns JSON structured like this:

```shell
[
  {
    "id": 2048,
    "object": "credit_note",
    "customer": 15444,
    "invoice": 46225,
    "name": null,
    "currency": "usd",
    "draft": false,
    "closed": false,
    "paid": false,
    "status": "open",
    "number": "CN-0016",
    "date": 1416290400,
    "items": [
      {
        "id": 7,
        "object": "line_item",
        "catalog_item": null,
        "type": "product",
        "name": "Copy Paper, Case",
        "description": null,
        "quantity": 1,
        "unit_cost": 45,
        "amount": 45,
        "discountable": true,
        "discounts": [],
        "taxable": true,
        "taxes": [],
        "metadata": {}
      },
      {
        "id": 8,
        "object": "line_item",
        "catalog_item": "delivery",
        "type": "service",
        "name": "Delivery",
        "description": null,
        "quantity": 1,
        "unit_cost": 10,
        "amount": 10,
        "discountable": true,
        "discounts": [],
        "taxable": true,
        "taxes": [],
        "metadata": {}
      }
    ],
    "notes": null,
    "subtotal": 55,
    "discounts": [],
    "taxes": [
      {
        "id": 20554,
        "object": "tax",
        "amount": 3.85,
        "tax_rate": null
      }
    ],
    "total": 51.15,
    "balance": 51.15,
    "url": "https://dundermifflin.invoiced.com/credit_notes/IZmXbVOPyvfD3GPBmyd6FwXY",
    "pdf_url": "https://dundermifflin.invoiced.com/credit_notes/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
    "created_at": 1415229884,
    "metadata": {}
  },
  { ... },
  { ... }
]
```

```ruby
[
  #<Invoiced::CreditNote:0x3fdbf95e4d08 id=2048> JSON: {
    "id": 2048,
    "object": "credit_note",
    "customer": 15444,
    "invoice": 46225,
    "name": null,
    "currency": "usd",
    "draft": false,
    "closed": false,
    "paid": false,
    "status": "open",
    "number": "CN-0016",
    "date": 1416290400,
    "items": [
      {
        "id": 7,
        "object": "line_item",
        "catalog_item": null,
        "type": "product",
        "name": "Copy Paper, Case",
        "description": null,
        "quantity": 1,
        "unit_cost": 45,
        "amount": 45,
        "discountable": true,
        "discounts": [],
        "taxable": true,
        "taxes": [],
        "metadata": {}
      },
      {
        "id": 8,
        "object": "line_item",
        "catalog_item": "delivery",
        "type": "service",
        "name": "Delivery",
        "description": null,
        "quantity": 1,
        "unit_cost": 10,
        "amount": 10,
        "discountable": true,
        "discounts": [],
        "taxable": true,
        "taxes": [],
        "metadata": {}
      }
    ],
    "notes": null,
    "subtotal": 55,
    "discounts": [],
    "taxes": [
      {
        "id": 20554,
        "object": "tax",
        "amount": 3.85,
        "tax_rate": null
      }
    ],
    "total": 51.15,
    "balance": 51.15,
    "url": "https://dundermifflin.invoiced.com/credit_notes/IZmXbVOPyvfD3GPBmyd6FwXY",
    "pdf_url": "https://dundermifflin.invoiced.com/credit_notes/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
    "created_at": 1415229884,
    "metadata": {}
  },
  #<Invoiced::CreditNote:0x3fdbf95e4d09 id=15445> JSON: { ... },
  #<Invoiced::CreditNote:0x3fdbf95e4d10 id=15446> JSON: { ... }
]
```

```php
[
  Invoiced\CreditNote JSON: {
    "id": 2048,
    "object": "credit_note",
    "customer": 15444,
    "invoice": 46225,
    "name": null,
    "currency": "usd",
    "draft": false,
    "closed": false,
    "paid": false,
    "status": "open",
    "number": "CN-0016",
    "date": 1416290400,
    "items": [
      {
        "id": 7,
        "object": "line_item",
        "catalog_item": null,
        "type": "product",
        "name": "Copy Paper, Case",
        "description": null,
        "quantity": 1,
        "unit_cost": 45,
        "amount": 45,
        "discountable": true,
        "discounts": [],
        "taxable": true,
        "taxes": [],
        "metadata": {}
      },
      {
        "id": 8,
        "object": "line_item",
        "catalog_item": "delivery",
        "type": "service",
        "name": "Delivery",
        "description": null,
        "quantity": 1,
        "unit_cost": 10,
        "amount": 10,
        "discountable": true,
        "discounts": [],
        "taxable": true,
        "taxes": [],
        "metadata": {}
      }
    ],
    "notes": null,
    "subtotal": 55,
    "discounts": [],
    "taxes": [
      {
        "id": 20554,
        "object": "tax",
        "amount": 3.85,
        "tax_rate": null
      }
    ],
    "total": 51.15,
    "balance": 51.15,
    "url": "https://dundermifflin.invoiced.com/credit_notes/IZmXbVOPyvfD3GPBmyd6FwXY",
    "pdf_url": "https://dundermifflin.invoiced.com/credit_notes/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
    "created_at": 1415229884,
    "metadata": {}
  },
  Invoiced\CreditNote JSON: { ... },
  Invoiced\CreditNote JSON: { ... }
]
```

```python
[
  <CreditNote id=2048 at 0x3fdbf95e4d08> JSON: {
    "id": 2048,
    "object": "credit_note",
    "customer": 15444,
    "invoice": 46225,
    "name": null,
    "currency": "usd",
    "draft": false,
    "closed": false,
    "paid": false,
    "status": "open",
    "number": "CN-0016",
    "date": 1416290400,
    "items": [
      {
        "id": 7,
        "object": "line_item",
        "catalog_item": null,
        "type": "product",
        "name": "Copy Paper, Case",
        "description": null,
        "quantity": 1,
        "unit_cost": 45,
        "amount": 45,
        "discountable": true,
        "discounts": [],
        "taxable": true,
        "taxes": [],
        "metadata": {}
      },
      {
        "id": 8,
        "object": "line_item",
        "catalog_item": "delivery",
        "type": "service",
        "name": "Delivery",
        "description": null,
        "quantity": 1,
        "unit_cost": 10,
        "amount": 10,
        "discountable": true,
        "discounts": [],
        "taxable": true,
        "taxes": [],
        "metadata": {}
      }
    ],
    "notes": null,
    "subtotal": 55,
    "discounts": [],
    "taxes": [
      {
        "id": 20554,
        "object": "tax",
        "amount": 3.85,
        "tax_rate": null
      }
    ],
    "total": 51.15,
    "balance": 51.15,
    "url": "https://dundermifflin.invoiced.com/credit_notes/IZmXbVOPyvfD3GPBmyd6FwXY",
    "pdf_url": "https://dundermifflin.invoiced.com/credit_notes/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
    "created_at": 1415229884,
    "metadata": {}
  },
  <CreditNote id=15445 at 0x3fdbf95e4d08> JSON: { ... },
  <CreditNote id=15446 at 0x3fdbf95e4d08> JSON: { ... }
]
```

```java
[
  com.invoiced.entity.CreditNote@c509a57 JSON: {
    "id": 2048,
    "object": "credit_note",
    "customer": 15444,
    "invoice": 46225,
    "name": null,
    "currency": "usd",
    "draft": false,
    "closed": false,
    "paid": false,
    "status": "open",
    "number": "CN-0016",
    "date": 1416290400,
    "items": [
      {
        "id": 7,
        "object": "line_item",
        "catalog_item": null,
        "type": "product",
        "name": "Copy Paper, Case",
        "description": null,
        "quantity": 1,
        "unit_cost": 45,
        "amount": 45,
        "discountable": true,
        "discounts": [],
        "taxable": true,
        "taxes": [],
        "metadata": {}
      },
      {
        "id": 8,
        "object": "line_item",
        "catalog_item": "delivery",
        "type": "service",
        "name": "Delivery",
        "description": null,
        "quantity": 1,
        "unit_cost": 10,
        "amount": 10,
        "discountable": true,
        "discounts": [],
        "taxable": true,
        "taxes": [],
        "metadata": {}
      }
    ],
    "notes": null,
    "subtotal": 55,
    "discounts": [],
    "taxes": [
      {
        "id": 20554,
        "object": "tax",
        "amount": 3.85,
        "tax_rate": null
      }
    ],
    "total": 51.15,
    "balance": 51.15,
    "url": "https://dundermifflin.invoiced.com/credit_notes/IZmXbVOPyvfD3GPBmyd6FwXY",
    "pdf_url": "https://dundermifflin.invoiced.com/credit_notes/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
    "created_at": 1415229884,
    "metadata": {}
  }, 
  com.invoiced.entity.CreditNote@20301171 JSON: {...},
  com.invoiced.entity.CreditNote@30301171 JSON: {...}
]
```

This endpoint retrieves all credit notes.

### HTTP Request

`GET /credit_notes`

### Query Parameters

Parameter | Description
--------- | -----------
**sort** *string* | Column to sort by, i.e. `name asc`
**filter** *object* | Filter object
**metadata** *object* | Metadata filter object
**start_date** *timestamp* | Restricts the results to credit notes *on or after* the given timestamp
**end_date** *timestamp* | Restricts the results to credit notes *on or before* the given timestamp
