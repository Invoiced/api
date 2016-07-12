# Invoices

An invoice representeds a balance owed to you by a Customer. Each invoice has a collection of line items that detail the products or services that are now due. An invoice can be in one of many different states depending on the due date, payments, and whether it was sent to or viewed by the customer.

Invoices can be marked as paid with Transactions. Once the sum of all Transactions for an invoice is greater than or equal to the total then the invoice will be considered paid in full.

## Invoice Object

### Attributes

```shell
{
  "id": 46225,
  "customer": 15444,
  "name": null,
  "currency": "usd",
  "draft": false,
  "closed": false,
  "paid": false,
  "status": "not_sent",
  "chase": false,
  "next_chase_on": null,
  "collection_mode": "manual",
  "attempt_count": 0,
  "next_payment_attempt": null,
  "subscription": null,
  "number": "INV-0016",
  "date": 1416290400,
  "due_date": 1417500000,
  "payment_terms": "NET 14",
  "items": [
    {
      "id": 7,
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
      "catalog_item": "delivery",
      "type": "service",
      "name": "Delivery",
      "description": "",
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
      "amount": 3.85,
      "tax_rate": null
    }
  ],
  "total": 51.15,
  "balance": 51.15,
  "tags": [],
  "url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY",
  "payment_url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY/payment",
  "pdf_url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
  "created_at": 1415229884,
  "metadata": {}
}
```

```ruby
#<Invoiced::Invoice:0x3fdbf95e4d08 id=46225> JSON: {
  "id": 46225,
  "customer": 15444,
  "name": null,
  "currency": "usd",
  "draft": false,
  "closed": false,
  "paid": false,
  "status": "not_sent",
  "chase": false,
  "next_chase_on": null,
  "collection_mode": "manual",
  "attempt_count": 0,
  "next_payment_attempt": null,
  "subscription": null,
  "number": "INV-0016",
  "date": 1416290400,
  "due_date": 1417500000,
  "payment_terms": "NET 14",
  "items": [
    {
      "id": 7,
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
      "catalog_item": "delivery",
      "type": "service",
      "name": "Delivery",
      "description": "",
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
      "amount": 3.85,
      "tax_rate": null
    }
  ],
  "total": 51.15,
  "balance": 51.15,
  "tags": [],
  "url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY",
  "payment_url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY/payment",
  "pdf_url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
  "created_at": 1415229884,
  "metadata": {}
}
```

```php
Invoiced\Invoice JSON: {
  "id": 46225,
  "customer": 15444,
  "name": null,
  "currency": "usd",
  "draft": false,
  "closed": false,
  "paid": false,
  "status": "not_sent",
  "chase": false,
  "next_chase_on": null,
  "collection_mode": "manual",
  "attempt_count": 0,
  "next_payment_attempt": null,
  "subscription": null,
  "number": "INV-0016",
  "date": 1416290400,
  "due_date": 1417500000,
  "payment_terms": "NET 14",
  "items": [
    {
      "id": 7,
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
      "catalog_item": "delivery",
      "type": "service",
      "name": "Delivery",
      "description": "",
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
      "amount": 3.85,
      "tax_rate": null
    }
  ],
  "total": 51.15,
  "balance": 51.15,
  "tags": [],
  "url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY",
  "payment_url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY/payment",
  "pdf_url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
  "created_at": 1415229884,
  "metadata": {}
}
```

```python
<Invoice id=46225 at 0x3fdbf95e4d08> JSON: {
  "id": 46225,
  "customer": 15444,
  "name": null,
  "currency": "usd",
  "draft": false,
  "closed": false,
  "paid": false,
  "status": "not_sent",
  "chase": false,
  "next_chase_on": null,
  "collection_mode": "manual",
  "attempt_count": 0,
  "next_payment_attempt": null,
  "subscription": null,
  "number": "INV-0016",
  "date": 1416290400,
  "due_date": 1417500000,
  "payment_terms": "NET 14",
  "items": [
    {
      "id": 7,
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
      "catalog_item": "delivery",
      "type": "service",
      "name": "Delivery",
      "description": "",
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
      "amount": 3.85,
      "tax_rate": null
    }
  ],
  "total": 51.15,
  "balance": 51.15,
  "tags": [],
  "url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY",
  "payment_url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY/payment",
  "pdf_url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
  "created_at": 1415229884,
  "metadata": {}
}
```

