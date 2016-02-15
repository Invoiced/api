# Subscriptions

Subscriptions allow you to set up recurring billing for your customers. Creating a Subscription will bill a customer according to a given Plan. Addons let you bill for additonal catalog items that get added onto the base plan price.

Subscriptions can have a fixed or infinite duration. Setting the `cycles` property will end the subscription after a fixed number of billing cycles. Otherwise, the subscription must be canceled in order to be stopped.

## Subscription Object

### Attributes

```shell
{
    "id": 595,
    "customer": 15444,
    "plan": "starter",
    "cycles": null,
    "quantity": 1,
    "start_date": 1420391704,
    "renewed_last": 1446657304,
    "renews_next": 1449249304,
    "status": "active",
    "addons": [
        {
            "id": 3,
            "catalog_item": "ipad-license",
            "quantity": 11,
            "created_at": 1420391704
        }
    ],
    "discounts": [],
    "taxes": [],
    "url": "https://dundermifflin.invoiced.com/subscriptions/o2mAd2wWVfYy16XZto7xHwXX",
    "created_at": 1420391704
}
```

```ruby
#<Invoiced::Subscription:0x3fdbf95e4d08 id=595> JSON: {
    "id": 595,
    "customer": 15444,
    "plan": "starter",
    "cycles": null,
    "quantity": 1,
    "start_date": 1420391704,
    "renewed_last": 1446657304,
    "renews_next": 1449249304,
    "status": "active",
    "addons": [
        {
            "id": 3,
            "catalog_item": "ipad-license",
            "quantity": 11,
            "created_at": 1420391704
        }
    ],
    "discounts": [],
    "taxes": [],
    "url": "https://dundermifflin.invoiced.com/subscriptions/o2mAd2wWVfYy16XZto7xHwXX",
    "created_at": 1420391704
}
```

```php
Invoiced\Subscription JSON: {
    "id": 595,
    "customer": 15444,
    "plan": "starter",
    "cycles": null,
    "quantity": 1,
    "start_date": 1420391704,
    "renewed_last": 1446657304,
    "renews_next": 1449249304,
    "status": "active",
    "addons": [
        {
            "id": 3,
            "catalog_item": "ipad-license",
            "quantity": 11,
            "created_at": 1420391704
        }
    ],
    "discounts": [],
    "taxes": [],
    "url": "https://dundermifflin.invoiced.com/subscriptions/o2mAd2wWVfYy16XZto7xHwXX",
    "created_at": 1420391704
}
```

```python
<Subscription id=595 at 0x3fdbf95e4d08> JSON: {
    "id": 595,
    "customer": 15444,
    "plan": "starter",
    "cycles": null,
    "quantity": 1,
    "start_date": 1420391704,
    "renewed_last": 1446657304,
    "renews_next": 1449249304,
    "status": "active",
    "addons": [
        {
            "id": 3,
            "catalog_item": "ipad-license",
            "quantity": 11,
            "created_at": 1420391704
        }
    ],
    "discounts": [],
    "taxes": [],
    "url": "https://dundermifflin.invoiced.com/subscriptions/o2mAd2wWVfYy16XZto7xHwXX",
    "created_at": 1420391704
}
```

Parameter | Type | Description
--------- | ---- | -----------
**id** | *integer* | The subscription's unique ID
**customer** | *integer* | Associated Customer
**plan** | *string* | Plan ID
**start_date** | *timestamp* | Timestamp subscription starts (or started)
**quantity** | *integer* | Plan quantity. Defaults to 1
**cycles** | *integer* | Number of billing cycles the subscription runs for, when `null` runs until canceled (default).
**renewed_last** | *timestamp* | Start of the current billing period
**renews_next** | *timestamp* | End of the current billing period
**status** | *string* | Subscription status, one of `not_started`, `active`, `past_due`, `finished`
**addons** | *array* | Collection of Subscription Addons
**discounts** | *array* | Collection of Discount objects
**taxes** | *array* | Collection of Tax objects
**url** | *string* | URL to manage the subscription in the billing portal
**created_at** | *timestamp* | Timestamp when created

## Subscription Addon Object

### Attributes

