# Metered Billing

Metered billing on Invoiced allows you to bill customers for charges that occur during a billing cycle outside of their ordinary subscription. These charges are called **pending line items**. A pending line item is a [Line Item](#line-item-object) that has been attached to a customer, but not billed yet. Pending line items will be swept up by the next invoice that is triggered for the customer. This happens automatically with subscription invoices or when [triggering an invoice manually](#trigger-an-invoice).

## Create a pending line item

```shell
curl "https://api.invoiced.com/customers/:customer_id/line_items" \
  -u {API_KEY}: \
  -d catalog_item="delivery"
```

```ruby
customer = invoiced.Customer.retrieve("{CUSTOMER_ID}")
customer.line_items.create(
  :catalog_item => "delivery"
)
```

```php
<?php

$customer = $invoiced->Customer->retrieve("{CUSTOMER_ID}");
$customer->lineItems()->create([
  'catalog_item' => "delivery"
]);
```

```python
customer = client.Customer.retrieve("{CUSTOMER_ID}")
customer.line_items().create(
  catalog_item="delivery"
)
```

> The above command returns JSON structured like this:

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
  "discounts": [],
  "taxes": []
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
  "discounts": [],
  "taxes": []
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
  "discounts": [],
  "taxes": []
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
  "discounts": [],
  "taxes": []
}
```

Create a new pending line item with this endpoint.

### HTTP Request

`POST /customers/:customer_id/line_items`

### Attributes

Parameter | Type | Description
--------- | ---- | -----------
**catalog_item** | *string* | Optional Catalog Item ID. Fills the line item with the name and pricing of the Catalog Item.
**type** | *string* | Optional line item type. Used to group line items by type in reporting
**name** | *string* | Title
**description** | *string* | Optional description
**quantity** | *number* | Quantity
**unit_cost** | *number* | Unit cost or rate
**discounts** | *array* | Line item Discounts
**taxes** | *array* | Line item Taxes

## Retrieve a pending line item

```shell
curl "https://api.invoiced.com/customers/:customer_id/line_items/:id" \
  -u {API_KEY}:
```

```ruby
customer = invoiced.Customer.retrieve("{CUSTOMER_ID}")
line_item = customer.line_items.retrieve("{LINE_ITEM_ID}")
```

```php
<?php

$customer = $invoiced->Customer->retrieve("{CUSTOMER_ID}");
$lineItem = $customer->lineItems()->retrieve("{LINE_ITEM_ID}");
```

```python
customer = client.Customer.retrieve("{CUSTOMER_ID}")
line_item = customer.line_items().retrieve("{LINE_ITEM_ID}")
```

> The above command returns JSON structured like this:

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
  "discounts": [],
  "taxes": []
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
  "discounts": [],
  "taxes": []
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
  "discounts": [],
  "taxes": []
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
  "discounts": [],
  "taxes": []
}
```

This endpoint retrieves a specific pending line item.

### HTTP Request

`GET /customers/:customer_id/line_items/:id`

## Update a pending line item

```shell
curl "https://api.invoiced.com/customers/:customer_id/line_items/:id" \
  -u {API_KEY}: \
  -d quantity=2
  -X PATCH
```

```ruby
line_item.quantity = 2
line_item.save
```

```php
<?php

$lineItem->quantity = 2;
$lineItem->save();
```

```python
line_item.quantity = 2
line_item.save()
```

> The above command returns JSON structured like this:

```shell
{
  "id": 8,
  "catalog_item": "delivery",
  "type": "service",
  "name": "Delivery",
  "description": "",
  "quantity": 2,
  "unit_cost": 10,
  "amount": 20,
  "discounts": [],
  "taxes": []
}
```

```ruby
#<Invoiced::LineItem:0x3fdbf95e4d08 id=8> JSON: {
  "id": 8,
  "catalog_item": "delivery",
  "type": "service",
  "name": "Delivery",
  "description": "",
  "quantity": 2,
  "unit_cost": 10,
  "amount": 20,
  "discounts": [],
  "taxes": []
}
```

```php
Invoiced\LineItem JSON: {
  "id": 8,
  "catalog_item": "delivery",
  "type": "service",
  "name": "Delivery",
  "description": "",
  "quantity": 2,
  "unit_cost": 10,
  "amount": 20,
  "discounts": [],
  "taxes": []
}
```

```python
<LineItem id=8 at 0x3fdbf95e4d08> JSON: {
  "id": 8,
  "catalog_item": "delivery",
  "type": "service",
  "name": "Delivery",
  "description": "",
  "quantity": 2,
  "unit_cost": 10,
  "amount": 20,
  "discounts": [],
  "taxes": []
}
```

Use this endpoint to update a pending line item.

### HTTP Request

`PATCH /customers/:customer_id/line_items/:id`

### Request Parameters

Parameter | Type | Description
--------- | ---- | -----------
**type** | *string* | Optional line item type. Used to group line items by type in reporting
**name** | *string* | Title
**description** | *string* | Optional description
**quantity** | *number* | Quantity
**unit_cost** | *number* | Unit cost or rate
**discounts** | *array* | Line item Discounts
**taxes** | *array* | Line item Taxes