Parameter | Type | Description
--------- | ---- | -----------
**id** | *integer* | The invoice's unique ID
**customer** | *integer* | Customer ID
**name** | *string* | Invoice name for internal use, defaults to "Invoice"
**number** | *string* | The reference number assigned to the invoice for use in the dashboard
**collection_mode** | *string* | Invoice collection mode, `auto` or `manual`
**currency** | *string* | [3-letter ISO code](https://en.wikipedia.org/wiki/ISO_4217)
**draft** | *boolean* | When false, the invoice is considered outstanding, or when true, the invoice is a draft
**closed** | *boolean* | When true, an invoice is closed and considered bad debt. No further payments are allowed.
**paid** | *boolean* | Indicates whether an invoice has been paid in full
**status** | *string* | Invoice state, one of `draft`, `not_sent`, `sent`, `viewed`, `past_due`, `pending`, `paid`
**chase** | *boolean* | Whether chasing is enabled for the invoice
**next_chase_on** | *timestamp* | Next scheduled chase
**attempt_count** | *integer* | # of payment attempts
**next_payment_attempt** | *timestamp* | Next scheduled charge attempt, when in automatic collection
**subscription** | *integer* | Subscription ID if invoice came from subscription
**date** | *timestamp* | Invoice date
**due_date** | *timestamp* | Date payment is due by
**payment_terms** | *string* | Payment terms for the invoice, i.e. "NET 30"
**items** | *array* | Collection of Line Items
**notes** | *string* | Additional notes displayed on invoice
**subtotal** | *number* | Subtotal
**discounts** | *array* | Collection of Discounts
**taxes** | *array* | Collection of Taxes
**total** | *number* | Total
**balance** | *number* | Balance owed
**tags** | *array* | Invoice tags
**url** | *string* | URL to view the invoice in the billing portal
**payment_url** | *string* | URL for the invoice payment page
**pdf_url** | *string* | URL to download the invoice as a PDF
**created_at** | *timestamp* | Timestamp when created
**metadata** | *object* | A hash of key/value pairs that can store additional information about this object.

## Line Item Object

### Attributes

```shell
{
  "id": 8,
  "catalog_item": "delivery",
  "type": "service",
  "name": "Delivery",
  "description": "",
  "quantity": 1,
  "unit_cost": 10,
  "amount": 10,
  "discountable": true,
  "discounts": [],
  "taxable": true,
  "taxes": [],
  "metadata": {}
}
```

```ruby
#<Invoiced::LineItem:0x3fdbf95e4d08 id=8> JSON: {
  "id": 8,
  "catalog_item": "delivery",
  "type": "service",
  "name": "Delivery",
  "description": "",
  "quantity": 1,
  "unit_cost": 10,
  "amount": 10,
  "discountable": true,
  "discounts": [],
  "taxable": true,
  "taxes": [],
  "metadata": {}
}
```

```php
Invoiced\LineItem JSON: {
  "id": 8,
  "catalog_item": "delivery",
  "type": "service",
  "name": "Delivery",
  "description": "",
  "quantity": 1,
  "unit_cost": 10,
  "amount": 10,
  "discountable": true,
  "discounts": [],
  "taxable": true,
  "taxes": [],
  "metadata": {}
}
```

```python
<LineItem id=8 at 0x3fdbf95e4d08> JSON: {
  "id": 8,
  "catalog_item": "delivery",
  "type": "service",
  "name": "Delivery",
  "description": "",
  "quantity": 1,
  "unit_cost": 10,
  "amount": 10,
  "discountable": true,
  "discounts": [],
  "taxable": true,
  "taxes": [],
  "metadata": {}
}
```

Parameter | Type | Description
--------- | ---- | -----------
**id** | *integer* | The line item's unique ID
**catalog_item** | *string* | Optional Catalog Item ID. Fills the line item with the name and pricing of the Catalog Item.
**type** | *string* | Optional line item type. Used to group line items by type in reporting
**name** | *string* | Title
**description** | *string* | Optional description
**quantity** | *number* | Quantity
**unit_cost** | *number* | Unit cost or rate
**amount** | *number* | Computed from `quantity` x `unit_cost`
**discountable** | *boolean* | Excludes amount from invoice discounts when `false`
**discounts** | *array* | Line item Discounts
**taxable** | *boolean* | Excludes amount from invoice taxes when `false`
**taxes** | *array* | Line item Taxes
**plan** | *string* | Plan ID, only present when type is `plan`
**metadata** | *object* | A hash of key/value pairs that can store additional information about this object.

## Discount Object

Represents the application of a discount to an invoice or line item.

### Attributes

```shell
{
  "id": 20553,
  "amount": 5,
  "coupon": null,
  "expires": null
}
```

```ruby
#<Invoiced::Discount:0x3fdbf95e4d08 id=20553> JSON: {
  "id": 20553,
  "amount": 5,
  "coupon": null,
  "expires": null
}
```

```php
Invoiced\Discount JSON: {
  "id": 20553,
  "amount": 5,
  "coupon": null,
  "expires": null
}
```

```python
<Discount id=20553 at 0x3fdbf95e4d08> JSON: {
  "id": 20553,
  "amount": 5,
  "coupon": null,
  "expires": null
}
```

Parameter | Type | Description
--------- | ---- | -----------
**id** | *integer* | The discount's unique ID
**amount** | *number* | Discount amount
**coupon** | *object* | Coupon the discount was computed from, if any
**expires** | *timestamp* | Time until discount expires, if any

## Tax Object

Represents the application of tax to an invoice or line item.

### Attributes

```shell
{
  "id": 20554,
  "amount": 3.85,
  "tax_rate": null
}
```

```ruby
#<Invoiced::Tax:0x3fdbf95e4d08 id=20554> JSON: {
  "id": 20554,
  "amount": 3.85,
  "tax_rate": null
}
```

```php
Invoiced\Tax JSON: {
  "id": 20554,
  "amount": 3.85,
  "tax_rate": null
}
```

```python
<Tax id=20554 at 0x3fdbf95e4d08> JSON: {
  "id": 20554,
  "amount": 3.85,
  "tax_rate": null
}
```

Parameter | Type | Description
--------- | ---- | -----------
**id** | *integer* | The tax's unique ID
**amount** | *number* | Tax amount
**tax_rate** | *object* | Tax Rate the tax was computed from, if any

## Create an invoice

```shell
curl "https://api.invoiced.com/invoices" \
  -u {API_KEY}: \
  -d customer=15444 \
  -d payment_terms="NET 14" \
  -d items[0][name]="Copy paper, Case" \
  -d items[0][quantity]=1 \
  -d items[0][unit_cost]=45 \
  -d items[1][catalog_item]="delivery" \
  -d items[1][quantity]=1 \
  -d taxes[0][amount]=3.85
```

```ruby
invoiced.Invoice.create(
  :customer => 15444,
  :payment_terms => "NET 14",
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

$invoice = $invoiced->Invoice->create([
  'customer' => 15444,
  'payment_terms' => "NET 14",
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
client.Invoice.create(
  customer=15444,
  payment_terms="NET 14",
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

> The above command returns JSON structured like this:

```shell
{
  "id": 46225,
  "customer": 15444,
  "name": null,
  "currency": "usd",
  "draft": false,
  "closed": false,
  "paid": false,
  "status": "not_sent",
  "chase": false,
  "next_chase_on": null,
  "collection_mode": "manual",
  "attempt_count": 0,
  "next_payment_attempt": null,
  "subscription": null,
  "number": "INV-0016",
  "date": 1416290400,
  "due_date": 1417500000,
  "payment_terms": "NET 14",
  "items": [
    {
      "id": 7,
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
      "catalog_item": "delivery",
      "type": "service",
      "name": "Delivery",
      "description": "",
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
      "amount": 3.85,
      "tax_rate": null
    }
  ],
  "total": 51.15,
  "balance": 51.15,
  "tags": [],
  "url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY",
  "payment_url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY/payment",
  "pdf_url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
  "created_at": 1415229884,
  "metadata": {}
}
```

```ruby
#<Invoiced::Invoice:0x3fdbf95e4d08 id=46225> JSON: {
  "id": 46225,
  "customer": 15444,
  "name": null,
  "currency": "usd",
  "draft": false,
  "closed": false,
  "paid": false,
  "status": "not_sent",
  "chase": false,
  "next_chase_on": null,
  "collection_mode": "manual",
  "attempt_count": 0,
  "next_payment_attempt": null,
  "subscription": null,
  "number": "INV-0016",
  "date": 1416290400,
  "due_date": 1417500000,
  "payment_terms": "NET 14",
  "items": [
    {
      "id": 7,
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
      "catalog_item": "delivery",
      "type": "service",
      "name": "Delivery",
      "description": "",
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
      "amount": 3.85,
      "tax_rate": null
    }
  ],
  "total": 51.15,
  "balance": 51.15,
  "tags": [],
  "url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY",
  "payment_url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY/payment",
  "pdf_url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
  "created_at": 1415229884,
  "metadata": {}
}
```

```php
Invoiced\Invoice JSON: {
  "id": 46225,
  "customer": 15444,
  "name": null,
  "currency": "usd",
  "draft": false,
  "closed": false,
  "paid": false,
  "status": "not_sent",
  "chase": false,
  "next_chase_on": null,
  "collection_mode": "manual",
  "attempt_count": 0,
  "next_payment_attempt": null,
  "subscription": null,
  "number": "INV-0016",
  "date": 1416290400,
  "due_date": 1417500000,
  "payment_terms": "NET 14",
  "items": [
    {
      "id": 7,
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
      "catalog_item": "delivery",
      "type": "service",
      "name": "Delivery",
      "description": "",
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
      "amount": 3.85,
      "tax_rate": null
    }
  ],
  "total": 51.15,
  "balance": 51.15,
  "tags": [],
  "url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY",
  "payment_url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY/payment",
  "pdf_url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
  "created_at": 1415229884,
  "metadata": {}
}
```

```python
<Invoice id=46225 at 0x3fdbf95e4d08> JSON: {
  "id": 46225,
  "customer": 15444,
  "name": null,
  "currency": "usd",
  "draft": false,
  "closed": false,
  "paid": false,
  "status": "not_sent",
  "chase": false,
  "next_chase_on": null,
  "collection_mode": "manual",
  "attempt_count": 0,
  "next_payment_attempt": null,
  "subscription": null,
  "number": "INV-0016",
  "date": 1416290400,
  "due_date": 1417500000,
  "payment_terms": "NET 14",
  "items": [
    {
      "id": 7,
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
      "catalog_item": "delivery",
      "type": "service",
      "name": "Delivery",
      "description": "",
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
      "amount": 3.85,
      "tax_rate": null
    }
  ],
  "total": 51.15,
  "balance": 51.15,
  "tags": [],
  "url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY",
  "payment_url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY/payment",
  "pdf_url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
  "created_at": 1415229884,
  "metadata": {}
}
```

Create a new invoice with this endpoint.

### HTTP Request

`POST /invoices`

### Attributes

Parameter | Type | Description
--------- | ---- | -----------
**customer** | *integer* | Customer ID - **required**
**name** | *string* | Invoice name for internal use, defaults to "Invoice"
**number** | *string* | The reference number assigned to the invoice, defaults to next # in auto-numbering sequence
**currency** | *string* | [3-letter ISO code](https://en.wikipedia.org/wiki/ISO_4217) - defaults to account currency
**collection_mode** | *string* | Invoice collection mode, `auto` or `manual` - inherited from customer by default
**payment_terms** | *string* | Payment terms for the invoice, i.e. "NET 30" - inherited from customer by default
**date** | *timestamp* | Invoice date - defaults to current timestamp
**due_date** | *timestamp* | Due date - computed from `payment_terms` when not supplied
**draft** | *boolean* | When false, the invoice is considered outstanding, or when true, the invoice is a draft
**closed** | *boolean* | Marks an invoice as closed
**chase** | *boolean* | Enables chasing for this invoice
**items** | *array* | Collection of Line Items
**notes** | *string* | Additional notes displayed on invoice
**discounts** | *array* | Collection of Discounts
**taxes** | *array* | Collection of Taxes
**tags** | *array* | Invoice tags
**metadata** | *object* | A hash of key/value pairs that can store additional information about this object.
**attachments** | *array* | A list of [File](#file-object) IDs to attach to the invoice

## Retrieve an invoice

```shell
curl "https://api.invoiced.com/invoices/:id" \
  -u {API_KEY}:
```

```ruby
invoice = invoiced.Invoice.retrieve("{INVOICE_ID}")
```

```php
<?php

$invoice = $invoiced->Invoice->retrieve("{INVOICE_ID}");
```

```python
invoice = client.Invoice.retrieve("{INVOICE_ID}")
```

> The above command returns JSON structured like this:

```shell
{
  "id": 46225,
  "customer": 15444,
  "name": null,
  "currency": "usd",
  "draft": false,
  "closed": false,
  "paid": false,
  "status": "not_sent",
  "chase": false,
  "next_chase_on": null,
  "collection_mode": "manual",
  "attempt_count": 0,
  "next_payment_attempt": null,
  "subscription": null,
  "number": "INV-0016",
  "date": 1416290400,
  "due_date": 1417500000,
  "payment_terms": "NET 14",
  "items": [
    {
      "id": 7,
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
      "catalog_item": "delivery",
      "type": "service",
      "name": "Delivery",
      "description": "",
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
      "amount": 3.85,
      "tax_rate": null
    }
  ],
  "total": 51.15,
  "balance": 51.15,
  "tags": [],
  "url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY",
  "payment_url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY/payment",
  "pdf_url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
  "created_at": 1415229884,
  "metadata": {}
}
```

```ruby
#<Invoiced::Invoice:0x3fdbf95e4d08 id=46225> JSON: {
  "id": 46225,
  "customer": 15444,
  "name": null,
  "currency": "usd",
  "draft": false,
  "closed": false,
  "paid": false,
  "status": "not_sent",
  "chase": false,
  "next_chase_on": null,
  "collection_mode": "manual",
  "attempt_count": 0,
  "next_payment_attempt": null,
  "subscription": null,
  "number": "INV-0016",
  "date": 1416290400,
  "due_date": 1417500000,
  "payment_terms": "NET 14",
  "items": [
    {
      "id": 7,
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
      "catalog_item": "delivery",
      "type": "service",
      "name": "Delivery",
      "description": "",
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
      "amount": 3.85,
      "tax_rate": null
    }
  ],
  "total": 51.15,
  "balance": 51.15,
  "tags": [],
  "url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY",
  "payment_url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY/payment",
  "pdf_url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
  "created_at": 1415229884,
  "metadata": {}
}
```

```php
Invoiced\Invoice JSON: {
  "id": 46225,
  "customer": 15444,
  "name": null,
  "currency": "usd",
  "draft": false,
  "closed": false,
  "paid": false,
  "status": "not_sent",
  "chase": false,
  "next_chase_on": null,
  "collection_mode": "manual",
  "attempt_count": 0,
  "next_payment_attempt": null,
  "subscription": null,
  "number": "INV-0016",
  "date": 1416290400,
  "due_date": 1417500000,
  "payment_terms": "NET 14",
  "items": [
    {
      "id": 7,
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
      "catalog_item": "delivery",
      "type": "service",
      "name": "Delivery",
      "description": "",
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
      "amount": 3.85,
      "tax_rate": null
    }
  ],
  "total": 51.15,
  "balance": 51.15,
  "tags": [],
  "url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY",
  "payment_url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY/payment",
  "pdf_url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
  "created_at": 1415229884,
  "metadata": {}
}
```

```python
<Invoice id=46225 at 0x3fdbf95e4d08> JSON: {
  "id": 46225,
  "customer": 15444,
  "name": null,
  "currency": "usd",
  "draft": false,
  "closed": false,
  "paid": false,
  "status": "not_sent",
  "chase": false,
  "next_chase_on": null,
  "collection_mode": "manual",
  "attempt_count": 0,
  "next_payment_attempt": null,
  "subscription": null,
  "number": "INV-0016",
  "date": 1416290400,
  "due_date": 1417500000,
  "payment_terms": "NET 14",
  "items": [
    {
      "id": 7,
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
      "catalog_item": "delivery",
      "type": "service",
      "name": "Delivery",
      "description": "",
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
      "amount": 3.85,
      "tax_rate": null
    }
  ],
  "total": 51.15,
  "balance": 51.15,
  "tags": [],
  "url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY",
  "payment_url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY/payment",
  "pdf_url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
  "created_at": 1415229884,
  "metadata": {}
}
```

This endpoint retrieves a specific invoice.

### HTTP Request

`GET /invoices/:id`

### Query Parameters

Parameter | Type | Description
--------- | ---- | -----------
**expand** | *string* | Properties to expand

## Update an invoice

```shell
curl "https://api.invoiced.com/invoices/:id" \
  -u {API_KEY}: \
  -X PATCH \
  -d sent=1 \
  -d chase=1