```shell
{
    "id": 3,
    "catalog_item": "ipad-license",
    "quantity": 11,
    "created_at": 1420391704
}
```

```ruby
#<Invoiced::SubscriptionAddon:0x3fdbf95e4d08 id=3> JSON: {
    "id": 3,
    "catalog_item": "ipad-license",
    "quantity": 11,
    "created_at": 1420391704
}
```

```php
Invoiced\SubscriptionAddon JSON: {
    "id": 3,
    "catalog_item": "ipad-license",
    "quantity": 11,
    "created_at": 1420391704
}
```

```python
<SubscriptionAddon id=3 at 0x3fdbf95e4d08> JSON: {
    "id": 3,
    "catalog_item": "ipad-license",
    "quantity": 11,
    "created_at": 1420391704
}
```

Parameter | Type | Description
--------- | ---- | -----------
**id** | *integer* | The subscription's unique ID
**catalog_item** | *string* | Catalog Item ID
**quantity** | *integer* | Quantity
**created_at** | *timestamp* | Timestamp when created

## Create a subscription

```shell
curl "https://api.invoiced.com/subscriptions" \
  -u {API_KEY}: \
  -d customer=15444 \
  -d plan="starter" \
  -d addons[0][catalog_item]="ipad-license" \
  -d addons[0][quantity]=11

```

```ruby
invoiced.Subscription.create(
	:customer => 15444,
	:plan => "starter",
	:addons => [
		{
			:catalog_item => "ipad-license",
			:quantity => 11
		}
	]
)
```

```php
<?php

$invoiced->Subscription->create([
	'customer' => 15444,
	'plan' => "starter",
	'addons' => [
		[
			'catalog_item' => "ipad-license",
			'quantity' => 11
		]
	]
]);
```

```python
client.Subscription.create(
	customer=15444,
	plan="starter",
	addons=[
		{
			'catalog_item': "ipad-license",
			'quantity': 11
		}
	]
)
```

> The above command returns JSON structured like this:

```shell
{
    "id": 595,
    "customer": 15444,
    "plan": "starter",
    "cycles": null,
    "quantity": 1,
    "start_date": 1420391704,
    "renewed_last": null,
    "renews_next": 1420391704,
    "status": "active",
    "addons": [
        {
            "id": 3,
            "catalog_item": "ipad-license",
            "quantity": 11,
            "created_at": 1420391704
        }
    ],
    "discounts": [],
    "taxes": [],
    "url": "https://dundermifflin.invoiced.com/subscriptions/o2mAd2wWVfYy16XZto7xHwXX",
    "created_at": 1420391704
}
```

```ruby
#<Invoiced::Subscription:0x3fdbf95e4d08 id=595> JSON: {
    "id": 595,
    "customer": 15444,
    "plan": "starter",
    "cycles": null,
    "quantity": 1,
    "start_date": 1420391704,
    "renewed_last": null,
    "renews_next": 1420391704,
    "status": "active",
    "addons": [
        {
            "id": 3,
            "catalog_item": "ipad-license",
            "quantity": 11,
            "created_at": 1420391704
        }
    ],
    "discounts": [],
    "taxes": [],
    "url": "https://dundermifflin.invoiced.com/subscriptions/o2mAd2wWVfYy16XZto7xHwXX",
    "created_at": 1420391704
}
```

```php
Invoiced\Subscription JSON: {
    "id": 595,
    "customer": 15444,
    "plan": "starter",
    "cycles": null,
    "quantity": 1,
    "start_date": 1420391704,
    "renewed_last": null,
    "renews_next": 1420391704,
    "status": "active",
    "addons": [
        {
            "id": 3,
            "catalog_item": "ipad-license",
            "quantity": 11,
            "created_at": 1420391704
        }
    ],
    "discounts": [],
    "taxes": [],
    "url": "https://dundermifflin.invoiced.com/subscriptions/o2mAd2wWVfYy16XZto7xHwXX",
    "created_at": 1420391704
}
```

