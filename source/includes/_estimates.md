# Estimates

An estimate provides a quote to a [Customer](#customer-object). Like invoices, each estimate has a collection of line items that detail the products or services. Estimates, unlike invoices, do not have a balance owed until converted to an invoice.

## Estimate Object

### Attributes

```shell
{
  "id": 2048,
  "customer": 15444,
  "invoice": null,
  "name": null,
  "currency": "usd",
  "draft": false,
  "closed": false,
  "paid": false,
  "status": "not_sent",
  "number": "EST-0016",
  "date": 1416290400,
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
  "url": "https://dundermifflin.invoiced.com/estimates/IZmXbVOPyvfD3GPBmyd6FwXY",
  "pdf_url": "https://dundermifflin.invoiced.com/estimates/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
  "created_at": 1415229884,
  "metadata": {}
}
```

```ruby
#<Invoiced::Estimate:0x3fdbf95e4d08 id=2048> JSON: {
  "id": 2048,
  "customer": 15444,
  "invoice": null,
  "name": null,
  "currency": "usd",
  "draft": false,
  "closed": false,
  "paid": false,
  "status": "not_sent",
  "number": "EST-0016",
  "date": 1416290400,
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
  "url": "https://dundermifflin.invoiced.com/estimates/IZmXbVOPyvfD3GPBmyd6FwXY",
  "pdf_url": "https://dundermifflin.invoiced.com/estimates/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
  "created_at": 1415229884,
  "metadata": {}
}
```

```php
Invoiced\Estimate JSON: {
  "id": 2048,
  "customer": 15444,
  "invoice": null,
  "name": null,
  "currency": "usd",
  "draft": false,
  "closed": false,
  "paid": false,
  "status": "not_sent",
  "number": "EST-0016",
  "date": 1416290400,
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
  "url": "https://dundermifflin.invoiced.com/estimates/IZmXbVOPyvfD3GPBmyd6FwXY",
  "pdf_url": "https://dundermifflin.invoiced.com/estimates/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
  "created_at": 1415229884,
  "metadata": {}
}
```

```python
<Estimate id=2048 at 0x3fdbf95e4d08> JSON: {
  "id": 2048,
  "customer": 15444,
  "invoice": null,
  "name": null,
  "currency": "usd",
  "draft": false,
  "closed": false,
  "paid": false,
  "status": "not_sent",
  "number": "EST-0016",
  "date": 1416290400,
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
  "url": "https://dundermifflin.invoiced.com/estimates/IZmXbVOPyvfD3GPBmyd6FwXY",
  "pdf_url": "https://dundermifflin.invoiced.com/estimates/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
  "created_at": 1415229884,
  "metadata": {}
}
```

```java
com.invoiced.entity.Estimate@e48fa2a JSON: {
  "id": 2048,
  "customer": 15444,
  "invoice": null,
  "name": null,
  "currency": "usd",
  "draft": false,
  "closed": false,
  "paid": false,
  "status": "not_sent",
  "chase": false,
  "number": "EST-0016",
  "date": 1416290400,
  "payment_terms": "NET 14",
  "items": [
    {
      "id": 7,
      "type": "product",
      "name": "Copy Paper, Case",
      "quantity": 1,
      "unit_cost": 45,
      "amount": 45,
      "discountable": true,
      "taxable": true,
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
      "taxable": true,
    }
  ],
  "subtotal": 55,
  "taxes": [
    {
      "id": 20554,
      "amount": 3.85,
      "tax_rate": null
    }
  ],
  "total": 51.15,
  "url": "https://dundermifflin.invoiced.com/estimates/IZmXbVOPyvfD3GPBmyd6FwXY",
  "pdf_url": "https://dundermifflin.invoiced.com/estimates/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
  "created_at": 1415229884,
}
```

Parameter | Type | Description
--------- | ---- | -----------
**id** | *integer* | The estimate's unique ID
**customer** | *integer* | Customer ID
**invoice** | *integer* | Invoice ID
**name** | *string* | Estimate name for internal use, defaults to "Estimate"
**number** | *string* | The reference number assigned to the estimate for use in the dashboard
**currency** | *string* | [3-letter ISO code](https://en.wikipedia.org/wiki/ISO_4217)
**draft** | *boolean* | When false, the estimate is considered outstanding, or when true, the estimate is a draft
**closed** | *boolean* | When true, an estimate is closed and considered bad debt. No further payments are allowed.
**paid** | *boolean* | Indicates whether an estimate has been paid in full
**status** | *string* | Estimate state, one of `draft`, `not_sent`, `sent`, `approved`, `invoiced`, `declined`
**date** | *timestamp* | Estimate date
**payment_terms** | *string* | Payment terms for the estimate, i.e. "NET 30"
**items** | *array* | Collection of Line Items
**notes** | *string* | Additional notes displayed on estimate
**subtotal** | *number* | Subtotal
**discounts** | *array* | Collection of Discounts
**taxes** | *array* | Collection of Taxes
**total** | *number* | Total
**url** | *string* | URL to view the estimate in the billing portal
**pdf_url** | *string* | URL to download the estimate as a PDF
**created_at** | *timestamp* | Timestamp when created
**metadata** | *object* | A hash of key/value pairs that can store additional information about this object.

## Create an estimate

```shell
curl "https://api.invoiced.com/estimates" \
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
invoiced.Estimate.create(
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

$estimate = $invoiced->Estimate->create([
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
client.Estimate.create(
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

```java
Estimate estimate = invoiced.newEstimate();
estimate.customer = 15444L;
estimate.paymentTerms = "NET 14";
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
estimate.items = items;
estimate.taxes = taxes;
estimate.create();
```

> The above command returns JSON structured like this:

```shell
{
  "id": 2048,
  "customer": 15444,
  "invoice": null,
  "name": null,
  "currency": "usd",
  "draft": false,
  "closed": false,
  "paid": false,
  "status": "not_sent",
  "number": "EST-0016",
  "date": 1416290400,
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
  "url": "https://dundermifflin.invoiced.com/estimates/IZmXbVOPyvfD3GPBmyd6FwXY",
  "pdf_url": "https://dundermifflin.invoiced.com/estimates/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
  "created_at": 1415229884,
  "metadata": {}
}
```

```ruby
#<Invoiced::Estimate:0x3fdbf95e4d08 id=2048> JSON: {
  "id": 2048,
  "customer": 15444,
  "invoice": null,
  "name": null,
  "currency": "usd",
  "draft": false,
  "closed": false,
  "paid": false,
  "status": "not_sent",
  "number": "EST-0016",
  "date": 1416290400,
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
  "url": "https://dundermifflin.invoiced.com/estimates/IZmXbVOPyvfD3GPBmyd6FwXY",
  "pdf_url": "https://dundermifflin.invoiced.com/estimates/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
  "created_at": 1415229884,
  "metadata": {}
}
```

```php
Invoiced\Estimate JSON: {
  "id": 2048,
  "customer": 15444,
  "invoice": null,
  "name": null,
  "currency": "usd",
  "draft": false,
  "closed": false,
  "paid": false,
  "status": "not_sent",
  "number": "EST-0016",
  "date": 1416290400,
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
  "url": "https://dundermifflin.invoiced.com/estimates/IZmXbVOPyvfD3GPBmyd6FwXY",
  "pdf_url": "https://dundermifflin.invoiced.com/estimates/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
  "created_at": 1415229884,
  "metadata": {}
}
```

```python
<Estimate id=2048 at 0x3fdbf95e4d08> JSON: {
  "id": 2048,
  "customer": 15444,
  "invoice": null,
  "name": null,
  "currency": "usd",
  "draft": false,
  "closed": false,
  "paid": false,
  "status": "not_sent",
  "number": "EST-0016",
  "date": 1416290400,
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
  "url": "https://dundermifflin.invoiced.com/estimates/IZmXbVOPyvfD3GPBmyd6FwXY",
  "pdf_url": "https://dundermifflin.invoiced.com/estimates/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
  "created_at": 1415229884,
  "metadata": {}
}
```

```java
com.invoiced.entity.Estimate@e48fa2a JSON: {
  "id": 2048,
  "customer": 15444,
  "invoice": null,
  "currency": "usd",
  "draft": false,
  "closed": false,
  "paid": false,
  "status": "not_sent",
  "chase": false,
  "number": "EST-0016",
  "date": 1416290400,
  "payment_terms": "NET 14",
  "items": [
    {
      "id": 7,
      "type": "product",
      "name": "Copy Paper, Case",
      "quantity": 1,
      "unit_cost": 45,
      "amount": 45,
      "discountable": true,
      "taxable": true
    },
    {
      "id": 8,
      "catalog_item": "delivery",
      "type": "service",
      "name": "Delivery",
      "quantity": 1,
      "unit_cost": 10,
      "amount": 10,
      "discountable": true,
      "taxable": true
    }
  ],
  "subtotal": 55,
  "taxes": [
    {
      "id": 20554,
      "amount": 3.85,
      "tax_rate": null
    }
  ],
  "total": 51.15,
  "url": "https://dundermifflin.invoiced.com/estimates/IZmXbVOPyvfD3GPBmyd6FwXY",
  "pdf_url": "https://dundermifflin.invoiced.com/estimates/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
  "created_at": 1415229884
}
```

Create a new estimate with this endpoint.

### HTTP Request

`POST /estimates`

### Attributes

Parameter | Type | Description
--------- | ---- | -----------
**customer** | *integer* | Customer ID - **required**
**invoice** | *integer* | Invoice ID
**name** | *string* | Estimate name for internal use, defaults to "Estimate"
**number** | *string* | The reference number assigned to the estimate, defaults to next # in auto-numbering sequence
**currency** | *string* | [3-letter ISO code](https://en.wikipedia.org/wiki/ISO_4217) - defaults to account currency
**date** | *timestamp* | Estimate date - defaults to current timestamp
**payment_terms** | *string* | Payment terms for the estimate, i.e. "NET 30"
**draft** | *boolean* | When false, the estimate is considered outstanding, or when true, the estimate is a draft
**closed** | *boolean* | Marks an estimate as closed
**items** | *array* | Collection of Line Items
**notes** | *string* | Additional notes displayed on estimate
**discounts** | *array* | Collection of Discounts
**taxes** | *array* | Collection of Taxes
**metadata** | *object* | A hash of key/value pairs that can store additional information about this object.
**attachments** | *array* | A list of [File](#file-object) IDs to attach to the estimate

## Retrieve an estimate

```shell
curl "https://api.invoiced.com/estimates/:id" \
  -u {API_KEY}:
```

```ruby
estimate = invoiced.Estimate.retrieve("{ESTOICE_ID}")
```

```php
<?php

$estimate = $invoiced->Estimate->retrieve("{ESTOICE_ID}");
```

```python
estimate = client.Estimate.retrieve("{ESTOICE_ID}")
```

```java
Estimate estimate = invoiced.newEstimate().retrieve({ESTOICE_ID});
```

> The above command returns JSON structured like this:

```shell
{
  "id": 2048,
  "customer": 15444,
  "invoice": null,
  "name": null,
  "currency": "usd",
  "draft": false,
  "closed": false,
  "paid": false,
  "status": "not_sent",
  "number": "EST-0016",
  "date": 1416290400,
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
  "url": "https://dundermifflin.invoiced.com/estimates/IZmXbVOPyvfD3GPBmyd6FwXY",
  "pdf_url": "https://dundermifflin.invoiced.com/estimates/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
  "created_at": 1415229884,
  "metadata": {}
}
```

```ruby
#<Invoiced::Estimate:0x3fdbf95e4d08 id=2048> JSON: {
  "id": 2048,
  "customer": 15444,
  "invoice": null,
  "name": null,
  "currency": "usd",
  "draft": false,
  "closed": false,
  "paid": false,
  "status": "not_sent",
  "number": "EST-0016",
  "date": 1416290400,
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
  "url": "https://dundermifflin.invoiced.com/estimates/IZmXbVOPyvfD3GPBmyd6FwXY",
  "pdf_url": "https://dundermifflin.invoiced.com/estimates/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
  "created_at": 1415229884,
  "metadata": {}
}
```

```php
Invoiced\Estimate JSON: {
  "id": 2048,
  "customer": 15444,
  "invoice": null,
  "name": null,
  "currency": "usd",
  "draft": false,
  "closed": false,
  "paid": false,
  "status": "not_sent",
  "number": "EST-0016",
  "date": 1416290400,
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
  "url": "https://dundermifflin.invoiced.com/estimates/IZmXbVOPyvfD3GPBmyd6FwXY",
  "pdf_url": "https://dundermifflin.invoiced.com/estimates/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
  "created_at": 1415229884,
  "metadata": {}
}
```

```python
<Estimate id=2048 at 0x3fdbf95e4d08> JSON: {
  "id": 2048,
  "customer": 15444,
  "invoice": null,
  "name": null,
  "currency": "usd",
  "draft": false,
  "closed": false,
  "paid": false,
  "status": "not_sent",
  "number": "EST-0016",
  "date": 1416290400,
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
  "url": "https://dundermifflin.invoiced.com/estimates/IZmXbVOPyvfD3GPBmyd6FwXY",
  "pdf_url": "https://dundermifflin.invoiced.com/estimates/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
  "created_at": 1415229884,
  "metadata": {}
}
```

```java
com.invoiced.entity.Estimate@e48fa2a JSON: {
  "id": 2048,
  "customer": 15444,
  "invoice": null,
  "name": null,
  "currency": "usd",
  "draft": false,
  "closed": false,
  "paid": false,
  "status": "not_sent",
  "number": "EST-0016",
  "date": 1416290400,
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
  "url": "https://dundermifflin.invoiced.com/estimates/IZmXbVOPyvfD3GPBmyd6FwXY",
  "pdf_url": "https://dundermifflin.invoiced.com/estimates/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
  "created_at": 1415229884,
  "metadata": {}
}
```

This endpoint retrieves a specific estimate.

### HTTP Request

`GET /estimates/:id`

### Query Parameters

Parameter | Type | Description
--------- | ---- | -----------
**expand** | *string* | Properties to expand

## Update an estimate

```shell
curl "https://api.invoiced.com/estimates/:id" \
  -u {API_KEY}: \
  -X PATCH \
  -d sent=1 \
  -d chase=1