```

```ruby
invoice.name = "July Paper Delivery"
invoice.notes = "The order was delivered on Jul 20, 2015"
invoice.sent = true
invoice.save
```

```php
<?php

$invoice->name = "July Paper Delivery";
$invoice->notes = "The order was delivered on Jul 20, 2015";
$invoice->sent = true;
$invoice->save();
```

```python
invoice.name = "July Paper Delivery"
invoice.notes = "The order was delivered on Jul 20, 2015"
invoice.sent = True
invoice.save()
```

> The above command returns JSON structured like this:

```shell
{
  "id": 46225,
  "customer": 15444,
  "name": "July Paper Delivery",
  "currency": "usd",
  "draft": false,
  "closed": false,
  "paid": false,
  "status": "sent",
  "chase": false,
  "next_chase_on": null,
  "collection_mode": "manual",
  "attempt_count": 0,
  "next_payment_attempt": null,
  "subscription": null,
  "number": "INV-0016",
  "date": 1416290400,
  "due_date": 1417500000,
  "payment_terms": "NET 14",
  "items": [
    {
      "id": 7,
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
      "catalog_item": "delivery",
      "type": "service",
      "name": "Delivery",
      "description": "",
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
      "amount": 3.85,
      "tax_rate": null
    }
  ],
  "total": 51.15,
  "balance": 51.15,
  "tags": [],
  "url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY",
  "payment_url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY/payment",
  "pdf_url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
  "created_at": 1415229884,
  "metadata": {}
}
```

```ruby
#<Invoiced::Invoice:0x3fdbf95e4d08 id=46225> JSON: {
  "id": 46225,
  "customer": 15444,
  "name": null,
  "currency": "usd",
  "draft": false,
  "closed": false,
  "paid": false,
  "status": "not_sent",
  "chase": false,
  "next_chase_on": null,
  "collection_mode": "manual",
  "attempt_count": 0,
  "next_payment_attempt": null,
  "subscription": null,
  "number": "INV-0016",
  "date": 1416290400,
  "due_date": 1417500000,
  "payment_terms": "NET 14",
  "items": [
    {
      "id": 7,
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
      "catalog_item": "delivery",
      "type": "service",
      "name": "Delivery",
      "description": "",
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
      "amount": 3.85,
      "tax_rate": null
    }
  ],
  "total": 51.15,
  "balance": 51.15,
  "tags": [],
  "url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY",
  "payment_url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY/payment",
  "pdf_url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
  "created_at": 1415229884,
  "metadata": {}
}
```

```php
Invoiced\Invoice JSON: {
  "id": 46225,
  "customer": 15444,
  "name": null,
  "currency": "usd",
  "draft": false,
  "closed": false,
  "paid": false,
  "status": "not_sent",
  "chase": false,
  "next_chase_on": null,
  "collection_mode": "manual",
  "attempt_count": 0,
  "next_payment_attempt": null,
  "subscription": null,
  "number": "INV-0016",
  "date": 1416290400,
  "due_date": 1417500000,
  "payment_terms": "NET 14",
  "items": [
    {
      "id": 7,
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
      "catalog_item": "delivery",
      "type": "service",
      "name": "Delivery",
      "description": "",
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
      "amount": 3.85,
      "tax_rate": null
    }
  ],
  "total": 51.15,
  "balance": 51.15,
  "tags": [],
  "url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY",
  "payment_url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY/payment",
  "pdf_url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
  "created_at": 1415229884,
  "metadata": {}
}
```

```python
<Invoice id=46225 at 0x3fdbf95e4d08> JSON: {
  "id": 46225,
  "customer": 15444,
  "name": null,
  "currency": "usd",
  "draft": false,
  "closed": false,
  "paid": false,
  "status": "not_sent",
  "chase": false,
  "next_chase_on": null,
  "collection_mode": "manual",
  "attempt_count": 0,
  "next_payment_attempt": null,
  "subscription": null,
  "number": "INV-0016",
  "date": 1416290400,
  "due_date": 1417500000,
  "payment_terms": "NET 14",
  "items": [
    {
      "id": 7,
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
      "catalog_item": "delivery",
      "type": "service",
      "name": "Delivery",
      "description": "",
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
      "amount": 3.85,
      "tax_rate": null
    }
  ],
  "total": 51.15,
  "balance": 51.15,
  "tags": [],
  "url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY",
  "payment_url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY/payment",
  "pdf_url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
  "created_at": 1415229884,
  "metadata": {}
}
```

Use this endpoint to update an invoice.

### HTTP Request

`PATCH /invoices/:id`

### Attributes

Parameter | Type | Description
--------- | ---- | -----------
**name** | *string* | Invoice name for internal use, defaults to "Invoice"
**number** | *string* | The reference number assigned to the invoice, defaults to next # in auto-numbering sequence
**currency** | *string* | [3-letter ISO code](https://en.wikipedia.org/wiki/ISO_4217) - defaults to account currency
**payment_terms** | *string* | Payment terms for the invoice, i.e. "NET 30" - inherited from customer by default
**date** | *timestamp* | Invoice date - defaults to current timestamp
**due_date** | *timestamp* | Due date - computed from `payment_terms` when not supplied
**draft** | *boolean* | When false, the invoice is considered outstanding, or when true, the invoice is a draft
**closed** | *boolean* | Marks an invoice as closed
**chase** | *boolean* | Enables chasing for this invoice
**items** | *array* | Collection of Line Items
**notes** | *string* | Additional notes displayed on invoice
**discounts** | *array* | Collection of Discounts
**taxes** | *array* | Collection of Taxes
**tags** | *array* | Invoice tags
**metadata** | *object* | A hash of key/value pairs that can store additional information about this object.
**attachments** | *array* | A list of [File](#file-object) IDs to attach to the invoice. Replaces existing attachments. Not providing this keeps existing attachments.

## Send an invoice

```shell
curl "https://api.invoiced.com/invoices/:id/emails" \
  -u {API_KEY}: \
  -X POST