```python
<Subscription id=595 at 0x3fdbf95e4d08> JSON: {
    "id": 595,
    "customer": 15444,
    "plan": "starter",
    "cycles": null,
    "quantity": 1,
    "start_date": 1420391704,
    "renewed_last": null,
    "renews_next": 1420391704,
    "status": "active",
    "addons": [
        {
            "id": 3,
            "catalog_item": "ipad-license",
            "quantity": 11,
            "created_at": 1420391704
        }
    ],
    "discounts": [],
    "taxes": [],
    "url": "https://dundermifflin.invoiced.com/subscriptions/o2mAd2wWVfYy16XZto7xHwXX",
    "created_at": 1420391704
}
```

Create a new subscription with this endpoint.

### HTTP Request

`POST /subscriptions`

### Attributes

Parameter | Type | Description
--------- | ---- | -----------
**customer** | *integer* | Customer ID, required
**plan** | *string* | Plan ID, required
**start_date** | *integer* | Timestamp subscription begins, defaults to `now`
**quantity** | *integer* | Plan quantity. Defaults to 1
**cycles** | *integer* | Number of billing cycles the subscription runs for, when `null` runs until canceled (default).
**discounts** | *array* | Collection of Discount objects
**taxes** | *array* | Collection of Tax objects
**addons** | *array* | Collection of optional Subscription Addons

## Retrieve a subscription

```shell
curl "https://api.invoiced.com/subscriptions/:id" \
  -u {API_KEY}:
```

```ruby
subscription = invoiced.Subscription.retrieve("{SUBSCRIPTION_ID}")
```

```php
<?php

$subscription = $invoiced->Subscription->retrieve("{SUBSCRIPTION_ID}");
```

```python
subscription = client.Subscription.retrieve("{SUBSCRIPTION_ID}")
```

> The above command returns JSON structured like this:

```shell
{
    "id": 595,
    "customer": 15444,
    "plan": "starter",
    "cycles": null,
    "quantity": 1,
    "start_date": 1420391704,
    "renewed_last": 1446657304,
    "renews_next": 1449249304,
    "status": "active",
    "addons": [
        {
            "id": 3,
            "catalog_item": "ipad-license",
            "quantity": 11,
            "created_at": 1420391704
        }
    ],
    "discounts": [],
    "taxes": [],
    "url": "https://dundermifflin.invoiced.com/subscriptions/o2mAd2wWVfYy16XZto7xHwXX",
    "created_at": 1420391704
}
```

```ruby
#<Invoiced::Subscription:0x3fdbf95e4d08 id=595> JSON: {
    "id": 595,
    "customer": 15444,
    "plan": "starter",
    "cycles": null,
    "quantity": 1,
    "start_date": 1420391704,
    "renewed_last": 1446657304,
    "renews_next": 1449249304,
    "status": "active",
    "addons": [
        {
            "id": 3,
            "catalog_item": "ipad-license",
            "quantity": 11,
            "created_at": 1420391704
        }
    ],
    "discounts": [],
    "taxes": [],
    "url": "https://dundermifflin.invoiced.com/subscriptions/o2mAd2wWVfYy16XZto7xHwXX",
    "created_at": 1420391704
}
```

```php
Invoiced\Subscription JSON: {
    "id": 595,
    "customer": 15444,
    "plan": "starter",
    "cycles": null,
    "quantity": 1,
    "start_date": 1420391704,
    "renewed_last": 1446657304,
    "renews_next": 1449249304,
    "status": "active",
    "addons": [
        {
            "id": 3,
            "catalog_item": "ipad-license",
            "quantity": 11,
            "created_at": 1420391704
        }
    ],
    "discounts": [],
    "taxes": [],
    "url": "https://dundermifflin.invoiced.com/subscriptions/o2mAd2wWVfYy16XZto7xHwXX",
    "created_at": 1420391704
}
```

```python
<Subscription id=595 at 0x3fdbf95e4d08> JSON: {
    "id": 595,
    "customer": 15444,
    "plan": "starter",
    "cycles": null,
    "quantity": 1,
    "start_date": 1420391704,
    "renewed_last": 1446657304,
    "renews_next": 1449249304,
    "status": "active",
    "addons": [
        {
            "id": 3,
            "catalog_item": "ipad-license",
            "quantity": 11,
            "created_at": 1420391704
        }
    ],
    "discounts": [],
    "taxes": [],
    "url": "https://dundermifflin.invoiced.com/subscriptions/o2mAd2wWVfYy16XZto7xHwXX",
    "created_at": 1420391704
}
```