```

```ruby
estimate.name = "July Paper Delivery"
estimate.notes = "The order was delivered on Jul 20, 2015"
estimate.sent = true
estimate.save
```

```php
<?php

$estimate->name = "July Paper Delivery";
$estimate->notes = "The order was delivered on Jul 20, 2015";
$estimate->sent = true;
$estimate->save();
```

```python
estimate.name = "July Paper Delivery"
estimate.notes = "The order was delivered on Jul 20, 2015"
estimate.sent = True
estimate.save()
```

```java
estimate.name =  "July Paper Delivery";
estimate.notes = "The order was delivered on Jul 20, 2015";
estimate.sent = true;
estimate.save();
```

> The above command returns JSON structured like this:

```shell
{
  "id": 2048,
  "customer": 15444,
  "invoice": null,
  "name": "July Paper Delivery",
  "currency": "usd",
  "draft": false,
  "closed": false,
  "paid": false,
  "status": "sent",
  "number": "EST-0016",
  "date": 1416290400,
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
  "url": "https://dundermifflin.invoiced.com/estimates/IZmXbVOPyvfD3GPBmyd6FwXY",
  "pdf_url": "https://dundermifflin.invoiced.com/estimates/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
  "created_at": 1415229884,
  "metadata": {}
}
```

```ruby
#<Invoiced::Estimate:0x3fdbf95e4d08 id=2048> JSON: {
  "id": 2048,
  "customer": 15444,
  "invoice": null,
  "name": null,
  "currency": "usd",
  "draft": false,
  "closed": false,
  "paid": false,
  "status": "not_sent",
  "number": "EST-0016",
  "date": 1416290400,
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
  "url": "https://dundermifflin.invoiced.com/estimates/IZmXbVOPyvfD3GPBmyd6FwXY",
  "pdf_url": "https://dundermifflin.invoiced.com/estimates/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
  "created_at": 1415229884,
  "metadata": {}
}
```

```php
Invoiced\Estimate JSON: {
  "id": 2048,
  "customer": 15444,
  "invoice": null,
  "name": null,
  "currency": "usd",
  "draft": false,
  "closed": false,
  "paid": false,
  "status": "not_sent",
  "number": "EST-0016",
  "date": 1416290400,
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
  "url": "https://dundermifflin.invoiced.com/estimates/IZmXbVOPyvfD3GPBmyd6FwXY",
  "pdf_url": "https://dundermifflin.invoiced.com/estimates/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
  "created_at": 1415229884,
  "metadata": {}
}
```

```python
<Estimate id=2048 at 0x3fdbf95e4d08> JSON: {
  "id": 2048,
  "customer": 15444,
  "invoice": null,
  "name": null,
  "currency": "usd",
  "draft": false,
  "closed": false,
  "paid": false,
  "status": "not_sent",
  "number": "EST-0016",
  "date": 1416290400,
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
  "url": "https://dundermifflin.invoiced.com/estimates/IZmXbVOPyvfD3GPBmyd6FwXY",
  "pdf_url": "https://dundermifflin.invoiced.com/estimates/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
  "created_at": 1415229884,
  "metadata": {}
}
```

```java
com.invoiced.entity.Estimate@e48fa2a JSON: {
  "id": 2048,
  "customer": 15444,
  "invoice": null,
  "name": null,
  "currency": "usd",
  "draft": false,
  "closed": false,
  "paid": false,
  "status": "not_sent",
  "number": "EST-0016",
  "date": 1416290400,
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
  "url": "https://dundermifflin.invoiced.com/estimates/IZmXbVOPyvfD3GPBmyd6FwXY",
  "pdf_url": "https://dundermifflin.invoiced.com/estimates/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
  "created_at": 1415229884,
  "metadata": {}
}
```

Use this endpoint to update an estimate.

### HTTP Request

`PATCH /estimates/:id`

### Attributes

Parameter | Type | Description
--------- | ---- | -----------
**name** | *string* | Estimate name for internal use, defaults to "Estimate"
**number** | *string* | The reference number assigned to the estimate, defaults to next # in auto-numbering sequence
**currency** | *string* | [3-letter ISO code](https://en.wikipedia.org/wiki/ISO_4217) - defaults to account currency
**date** | *timestamp* | Estimate date - defaults to current timestamp
**payment_terms** | *string* | Payment terms for the estimate, i.e. "NET 30"
**draft** | *boolean* | When false, the estimate is considered outstanding, or when true, the invoice is a draft
**closed** | *boolean* | Marks an estimate as closed
**items** | *array* | Collection of Line Items
**notes** | *string* | Additional notes displayed on estimate
**discounts** | *array* | Collection of Discounts
**taxes** | *array* | Collection of Taxes
**metadata** | *object* | A hash of key/value pairs that can store additional information about this object.
**attachments** | *array* | A list of [File](#file-object) IDs to attach to the estimate. Replaces existing attachments. Not providing this keeps existing attachments.

## Send an estimate

```shell
curl "https://api.invoiced.com/estimates/:id/emails" \
  -u {API_KEY}: \
  -X POST
