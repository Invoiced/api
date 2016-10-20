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

```java
Customer customer = invoiced.newCustomer().retrieve({CUSTOMER_ID});
PendingLineItem pli = customer.newPendingLineItem();
pli.catalogItem = "delivery";
pli.create();
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

```java
com.invoiced.entity.PendingLineItem@754f2c43 JSON: {
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
**discountable** | *boolean* | Excludes amount from invoice discounts when `false`, defaults to `true
**discounts** | *array* | Line item Discounts
**taxable** | *boolean* | Excludes amount from invoice taxes when `false`, defaults to `true
**taxes** | *array* | Line item Taxes
**metadata** | *object* | A hash of key/value pairs that can store additional information about this object.

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

```java
Customer customer = invoiced.newCustomer().retrieve({CUSTOMER_ID});
PendingLineItem pli = customer.newPendingLineItem().retrieve({LINE_ITEM_ID});
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

```java
com.invoiced.entity.PendingLineItem@754f2c43 JSON: {
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
```

This endpoint retrieves a specific pending line item.

### HTTP Request

`GET /customers/:customer_id/line_items/:id`

## Update a pending line item

```shell
curl "https://api.invoiced.com/customers/:customer_id/line_items/:id" \
  -u {API_KEY}: \
  -d quantity=2 \
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

```java
PendingLineItem pli = customer.newPendingLineItem().retrieve({LINE_ITEM_ID});
pli.quantity = 2;
pli.save();
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
  "quantity": 2,
  "unit_cost": 10,
  "amount": 20,
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
  "quantity": 2,
  "unit_cost": 10,
  "amount": 20,
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
  "quantity": 2,
  "unit_cost": 10,
  "amount": 20,
  "discountable": true,
  "discounts": [],
  "taxable": true,
  "taxes": [],
  "metadata": {}
}
```

```java
com.invoiced.entity.PendingLineItem@754f2c43 JSON: {
  "id": 8,
  "catalog_item": "delivery",
  "type": "service",
  "name": "Delivery",
  "description": "",
  "quantity": 2,
  "unit_cost": 10,
  "amount": 20,
  "discountable": true,
  "taxable": true
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
**discountable** | *boolean* | Excludes amount from invoice discounts when `false`, defaults to `true
**discounts** | *array* | Line item Discounts
**taxable** | *boolean* | Excludes amount from invoice taxes when `false`, defaults to `true
**taxes** | *array* | Line item Taxes
**metadata** | *object* | A hash of key/value pairs that can store additional information about this object.

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

```java
Invoice invoice = customer.invoice();
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
  "tags": [],
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

```java
PendingLineItem pli = customer.newPendingLineItem().retrieve({LINE_ITEM_ID});
pli.delete();
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

```java
PendingLineItem pli = customer.newPendingLineItem();
EntityList<PendingLineItem> plis = pli.listAll();
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
    "discountable": true,
    "discounts": [],
    "taxable": true,
    "taxes": [],
    "metadata": {}
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
    "discountable": true,
    "discounts": [],
    "taxable": true,
    "taxes": [],
    "metadata": {}
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
    "discountable": true,
    "discounts": [],
    "taxable": true,
    "taxes": [],
    "metadata": {}
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
    "discountable": true,
    "discounts": [],
    "taxable": true,
    "taxes": [],
    "metadata": {}
  },
  <LineItem id=9 at 0x3fdbf95e4d08> JSON: { ... },
  <LineItem id=10 at 0x3fdbf95e4d08> JSON: { ... }
]
```

```java
[
  com.invoiced.entity.PendingLineItem@5dac2ea1 JSON: {
    "id" : 8,
    "catalog_item" : "delivery",
    "type" : "service",
    "name" : "Delivery",
    "quantity" : 1.0,
    "amount" : 10.0,
    "unit_cost" : 10.0,
    "discountable" : true,
    "taxable" : true
  }, 
  com.invoiced.entity.PendingLineItem@4e7a0117 JSON: {...},
  com.invoiced.entity.PendingLineItem@4e7a01a7 JSON: {...}]
```

This endpoint retrieves all pending line items.

### HTTP Request

`GET /customers/:customer_id/line_items`

### Query Parameters

Parameter | Description
--------- | -----------
**sort** *string* | Column to sort by, i.e. `name asc`
**filter** *object* | Filter object
**metadata** *object* | Metadata filter object