This endpoint retrieves a specific subscription.

### HTTP Request

`GET /subscriptions/:id`

## Update a subscription

```shell
curl "https://api.invoiced.com/subscriptions/:id" \
  -u {API_KEY}: \
  -d plan="pro" \
  -X PATCH
```

```ruby
subscription.plan = "pro"
subscription.save
```

```php
<?php

$subscription->plan = "pro";
$subscription->save();
```

```python
subscription.plan = "pro"
subscription.save()
```

> The above command returns JSON structured like this:

```shell
{
    "id": 595,
    "customer": 15444,
    "plan": "pro",
    "cycles": null,
    "quantity": 1,
    "start_date": 1420391704,
    "renewed_last": 1446657304,
    "renews_next": 1449249304,
    "status": "active",
    "addons": [
        {
            "id": 3,
            "catalog_item": "ipad-license",
            "quantity": 11,
            "created_at": 1420391704
        }
    ],
    "discounts": [],
    "taxes": [],
    "url": "https://dundermifflin.invoiced.com/subscriptions/o2mAd2wWVfYy16XZto7xHwXX",
    "created_at": 1420391704
}
```

```ruby
#<Invoiced::Subscription:0x3fdbf95e4d08 id=595> JSON: {
    "id": 595,
    "customer": 15444,
    "plan": "pro",
    "cycles": null,
    "quantity": 1,
    "start_date": 1420391704,
    "renewed_last": 1446657304,
    "renews_next": 1449249304,
    "status": "active",
    "addons": [
        {
            "id": 3,
            "catalog_item": "ipad-license",
            "quantity": 11,
            "created_at": 1420391704
        }
    ],
    "discounts": [],
    "taxes": [],
    "url": "https://dundermifflin.invoiced.com/subscriptions/o2mAd2wWVfYy16XZto7xHwXX",
    "created_at": 1420391704
}
```

```php
Invoiced\Subscription JSON: {
    "id": 595,
    "customer": 15444,
    "plan": "pro",
    "cycles": null,
    "quantity": 1,
    "start_date": 1420391704,
    "renewed_last": 1446657304,
    "renews_next": 1449249304,
    "status": "active",
    "addons": [
        {
            "id": 3,
            "catalog_item": "ipad-license",
            "quantity": 11,
            "created_at": 1420391704
        }
    ],
    "discounts": [],
    "taxes": [],
    "url": "https://dundermifflin.invoiced.com/subscriptions/o2mAd2wWVfYy16XZto7xHwXX",
    "created_at": 1420391704
}
```

```python
<Subscription id=595 at 0x3fdbf95e4d08> JSON: {
    "id": 595,
    "customer": 15444,
    "plan": "pro",
    "cycles": null,
    "quantity": 1,
    "start_date": 1420391704,
    "renewed_last": 1446657304,
    "renews_next": 1449249304,
    "status": "active",
    "addons": [
        {
            "id": 3,
            "catalog_item": "ipad-license",
            "quantity": 11,
            "created_at": 1420391704
        }
    ],
    "discounts": [],
    "taxes": [],
    "url": "https://dundermifflin.invoiced.com/subscriptions/o2mAd2wWVfYy16XZto7xHwXX",
    "created_at": 1420391704
}
```

Use this endpoint to update a subscription.

### HTTP Request

`PATCH /subscriptions/:id`

### Request Parameters

Parameter | Type | Description
--------- | ---- | -----------
**plan** | *string* | Plan ID, required
**start_date** | *integer* | Timestamp subscription begins, defaults to `now`
**quantity** | *integer* | Plan quantity. Defaults to 1
**addons** | *array* | Collection of optional Subscription Addons
**prorate** | *boolean* | Prorate changes to plan, quantities, or addons, defaults to *true*

## Cancel a subscription

```shell
curl "https://api.invoiced.com/subscriptions/:id" \
  -u {API_KEY}: \
  -X DELETE
```

```ruby
subscription.cancel
```

```php
<?php

$subscription->cancel();
```