```

```ruby
emails = estimate.send
```

```php
<?php

$emails = $estimate->send();
```

```python
emails = estimate.send()
```

```java
EmailRequest emailRequest = new EmailRequest();
EmailRecipient[] emailRecipients = new EmailRecipient[1];
emailRecipients[0] = new EmailRecipient();
emailRecipients[0].name = "Client";
emailRecipients[0].email = "client@example.com";

emailRequest.to = emailRecipients;
emailRequest.subject = "New Estimate from Dunder Mifflin, Inc.: EST-0016";
emailRequest.message = "Dear Client, a new estimate for $51.15 has been created on your account. Thank you!";

Email[] emails = estimate.send(emailRequest);
```

> The above command returns JSON structured like this:

```shell
[
  {
    "id": "f45382c6fbc44d44aa7f9a55eb2ce731",
    "state": "sent",
    "reject_reason": null,
    "email": "client@example.com",
    "template": "estimate_email",
    "subject": "New Estimate from Dunder Mifflin, Inc.: EST-0016",
    "message": "Dear Client, a new estimate for $51.15 has been created on your account. Thank you!",
    "not_sents": 0,
    "not_sents_detail": [],
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
    "template": "estimate_email",
    "subject": "New Estimate from Dunder Mifflin, Inc.: EST-0016",
    "message": "Dear Client, a new estimate for $51.15 has been created on your account. Thank you!",
    "not_sents": 0,
    "not_sents_detail": [],
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
    "template": "estimate_email",
    "subject": "New Estimate from Dunder Mifflin, Inc.: EST-0016",
    "message": "Dear Client, a new estimate for $51.15 has been created on your account. Thank you!",
    "not_sents": 0,
    "not_sents_detail": [],
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
    "template": "estimate_email",
    "subject": "New Estimate from Dunder Mifflin, Inc.: EST-0016",
    "message": "Dear Client, a new estimate for $51.15 has been created on your account. Thank you!",
    "not_sents": 0,
    "not_sents_detail": [],
    "clicks": 0,
    "clicks_detail": [],
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
    "state": "sent",
    "email": "client@example.com",
    "template": "estimate_email",
    "subject": "New Estimate from Dunder Mifflin, Inc.: EST-0016",
    "message": "Dear Client, a new estimate for $51.15 has been created on your account. Thank you!",
    "created_at": 1436890047
    },
  com.invoiced.entity.Email@3ce1cfd8 JSON: {...},
  com.invoiced.entity.Email@4ce1cfd8 JSON: {...}
]
```

This endpoint sends an estimate to your customer.

### HTTP Request

`POST /estimates/:id/emails`

### Request Parameters

Parameter | Type | Description
--------- | ---- | -----------
**to** | *array* | Optional array of recipients like:<br/>`[{"name": "Client", "email": "client@example.com"}]`
**bcc** | *string* | Optional comma-separated list of email addresses to be blind carbon copied
**subject** | *string* | Optional subject
**message** | *string* | Optional message body, otherwise the appropriate estimate template is used

<aside class="info">
A successful response means that your email has been added to the send queue.
</aside>

## Generate an invoice

```shell
curl "https://api.invoiced.com/estimates/:estimate_id/invoices" \
  -u {API_KEY}: \
  -X POST
