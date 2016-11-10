# Pricing Catalog

Your pricing catalog describes the products and services you sell.

## Catalog Item Object

A catalog item represents a product or service that you sell. Catalog items can be used to generate [line items](#line-item-object) and can also be used as [subscription addons](#subscription-addon-object).

### Attributes

```shell
{
  "id": "delivery",
  "object": "catalog_item",
  "name": "Delivery",
  "currency": "usd",
  "unit_cost": 100,
  "description": null,
  "type": "service",
  "taxes": [],
  "discountable": true,
  "taxable": true,
  "unit_cost": 10,
  "created_at": 1477327516,
  "metadata": {}
}
```

```ruby
#<Invoiced::CatalogItem:0x3fdbf95e4d08 id=delivery> JSON: {
  "id": "delivery",
  "object": "catalog_item",
  "name": "Delivery",
  "currency": "usd",
  "unit_cost": 100,
  "description": null,
  "type": "service",
  "taxes": [],
  "discountable": true,
  "taxable": true,
  "unit_cost": 10,
  "created_at": 1477327516,
  "metadata": {}
}
```

```php
Invoiced\CatalogItem JSON: {
  "id": "delivery",
  "object": "catalog_item",
  "name": "Delivery",
  "currency": "usd",
  "unit_cost": 100,
  "description": null,
  "type": "service",
  "taxes": [],
  "discountable": true,
  "taxable": true,
  "unit_cost": 10,
  "created_at": 1477327516,
  "metadata": {}
}
```

```python
<CatalogItem id=delivery at 0x3fdbf95e4d08> JSON: {
  "id": "delivery",
  "object": "catalog_item",
  "name": "Delivery",
  "currency": "usd",
  "unit_cost": 100,
  "description": null,
  "type": "service",
  "taxes": [],
  "discountable": true,
  "taxable": true,
  "unit_cost": 10,
  "created_at": 1477327516,
  "metadata": {}
}
```

```java
com.invoiced.entity.CatalogItem@192cafae JSON: {
  "id": "delivery",
  "object": "catalog_item",
  "name": "Delivery",
  "currency": "usd",
  "unit_cost": 100,
  "description": null,
  "type": "service",
  "taxes": [],
  "discountable": true,
  "taxable": true,
  "unit_cost": 10,
  "created_at": 1477327516,
  "metadata": {}
}
```

Parameter | Type | Description
--------- | ---- | -----------
**id** | *integer* | The catalog item's unique ID
**object** | *string* | `catalog_item`
**name** | *string* | Catalog item name
**currency** | *string* | [3-letter ISO code](https://en.wikipedia.org/wiki/ISO_4217)
**unit_cost** | *number* | Unit cost or rate
**description** | *string* | Optional description
**type** | *string* | Optional line item type. Used to group line items by type in reporting
**taxes** | *array* | Collection of Tax Rate Objects
**discountable** | *boolean* | Excludes amount from discounts when `false`
**taxable** | *boolean* | Excludes amount from taxes when `false`
**created_at** | *timestamp* | Timestamp when created
**metadata** | *object* | A hash of key/value pairs that can store additional information about this object.

## Plan Object

A plan describes a fixed amount that is billed to customers over a recurring interval. Used with [subscriptions](#subscription-object).

### Attributes

```shell
{
  "id": "starter",
  "object": "plan",
  "name": "Starter",
  "currency": "usd",
  "amount": 49,
  "interval": "month",
  "interval_count": 1,
  "created_at": 1477418268,
  "metadata": {}
}
```

```ruby
#<Invoiced::Plan:0x3fdbf95e4d08 id=starter> JSON: {
  "id": "starter",
  "object": "plan",
  "name": "Starter",
  "currency": "usd",
  "amount": 49,
  "interval": "month",
  "interval_count": 1,
  "created_at": 1477418268,
  "metadata": {}
}
```

```php
Invoiced\Plan JSON: {
  "id": "starter",
  "object": "plan",
  "name": "Starter",
  "currency": "usd",
  "amount": 49,
  "interval": "month",
  "interval_count": 1,
  "created_at": 1477418268,
  "metadata": {}
}
```

```python
<Plan id=starter at 0x3fdbf95e4d08> JSON: {
  "id": "starter",
  "object": "plan",
  "name": "Starter",
  "currency": "usd",
  "amount": 49,
  "interval": "month",
  "interval_count": 1,
  "created_at": 1477418268,
  "metadata": {}
}
```

```java
com.invoiced.entity.Plan@192cafae JSON: {
  "id": "starter",
  "object": "plan",
  "name": "Starter",
  "currency": "usd",
  "amount": 49,
  "interval": "month",
  "interval_count": 1,
  "created_at": 1477418268,
  "metadata": {}
}
```

Parameter | Type | Description
--------- | ---- | -----------
**id** | *integer* | The plan's unique ID
**object** | *string* | `plan`
**name** | *string* | Plan name
**currency** | *string* | [3-letter ISO code](https://en.wikipedia.org/wiki/ISO_4217)
**amount** | *number* | Plan amount
**interval** | *string* | One of `day`, `week`, `month`, `year`. The frequency with which a subscription should be billed.
**interval_count** | *number* | The number of intervals between each subscription billing. Defaults to `1`.
**description** | *string* | Optional description
**created_at** | *timestamp* | Timestamp when created
**metadata** | *object* | A hash of key/value pairs that can store additional information about this object.

## Tax Rate Object

A tax rate describes a tax that customers should be charged. Tax rates can be applied to [invoices](#invoice-object), [line items](#line-item-object), and [subscriptions](#subscription-object).

### Attributes

```shell
{
  "id": "vat",
  "object": "tax_rate",
  "name": "VAT",
  "currency": null,
  "value": 5,
  "is_percent": true,
  "created_at": 1477418268,
  "metadata": {}
}
```

```ruby
#<Invoiced::TaxRate:0x3fdbf95e4d08 id=vat> JSON: {
  "id": "vat",
  "object": "tax_rate",
  "name": "VAT",
  "currency": null,
  "value": 5,
  "is_percent": true,
  "created_at": 1477418268,
  "metadata": {}
}
```

```php
Invoiced\TaxRate JSON: {
  "id": "vat",
  "object": "tax_rate",
  "name": "VAT",
  "currency": null,
  "value": 5,
  "is_percent": true,
  "created_at": 1477418268,
  "metadata": {}
}
```

```python
<TaxRate id=vat at 0x3fdbf95e4d08> JSON: {
  "id": "vat",
  "object": "tax_rate",
  "name": "VAT",
  "currency": null,
  "value": 5,
  "is_percent": true,
  "created_at": 1477418268,
  "metadata": {}
}
```

```java
com.invoiced.entity.TaxRate@192cafae JSON: {
  "id": "vat",
  "object": "tax_rate",
  "name": "VAT",
  "currency": null,
  "value": 5,
  "is_percent": true,
  "created_at": 1477418268,
  "metadata": {}
}
```

Parameter | Type | Description
--------- | ---- | -----------
**id** | *integer* | The tax rate's unique ID
**object** | *string* | `tax_rate`
**name** | *string* | Tax rate name
**currency** | *string* | [3-letter ISO code](https://en.wikipedia.org/wiki/ISO_4217)
**value** | *number* | Amount
**is_percent** | *boolean* | When true the value is a %
**created_at** | *timestamp* | Timestamp when created
**metadata** | *object* | A hash of key/value pairs that can store additional information about this object.

## Coupon Object

A coupon describes a discount that can be applied to [invoices](#invoice-object), [line items](#line-item-object), and [subscriptions](#subscription-object).

### Attributes

```shell
{
  "id": "S8L47J",
  "object": "coupon",
  "name": "Non-profit Discount",
  "currency": null,
  "value": 20,
  "is_percent": true,
  "created_at": 1477415090,
  "metadata": {}
}
```

```ruby
#<Invoiced::Coupon:0x3fdbf95e4d08 id=S8L47J> JSON: {
  "id": "S8L47J",
  "object": "coupon",
  "name": "Non-profit Discount",
  "currency": null,
  "value": 20,
  "is_percent": true,
  "created_at": 1477415090,
  "metadata": {}
}
```

```php
Invoiced\Coupon JSON: {
  "id": "S8L47J",
  "object": "coupon",
  "name": "Non-profit Discount",
  "currency": null,
  "value": 20,
  "is_percent": true,
  "created_at": 1477415090,
  "metadata": {}
}
```

```python
<Coupon id=S8L47J at 0x3fdbf95e4d08> JSON: {
  "id": "S8L47J",
  "object": "coupon",
  "name": "Non-profit Discount",
  "currency": null,
  "value": 20,
  "is_percent": true,
  "created_at": 1477415090,
  "metadata": {}
}
```

```java
com.invoiced.entity.Coupon@192cafae JSON: {
  "id": "S8L47J",
  "object": "coupon",
  "name": "Non-profit Discount",
  "currency": null,
  "value": 20,
  "is_percent": true,
  "created_at": 1477415090,
  "metadata": {}
}
```

Parameter | Type | Description
--------- | ---- | -----------
**id** | *integer* | The coupon's unique ID
**object** | *string* | `coupon`
**name** | *string* | Coupon name
**currency** | *string* | [3-letter ISO code](https://en.wikipedia.org/wiki/ISO_4217)
**value** | *number* | Amount
**is_percent** | *boolean* | When true the value is a %
**created_at** | *timestamp* | Timestamp when created
**metadata** | *object* | A hash of key/value pairs that can store additional information about this object.