```python
subscription.cancel()
```

> The above command returns `204 No Content`

This endpoint cancels a subscription.

### HTTP Request

`DELETE /subscriptions/:id`

## List all subscriptions

```shell
curl "https://api.invoiced.com/subscriptions" \
  -u {API_KEY}:
```

```ruby
subscriptions, metadata = invoiced.Subscription.list(:per_page => 3)
```

```php
<?php

list($subscriptions, $metadata) = $invoiced->Subscription->all(['per_page' => 3]);
```

```python
subscriptions, metadata = invoiced.Subscription.list(per_page=3)
```

> The above command returns JSON structured like this:

```shell
[
  {
    "id": 595,
    "customer": 15444,
    "plan": "pro",
    "cycles": null,
    "quantity": 1,
    "start_date": 1420391704,
    "renewed_last": 1446657304,
    "renews_next": 1449249304,
    "status": "active",
    "addons": [
        {
            "id": 3,
            "catalog_item": "ipad-license",
            "quantity": 11,
            "created_at": 1420391704
        }
    ],
    "discounts": [],
    "taxes": [],
    "url": "https://dundermifflin.invoiced.com/subscriptions/o2mAd2wWVfYy16XZto7xHwXX",
    "created_at": 1420391704
  },
  { ... },
  { ... }
]
```

```ruby
[
  #<Invoiced::Subscription:0x3fdbf95e4d08 id=595> JSON: {
    "id": 595,
    "customer": 15444,
    "plan": "pro",
    "cycles": null,
    "quantity": 1,
    "start_date": 1420391704,
    "renewed_last": 1446657304,
    "renews_next": 1449249304,
    "status": "active",
    "addons": [
        {
            "id": 3,
            "catalog_item": "ipad-license",
            "quantity": 11,
            "created_at": 1420391704
        }
    ],
    "discounts": [],
    "taxes": [],
    "url": "https://dundermifflin.invoiced.com/subscriptions/o2mAd2wWVfYy16XZto7xHwXX",
    "created_at": 1420391704
  },
  #<Invoiced::Subscription:0x3fdbf95e4d09 id=596> JSON: { ... },
  #<Invoiced::Subscription:0x3fdbf95e4d10 id=597> JSON: { ... }
]
```

```php
[
  Invoiced\Subscription JSON: {
    "id": 595,
    "customer": 15444,
    "plan": "pro",
    "cycles": null,
    "quantity": 1,
    "start_date": 1420391704,
    "renewed_last": 1446657304,
    "renews_next": 1449249304,
    "status": "active",
    "addons": [
        {
            "id": 3,
            "catalog_item": "ipad-license",
            "quantity": 11,
            "created_at": 1420391704
        }
    ],
    "discounts": [],
    "taxes": [],
    "url": "https://dundermifflin.invoiced.com/subscriptions/o2mAd2wWVfYy16XZto7xHwXX",
    "created_at": 1420391704
  },
  Invoiced\Subscription JSON: { ... },
  Invoiced\Subscription JSON: { ... }
]
```

```python
[
  <Subscription id=595 at 0x3fdbf95e4d08> JSON: {
    "id": 595,
    "customer": 15444,
    "plan": "pro",
    "cycles": null,
    "quantity": 1,
    "start_date": 1420391704,
    "renewed_last": 1446657304,
    "renews_next": 1449249304,
    "status": "active",
    "addons": [
        {
            "id": 3,
            "catalog_item": "ipad-license",
            "quantity": 11,
            "created_at": 1420391704
        }
    ],
    "discounts": [],
    "taxes": [],
    "url": "https://dundermifflin.invoiced.com/subscriptions/o2mAd2wWVfYy16XZto7xHwXX",
    "created_at": 1420391704
  },
  <Subscription id=596 at 0x3fdbf95e4d08> JSON: { ... },
  <Subscription id=597 at 0x3fdbf95e4d08> JSON: { ... }
]
```

This endpoint retrieves all subscriptions.

### HTTP Request

`GET /subscriptions`

### Query Parameters

Parameter | Description
--------- | -----------
**sort** *string* | Column to sort by, i.e. `renews_next asc`
**filter** *object* | Filter object