```

```ruby
emails = invoice.send
```

```php
<?php

$emails = $invoice->send();
```

```python
emails = invoice.send()
```

> The above command returns JSON structured like this:

```shell
[
  {
    "id": "f45382c6fbc44d44aa7f9a55eb2ce731",
    "state": "sent",
    "reject_reason": null,
    "email": "client@example.com",
    "template": "new_invoice_email",
    "subject": "New Invoice from Dunder Mifflin, Inc.: INV-0016",
    "message": "Dear Client, a new invoice for $51.15 has been created on your account. [View and Pay Invoice button] Thank you!",
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
  #<Invoiced::Email:0x3fdbf95e4d08 id=f45382c6fbc44d44aa7f9a55eb2ce731> JSON: {
    "id": "f45382c6fbc44d44aa7f9a55eb2ce731",
    "state": "sent",
    "reject_reason": null,
    "email": "client@example.com",
    "template": "new_invoice_email",
    "subject": "New Invoice from Dunder Mifflin, Inc.: INV-0016",
    "message": "Dear Client, a new invoice for $51.15 has been created on your account. [View and Pay Invoice button] Thank you!",
    "opens": 0,
    "opens_detail": [],
    "clicks": 0,
    "clicks_detail": [],
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
    "state": "sent",
    "reject_reason": null,
    "email": "client@example.com",
    "template": "new_invoice_email",
    "subject": "New Invoice from Dunder Mifflin, Inc.: INV-0016",
    "message": "Dear Client, a new invoice for $51.15 has been created on your account. [View and Pay Invoice button] Thank you!",
    "opens": 0,
    "opens_detail": [],
    "clicks": 0,
    "clicks_detail": [],
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
    "state": "sent",
    "reject_reason": null,
    "email": "client@example.com",
    "template": "new_invoice_email",
    "subject": "New Invoice from Dunder Mifflin, Inc.: INV-0016",
    "message": "Dear Client, a new invoice for $51.15 has been created on your account. [View and Pay Invoice button] Thank you!",
    "opens": 0,
    "opens_detail": [],
    "clicks": 0,
    "clicks_detail": [],
    "created_at": 1436890047
  },
  <Email id=f45382c6fbc44d44aa7f9a55eb2ce731 at 0x3fdbf95e4d08> JSON: { ... },
  <Email id=f45382c6fbc44d44aa7f9a55eb2ce731 at 0x3fdbf95e4d08> JSON: { ... }
]
```

This endpoint sends an invoice to your customer.

### HTTP Request

`POST /invoices/:id/emails`

### Request Parameters

Parameter | Type | Description
--------- | ---- | -----------
**to** | *array* | Optional array of recipients like:<br/>`[{"name": "Client", "email": "client@example.com"}]`
**bcc** | *string* | Optional comma-separated list of email addresses to be blind carbon copied
**subject** | *string* | Optional subject
**message** | *string* | Optional message body, otherwise the appropriate invoice template is used

<aside class="info">
A successful response means that your email has been added to the send queue.
</aside>

## Pay an invoice

```shell
curl "https://api.invoiced.com/invoices/:id/pay" \
  -u {API_KEY}: \
  -X POST