```

```ruby
invoice = estimate.invoice
```

```php
<?php

$invoice = $estimate->invoice();
```

```python
invoice = estimate.invoice()
```

```java
Invoice invoice = estimate.invoice();
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
  "url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY",
  "payment_url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY/payment",
  "pdf_url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
  "created_at": 1415229884,
  "metadata": {}
}
```

```ruby
#<Invoiced::Invoice:0x3fdbf95e4d08 id=f45382c6fbc44d44aa7f9a55eb2ce731> JSON: {
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
  "url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY",
  "payment_url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY/payment",
  "pdf_url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
  "created_at": 1415229884,
  "metadata": {}
}
```

```python
<Invoice id=f45382c6fbc44d44aa7f9a55eb2ce731 at 0x3fdbf95e4d08> JSON: {
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
  "url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY",
  "payment_url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY/payment",
  "pdf_url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
  "created_at": 1415229884,
  "metadata": {}
}
```

```java 
com.invoiced.entity.Invoice@3df85de JSON: {
  "id": 46225,
  "customer": 15444,
  "currency": "usd",
  "draft": false,
  "closed": false,
  "paid": false,
  "status": "not_sent",
  "chase": false,
  "collection_mode": "manual",
  "attempt_count": 0,
  "number": "INV-0016",
  "date": 1416290400,
  "due_date": 1417500000,
  "payment_terms": "NET 14",
  "items": [
    {
      "id": 7,
      "type": "product",
      "name": "Copy Paper, Case",
      "quantity": 1,
      "unit_cost": 45,
      "amount": 45,
      "discountable": true,
      "taxable": true,
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
      "taxable": true,
    }
  ],
  "subtotal": 55,
  "taxes": [
    {
      "id": 20554,
      "amount": 3.85,
      "tax_rate": null
    }
  ],
  "total": 51.15,
  "balance": 51.15,
  "url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY",
  "payment_url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY/payment",
  "pdf_url": "https://dundermifflin.invoiced.com/invoices/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
  "created_at": 1415229884,
}
```

This endpoint generates an invoice from an estimate.

### HTTP Request

`POST /estimates/:estimate_id/invoices`

## List estimate attachments

```shell
curl "https://api.invoiced.com/estimates/:id/attachments" \
  -u {API_KEY}:
```

```ruby
attachments, metadata = estimate.attachments
```

```php
<?php

list($attachments, $metadata) = $estimate->attachments();
```

```python
attachments, metadata = estimate.attachments()
```

```java
Attachment[] attachments = estimate.listAttachments();
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

```java
[
  com.invoiced.entity.Attachment@1759eafd JSON: {
    "id": 13,
    "file": {
      "id": 13,
      "name": "logo-invoice.png",
      "object": "file",
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

This endpoint retrieves a list of files attached to a specific estimate.

### HTTP Request

`GET /estimates/:id/attachments`

## Delete an estimate

```shell
curl "https://api.invoiced.com/estimates/:id" \
  -u {API_KEY}: \
  -X DELETE
```

```ruby
estimate.delete
```

```php
<?php

$estimate->delete();
```

```python
estimate.delete()
```

```java
estimate.delete();
```

> The above command returns `204 No Content`

This endpoint deletes a specific estimate.

### HTTP Request

`DELETE /estimates/:id`

## List all estimates

```shell
curl "https://api.invoiced.com/estimates" \
  -u {API_KEY}:
```

```ruby
estimates, metadata = invoiced.Estimate.list(:per_page => 3)
```

```php
<?php

list($estimates, $metadata) = $invoiced->Estimate->all(['per_page' => 3]);
```

```python
estimates, metadata = invoiced.Estimate.list(per_page=3)
```

```java
EntityList<Estimate> estimates = conn.newEstimate().listAll();
```

> The above command returns JSON structured like this:

```shell
[
  {
    "id": 2048,
    "customer": 15444,
    "invoice": null,
    "name": null,
    "currency": "usd",
    "draft": false,
    "closed": false,
    "paid": false,
    "status": "not_sent",
    "number": "EST-0016",
    "date": 1416290400,
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
    "url": "https://dundermifflin.invoiced.com/estimates/IZmXbVOPyvfD3GPBmyd6FwXY",
    "pdf_url": "https://dundermifflin.invoiced.com/estimates/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
    "created_at": 1415229884,
    "metadata": {}
  },
  { ... },
  { ... }
]
```

```ruby
[
  #<Invoiced::Estimate:0x3fdbf95e4d08 id=2048> JSON: {
    "id": 2048,
    "customer": 15444,
    "invoice": null,
    "name": null,
    "currency": "usd",
    "draft": false,
    "closed": false,
    "paid": false,
    "status": "not_sent",
    "number": "EST-0016",
    "date": 1416290400,
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
    "url": "https://dundermifflin.invoiced.com/estimates/IZmXbVOPyvfD3GPBmyd6FwXY",
    "pdf_url": "https://dundermifflin.invoiced.com/estimates/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
    "created_at": 1415229884,
    "metadata": {}
  },
  #<Invoiced::Estimate:0x3fdbf95e4d09 id=15445> JSON: { ... },
  #<Invoiced::Estimate:0x3fdbf95e4d10 id=15446> JSON: { ... }
]
```

```php
[
  Invoiced\Estimate JSON: {
    "id": 2048,
    "customer": 15444,
    "invoice": null,
    "name": null,
    "currency": "usd",
    "draft": false,
    "closed": false,
    "paid": false,
    "status": "not_sent",
    "number": "EST-0016",
    "date": 1416290400,
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
    "url": "https://dundermifflin.invoiced.com/estimates/IZmXbVOPyvfD3GPBmyd6FwXY",
    "pdf_url": "https://dundermifflin.invoiced.com/estimates/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
    "created_at": 1415229884,
    "metadata": {}
  },
  Invoiced\Estimate JSON: { ... },
  Invoiced\Estimate JSON: { ... }
]
```

```python
[
  <Estimate id=2048 at 0x3fdbf95e4d08> JSON: {
    "id": 2048,
    "customer": 15444,
    "invoice": null,
    "name": null,
    "currency": "usd",
    "draft": false,
    "closed": false,
    "paid": false,
    "status": "not_sent",
    "number": "EST-0016",
    "date": 1416290400,
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
    "url": "https://dundermifflin.invoiced.com/estimates/IZmXbVOPyvfD3GPBmyd6FwXY",
    "pdf_url": "https://dundermifflin.invoiced.com/estimates/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
    "created_at": 1415229884,
    "metadata": {}
  },
  <Estimate id=15445 at 0x3fdbf95e4d08> JSON: { ... },
  <Estimate id=15446 at 0x3fdbf95e4d08> JSON: { ... }
]
```

```java
[
  com.invoiced.entity.Estimate@c509a57 JSON: {
    "id": 2048,
    "customer": 15444,
    "invoice": null,
    "number": "EST-0016",
    "currency": "usd",
    "draft": false,
    "closed": false,
    "paid": false,
    "status": "not_sent",
    "sent": false,
    "chase": false,
    "date": 1416290400,
    "payment_terms": "NET 14",
    "items": [ {
      "id": 7,
      "type": "product",
      "name": "Copy Paper, Case",
      "quantity": 1.0,
      "unit_cost": 45.0,
      "amount": 45.0,
      "discountable": true,
      "taxable": true
    }, {
      "id": 8,
      "catalog_item": "delivery",
      "type": "service",
      "name": "Delivery",
      "quantity": 1.0,
      "unit_cost": 10.0,
      "amount": 10.0,
      "discountable": true,
      "taxable": true
    } ],
    "subtotal": 55.0,
    "taxes": [ {
      "id": 20554,
      "amount": 3.85
    } ],
    "total": 51.15,
    "url": "https://dundermifflin.invoiced.com/estimates/IZmXbVOPyvfD3GPBmyd6FwXY",
    "pdf_url": "https://dundermifflin.invoiced.com/estimates/IZmXbVOPyvfD3GPBmyd6FwXY/pdf",
    "created_at": 1415229884
  }, 
  com.invoiced.entity.Estimate@20301171 JSON: {...},
  com.invoiced.entity.Estimate@30301171 JSON: {...}
]
```

This endpoint retrieves all estimates.

### HTTP Request

`GET /estimates`

### Query Parameters

Parameter | Description
--------- | -----------
**sort** *string* | Column to sort by, i.e. `name asc`
**filter** *object* | Filter object
**metadata** *object* | Metadata filter object
**start_date** *timestamp* | Restricts the results to estimates *on or after* the given timestamp
**end_date** *timestamp* | Restricts the results to estimates *on or before* the given timestamp