## Trigger an invoice

```shell
curl "https://api.invoiced.com/customers/:customer_id/invoices" \
  -u {API_KEY}: \
  -X POST
```

```ruby
invoice = customer.invoice
```

```php
<?php

$invoice = $customer->invoice();
```

```python
invoice = customer.invoice()
```

> The above command returns JSON structured like this:

```shell
{
  "id": 46225,
  "customer": 15444,
  "name": null,
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
      "discounts": [],
      "taxes": []
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
      "discounts": [],
      "taxes": []
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
  "created_at": 1415229884
}
```

```ruby
#<Invoiced::Invoice:0x3fdbf95e4d08 id=f45382c6fbc44d44aa7f9a55eb2ce731> JSON: {
  "id": 46225,
  "customer": 15444,
  "name": null,
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
      "discounts": [],
      "taxes": []
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
      "discounts": [],
      "taxes": []
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
  "created_at": 1415229884
}
```

```php
Invoiced\Invoice JSON: {
  "id": 46225,
  "customer": 15444,
  "name": null,
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
      "discounts": [],
      "taxes": []
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
      "discounts": [],
      "taxes": []
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
  "created_at": 1415229884
}
```

```python
<Invoice id=f45382c6fbc44d44aa7f9a55eb2ce731 at 0x3fdbf95e4d08> JSON: {
  "id": 46225,
  "customer": 15444,
  "name": null,
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
      "discounts": [],
      "taxes": []
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
      "discounts": [],
      "taxes": []
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
  "created_at": 1415229884
}
```

This endpoint generates an invoice for a customer with its pending line items.

### HTTP Request

`POST /customers/:customer_id/invoices`

<aside class="warning">
An invalid request error will be thrown if the customer has no pending line items.
</aside>

## Delete a pending line item

```shell
curl "https://api.invoiced.com/customers/:customer_id/line_items/:id" \
  -u {API_KEY}: \
  -X DELETE
```

```ruby
line_item.delete
```

```php
<?php

$lineItem->delete();
```

```python
line_item.delete()
```

> The above command returns `204 No Content`

This endpoint deletes a specific pending line item.

### HTTP Request

`DELETE /customers/:customer_id/line_items/:id`

## List all pending line items

```shell
curl "https://api.invoiced.com/customers/:customer_id/line_items" \
  -u {API_KEY}:
```

```ruby
customer = invoiced.Customer.retrieve("{CUSTOMER_ID}")
line_items, metadata = customer.line_items.list(:per_page => 3)
```

```php
<?php

$customer = $invoiced->Customer->retrieve("{CUSTOMER_ID}");
list($lineItems, $metadata) = $customer->lineItems()->all(['per_page' => 3]);
```

```python
customer = client.Customer.retrieve("{CUSTOMER_ID}")
line_items, metadata = customer.line_items().list(per_page=3)
```

> The above command returns JSON structured like this:

```shell
[
  {
    "id": 8,
    "catalog_item": "delivery",
    "type": "service",
    "name": "Delivery",
    "description": "",
    "quantity": 1,
    "unit_cost": 10,
    "amount": 10,
    "discounts": [],
    "taxes": []
  },
  { ... },
  { ... }
]
```

```ruby
[
  #<Invoiced::LineItem:0x3fdbf95e4d08 id=8> JSON: {
    "id": 8,
    "catalog_item": "delivery",
    "type": "service",
    "name": "Delivery",
    "description": "",
    "quantity": 1,
    "unit_cost": 10,
    "amount": 10,
    "discounts": [],
    "taxes": []
  },
  #<Invoiced::LineItem:0x3fdbf95e4d09 id=9> JSON: { ... },
  #<Invoiced::LineItem:0x3fdbf95e4d10 id=10> JSON: { ... }
]
```

```php
[
  Invoiced\LineItem JSON: {
    "id": 8,
    "catalog_item": "delivery",
    "type": "service",
    "name": "Delivery",
    "description": "",
    "quantity": 1,
    "unit_cost": 10,
    "amount": 10,
    "discounts": [],
    "taxes": []
  },
  Invoiced\LineItem JSON: { ... },
  Invoiced\LineItem JSON: { ... }
]
```

```python
[
  <LineItem id=8 at 0x3fdbf95e4d08> JSON: {
    "id": 8,
    "catalog_item": "delivery",
    "type": "service",
    "name": "Delivery",
    "description": "",
    "quantity": 1,
    "unit_cost": 10,
    "amount": 10,
    "discounts": [],
    "taxes": []
  },
  <LineItem id=9 at 0x3fdbf95e4d08> JSON: { ... },
  <LineItem id=10 at 0x3fdbf95e4d08> JSON: { ... }
]
```

This endpoint retrieves all pending line items.

### HTTP Request

`GET /customers/:customer_id/line_items`

### Query Parameters

Parameter | Description
--------- | -----------
**sort** *string* | Column to sort by, i.e. `name asc`
**filter** *object* | Filter object