```

```ruby
invoice.pay
```

```php
<?php

$invoice->pay();
```

```python
invoice.pay()
```

> The above command returns JSON structured like this:

```shell
{
  "id": 46226,
  "customer": 15446,
  "name": null,
  "currency": "usd",
  "draft": false,
  "closed": false,
  "paid": true,
  "status": "paid",
  "chase": false,
  "next_chase_on": null,
  "collection_mode": "auto",
  "attempt_count": 1,
  "next_payment_attempt": null,
  "subscription": null,
  "number": "INV-0017",
  "date": 1416290402,
  "due_date": null,
  "payment_terms": "Auto-Charged",
  "items": [
    {
      "id": 9,
      "catalog_item": null,
      "type": "product",
      "name": "Copy Paper, Case",
      "description": null,
      "quantity": 5,
      "unit_cost": 45,
      "amount": 225,
      "discountable": true,
      "discounts": [],
      "taxable": true,
      "taxes": [],
      "metadata": {}
    }
  ],
  "notes": null,
  "subtotal": 225,
  "discounts": [],
  "taxes": [
    {
      "id": 20554,
      "amount": 3.85,
      "tax_rate": null
    }
  ],
  "total": 228.85,
  "balance": 228.85,
  "tags": [],
  "url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfDasdfGPBmyd6FwXZ",
  "payment_url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfDasdfGPBmyd6FwXZ/payment",
  "pdf_url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfDasdfGPBmyd6FwXZ/pdf",
  "created_at": 1415229885,
  "metadata": {}
}
```

```ruby
#<Invoiced::Invoice:0x3fdbf95e4d08 id=46226> JSON: {
  "id": 46226,
  "customer": 15446,
  "name": null,
  "currency": "usd",
  "draft": false,
  "closed": false,
  "paid": true,
  "status": "paid",
  "chase": false,
  "next_chase_on": null,
  "collection_mode": "auto",
  "attempt_count": 1,
  "next_payment_attempt": null,
  "subscription": null,
  "number": "INV-0017",
  "date": 1416290402,
  "due_date": null,
  "payment_terms": "Auto-Charged",
  "items": [
    {
      "id": 9,
      "catalog_item": null,
      "type": "product",
      "name": "Copy Paper, Case",
      "description": null,
      "quantity": 5,
      "unit_cost": 45,
      "amount": 225,
      "discountable": true,
      "discounts": [],
      "taxable": true,
      "taxes": [],
      "metadata": {}
    }
  ],
  "notes": null,
  "subtotal": 225,
  "discounts": [],
  "taxes": [
    {
      "id": 20554,
      "amount": 3.85,
      "tax_rate": null
    }
  ],
  "total": 228.85,
  "balance": 228.85,
  "tags": [],
  "url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfDasdfGPBmyd6FwXZ",
  "payment_url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfDasdfGPBmyd6FwXZ/payment",
  "pdf_url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfDasdfGPBmyd6FwXZ/pdf",
  "created_at": 1415229885,
  "metadata": {}
}
```

```php
Invoiced\Invoice JSON: {
  "id": 46226,
  "customer": 15446,
  "name": null,
  "currency": "usd",
  "draft": false,
  "closed": false,
  "paid": true,
  "status": "paid",
  "chase": false,
  "next_chase_on": null,
  "collection_mode": "auto",
  "attempt_count": 1,
  "next_payment_attempt": null,
  "subscription": null,
  "number": "INV-0017",
  "date": 1416290402,
  "due_date": null,
  "payment_terms": "Auto-Charged",
  "items": [
    {
      "id": 9,
      "catalog_item": null,
      "type": "product",
      "name": "Copy Paper, Case",
      "description": null,
      "quantity": 5,
      "unit_cost": 45,
      "amount": 225,
      "discountable": true,
      "discounts": [],
      "taxable": true,
      "taxes": [],
      "metadata": {}
    }
  ],
  "notes": null,
  "subtotal": 225,
  "discounts": [],
  "taxes": [
    {
      "id": 20554,
      "amount": 3.85,
      "tax_rate": null
    }
  ],
  "total": 228.85,
  "balance": 228.85,
  "tags": [],
  "url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfDasdfGPBmyd6FwXZ",
  "payment_url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfDasdfGPBmyd6FwXZ/payment",
  "pdf_url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfDasdfGPBmyd6FwXZ/pdf",
  "created_at": 1415229885,
  "metadata": {}
}
```

```python
<Invoice id=46226 at 0x3fdbf95e4d08> JSON: {
  "id": 46226,
  "customer": 15446,
  "name": null,
  "currency": "usd",
  "draft": false,
  "closed": false,
  "paid": true,
  "status": "paid",
  "chase": false,
  "next_chase_on": null,
  "collection_mode": "auto",
  "attempt_count": 1,
  "next_payment_attempt": null,
  "subscription": null,
  "number": "INV-0017",
  "date": 1416290402,
  "due_date": null,
  "payment_terms": "Auto-Charged",
  "items": [
    {
      "id": 9,
      "catalog_item": null,
      "type": "product",
      "name": "Copy Paper, Case",
      "description": null,
      "quantity": 5,
      "unit_cost": 45,
      "amount": 225,
      "discountable": true,
      "discounts": [],
      "taxable": true,
      "taxes": [],
      "metadata": {}
    }
  ],
  "notes": null,
  "subtotal": 225,
  "discounts": [],
  "taxes": [
    {
      "id": 20554,
      "amount": 3.85,
      "tax_rate": null
    }
  ],
  "total": 228.85,
  "balance": 228.85,
  "tags": [],
  "url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfDasdfGPBmyd6FwXZ",
  "payment_url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfDasdfGPBmyd6FwXZ/payment",
  "pdf_url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfDasdfGPBmyd6FwXZ/pdf",
  "created_at": 1415229885,
  "metadata": {}
}
```

When an invoice is automatically collected we will perform the charge automatically. If a payment attempts fails then another attempt will be scheduled according to your retry settings. Or, you can trigger a charge attempt manually using this endpoint.

### HTTP Request

`POST /invoices/:id/pay`

<aside class="warning">
We can only collect on invoices in `auto` collection mode with a customer that has a valid payment source attached.
</aside>

## List invoice attachments

```shell
curl "https://api.invoiced.com/invoices/:id/attachments" \
  -u {API_KEY}:
```

```ruby
attachments, metadata = invoice.attachments
```

```php
<?php

list($attachments, $metadata) = $invoice->attachments();
```

```python
attachments, metadata = invoice.attachments()
```

> The above command returns JSON structured like this:

```shell
[
  {
    "id": 13,
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

This endpoint retrieves a list of files attached to a specific invoice.

### HTTP Request

`POST /invoices/:id/attachments`

## Delete an invoice

```shell
curl "https://api.invoiced.com/invoices/:id" \
  -u {API_KEY}: \
  -X DELETE
```

```ruby
invoice.delete
```

```php
<?php

$invoice->delete();
```

```python
invoice.delete()
```

> The above command returns `204 No Content`

This endpoint deletes a specific invoice.

### HTTP Request

`DELETE /invoices/:id`

## List all invoices

```shell
curl "https://api.invoiced.com/invoices" \
  -u {API_KEY}:
```

```ruby
invoices, metadata = invoiced.Invoice.list(:per_page => 3)
```

```php
<?php

list($invoices, $metadata) = $invoiced->Invoice->all(['per_page' => 3]);
```

```python
invoices, metadata = invoiced.Invoice.list(per_page=3)
```

> The above command returns JSON structured like this:

```shell
[
  {
    "id": 46225,
    "customer": 15444,
    "name": null,
    "currency": "usd",
    "draft": false,
    "closed": false,
    "paid": false,
    "status": "not_sent",
    "chase": false,
    "next_chase_on": null,
    "collection_mode": "manual",
    "attempt_count": 0,
    "next_payment_attempt": null,
    "subscription": null,
    "number": "INV-0016",
    "date": 1416290400,
    "due_date": 1417500000,
    "payment_terms": "NET 14",
    "items": [
      {
        "id": 7,
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
        "catalog_item": "delivery",
        "type": "service",
        "name": "Delivery",
        "description": "",
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
        "amount": 3.85,
        "tax_rate": null
      }
    ],
    "total": 51.15,
    "balance": 51.15,
    "tags": [],
    "url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY",
    "pdf_url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
    "created_at": 1415229884,
    "metadata": {}
  },
  { ... },
  { ... }
]
```

```ruby
[
  #<Invoiced::Invoice:0x3fdbf95e4d08 id=46225> JSON: {
    "id": 46225,
    "customer": 15444,
    "name": null,
    "currency": "usd",
    "draft": false,
    "closed": false,
    "paid": false,
    "status": "not_sent",
    "chase": false,
    "next_chase_on": null,
    "collection_mode": "manual",
    "attempt_count": 0,
    "next_payment_attempt": null,
    "subscription": null,
    "number": "INV-0016",
    "date": 1416290400,
    "due_date": 1417500000,
    "payment_terms": "NET 14",
    "items": [
      {
        "id": 7,
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
        "catalog_item": "delivery",
        "type": "service",
        "name": "Delivery",
        "description": "",
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
        "amount": 3.85,
        "tax_rate": null
      }
    ],
    "total": 51.15,
    "balance": 51.15,
    "tags": [],
    "url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY",
    "pdf_url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
    "created_at": 1415229884,
    "metadata": {}
  },
  #<Invoiced::Invoice:0x3fdbf95e4d09 id=15445> JSON: { ... },
  #<Invoiced::Invoice:0x3fdbf95e4d10 id=15446> JSON: { ... }
]
```

```php
[
  Invoiced\Invoice JSON: {
    "id": 46225,
    "customer": 15444,
    "name": null,
    "currency": "usd",
    "draft": false,
    "closed": false,
    "paid": false,
    "status": "not_sent",
    "chase": false,
    "next_chase_on": null,
    "collection_mode": "manual",
    "attempt_count": 0,
    "next_payment_attempt": null,
    "subscription": null,
    "number": "INV-0016",
    "date": 1416290400,
    "due_date": 1417500000,
    "payment_terms": "NET 14",
    "items": [
      {
        "id": 7,
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
        "catalog_item": "delivery",
        "type": "service",
        "name": "Delivery",
        "description": "",
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
        "amount": 3.85,
        "tax_rate": null
      }
    ],
    "total": 51.15,
    "balance": 51.15,
    "tags": [],
    "url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY",
    "pdf_url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
    "created_at": 1415229884,
    "metadata": {}
  },
  Invoiced\Invoice JSON: { ... },
  Invoiced\Invoice JSON: { ... }
]
```

```python
[
  <Invoice id=46225 at 0x3fdbf95e4d08> JSON: {
    "id": 46225,
    "customer": 15444,
    "name": null,
    "currency": "usd",
    "draft": false,
    "closed": false,
    "paid": false,
    "status": "not_sent",
    "chase": false,
    "next_chase_on": null,
    "collection_mode": "manual",
    "attempt_count": 0,
    "next_payment_attempt": null,
    "subscription": null,
    "number": "INV-0016",
    "date": 1416290400,
    "due_date": 1417500000,
    "payment_terms": "NET 14",
    "items": [
      {
        "id": 7,
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
        "catalog_item": "delivery",
        "type": "service",
        "name": "Delivery",
        "description": "",
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
        "amount": 3.85,
        "tax_rate": null
      }
    ],
    "total": 51.15,
    "balance": 51.15,
    "tags": [],
    "url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY",
    "pdf_url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
    "created_at": 1415229884,
    "metadata": {}
  },
  <Invoice id=15445 at 0x3fdbf95e4d08> JSON: { ... },
  <Invoice id=15446 at 0x3fdbf95e4d08> JSON: { ... }
]
```

This endpoint retrieves all invoices.

### HTTP Request

`GET /invoices`

### Query Parameters

Parameter | Description
--------- | -----------
**sort** *string* | Column to sort by, i.e. `name asc`
**filter** *object* | Filter object
**metadata** *object* | Metadata filter object
**start_date** *timestamp* | Restricts the results to invoices *on or after* the given timestamp
**end_date** *timestamp* | Restricts the results to invoices *on or before* the given timestamp
**tags** *array* | When set only returns invoices that match ANY of these tags. Can be an array or comma-separated list.
