# Subscription Billing

Subscriptions allow you to set up recurring billing for your customers. Creating a Subscription will bill a customer according to a given Plan. Addons let you bill for additonal catalog items that get added onto the base plan price.

Subscriptions can have a fixed or infinite duration. Setting the `cycles` property will end the subscription after a fixed number of billing cycles. Otherwise, the subscription must be canceled in order to be stopped.

By default subscriptions will renew each billing cycle on the same day of the cycle on which it was started. For example, a subscription that started on the 9th of the month will always renew on the 9th of the month. This is known as **Anniversary Billing**. We also support renewing subscriptions on a specific day of the month, i.e. the first. If the subscription does not begin on the day you've specified then the first bill will be prorated. This is called **Calendar Billing**.

## Subscription Object

### Attributes

```shell
{
    "id": 595,
    "object": "subscription",
    "customer": 15444,
    "plan": "starter",
    "cycles": null,
    "quantity": 1,
    "start_date": 1420391704,
    "period_start": 1446657304,
    "period_end": 1449249304,
    "cancel_at_period_end": false,
    "canceled_at": null,
    "status": "active",
    "addons": [
        {
            "id": 3,
            "object": "subscription_addon",
            "catalog_item": "ipad-license",
            "quantity": 11,
            "description": "",
            "created_at": 1420391704
        }
    ],
    "discounts": [],
    "taxes": [],
    "url": "https://dundermifflin.invoiced.com/subscriptions/o2mAd2wWVfYy16XZto7xHwXX",
    "created_at": 1420391704,
    "metadata": {}
}
```

```ruby
#<Invoiced::Subscription:0x3fdbf95e4d08 id=595> JSON: {
    "id": 595,
    "object": "subscription",
    "customer": 15444,
    "plan": "starter",
    "cycles": null,
    "quantity": 1,
    "start_date": 1420391704,
    "period_start": 1446657304,
    "period_end": 1449249304,
    "cancel_at_period_end": false,
    "canceled_at": null,
    "status": "active",
    "addons": [
        {
            "id": 3,
            "object": "subscription_addon",
            "catalog_item": "ipad-license",
            "quantity": 11,
            "description": "",
            "created_at": 1420391704
        }
    ],
    "discounts": [],
    "taxes": [],
    "url": "https://dundermifflin.invoiced.com/subscriptions/o2mAd2wWVfYy16XZto7xHwXX",
    "created_at": 1420391704,
    "metadata": {}
}
```

```php
Invoiced\Subscription JSON: {
    "id": 595,
    "object": "subscription",
    "customer": 15444,
    "plan": "starter",
    "cycles": null,
    "quantity": 1,
    "start_date": 1420391704,
    "period_start": 1446657304,
    "period_end": 1449249304,
    "cancel_at_period_end": false,
    "canceled_at": null,
    "status": "active",
    "addons": [
        {
            "id": 3,
            "object": "subscription_addon",
            "catalog_item": "ipad-license",
            "quantity": 11,
            "description": "",
            "created_at": 1420391704
        }
    ],
    "discounts": [],
    "taxes": [],
    "url": "https://dundermifflin.invoiced.com/subscriptions/o2mAd2wWVfYy16XZto7xHwXX",
    "created_at": 1420391704,
    "metadata": {}
}
```

```python
<Subscription id=595 at 0x3fdbf95e4d08> JSON: {
    "id": 595,
    "object": "subscription",
    "customer": 15444,
    "plan": "starter",
    "cycles": null,
    "quantity": 1,
    "start_date": 1420391704,
    "period_start": 1446657304,
    "period_end": 1449249304,
    "cancel_at_period_end": false,
    "canceled_at": null,
    "status": "active",
    "addons": [
        {
            "id": 3,
            "object": "subscription_addon",
            "catalog_item": "ipad-license",
            "quantity": 11,
            "description": "",
            "created_at": 1420391704
        }
    ],
    "discounts": [],
    "taxes": [],
    "url": "https://dundermifflin.invoiced.com/subscriptions/o2mAd2wWVfYy16XZto7xHwXX",
    "created_at": 1420391704,
    "metadata": {}
}
``` 
```java
com.invoiced.entity.Subscription@74f0915b JSON: {
    "id": 595,
    "object": "subscription",
    "customer": 15444,
    "plan": "starter",
    "cycles": null,
    "quantity": 1,
    "start_date": 1420391704,
    "period_start": 1446657304,
    "period_end": 1449249304,
    "cancel_at_period_end": false,
    "canceled_at": null,
    "status": "active",
    "addons": [
        {
            "id": 3,
            "object": "subscription_addon",
            "catalog_item": "ipad-license",
            "quantity": 11,
            "description": "",
            "created_at": 1420391704
        }
    ],
    "discounts": [],
    "taxes": [],
    "url": "https://dundermifflin.invoiced.com/subscriptions/o2mAd2wWVfYy16XZto7xHwXX",
    "created_at": 1420391704,
    "metadata": {}
}
```

Parameter | Type | Description
--------- | ---- | -----------
**id** | *integer* | The subscription's unique ID
**object** | *string* | Object type, `subscription`
**customer** | *integer* | Associated Customer
**plan** | *string* | Plan ID
**start_date** | *timestamp* | Timestamp subscription starts (or started)
**quantity** | *integer* | Plan quantity. Defaults to 1
**cycles** | *integer* | Number of billing cycles the subscription runs for, when `null` runs until canceled (default).
**period_start** | *timestamp* | Start of the current billing period
**period_end** | *timestamp* | End of the current billing period
**cancel_at_period_end** | *boolean* | When true the subscription will be canceled at the end of the current billing period
**canceled_at** | *timestamp* | Timestamp the subscription was canceled
**status** | *string* | Subscription status, one of `not_started`, `active`, `past_due`, `finished`, `canceled`
**addons** | *array* | Collection of Subscription Addons
**discounts** | *array* | Collection of Coupon Objects
**taxes** | *array* | Collection of Tax Rate Objects
**url** | *string* | URL to manage the subscription in the billing portal
**created_at** | *timestamp* | Timestamp when created
**metadata** | *object* | A hash of key/value pairs that can store additional information about this object.

## Subscription Addon Object

### Attributes

```shell
{
    "id": 3,
    "object": "subscription_addon",
    "catalog_item": "ipad-license",
    "quantity": 11,
    "description": "",
    "created_at": 1420391704
}
```

```ruby
#<Invoiced::SubscriptionAddon:0x3fdbf95e4d08 id=3> JSON: {
    "id": 3,
    "object": "subscription_addon",
    "catalog_item": "ipad-license",
    "quantity": 11,
    "description": "",
    "created_at": 1420391704
}
```

```php
Invoiced\SubscriptionAddon JSON: {
    "id": 3,
    "object": "subscription_addon",
    "catalog_item": "ipad-license",
    "quantity": 11,
    "description": "",
    "created_at": 1420391704
}
```

```python
<SubscriptionAddon id=3 at 0x3fdbf95e4d08> JSON: {
    "id": 3,
    "object": "subscription_addon",
    "catalog_item": "ipad-license",
    "quantity": 11,
    "description": "",
    "created_at": 1420391704
}
```

```java
com.invoiced.entity.SubscriptionAddOn@6ec9001c JSON: {
    "id": 3,
    "object": "subscription_addon",
    "catalog_item": "ipad-license",
    "quantity": 11,
    "description": "",
    "created_at": 1420391704
}
```

Parameter | Type | Description
--------- | ---- | -----------
**id** | *integer* | The subscription's unique ID
**object** | *string* | Object type, `subscription_addon`
**catalog_item** | *string* | Catalog Item ID
**quantity** | *integer* | Quantity
**description** | *string* | Optional description for line items generated from this addon
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

```java
Subscription subscription = invoiced.newSubscription();
subscription.customer = 15444;
subscription.plan = "starter";
subscription.addons = new SubscriptionAddOn[1];
subscription.addons[0] = new SubscriptionAddOn();
subscription.addons[0].catalogItem = "ipad-license";
subscription.addons[0].quantity = 11;
subscription.create();
```

> The above command returns JSON structured like this:

```shell
{
    "id": 595,
    "object": "subscription",
    "customer": 15444,
    "plan": "starter",
    "cycles": null,
    "quantity": 1,
    "start_date": 1420391704,
    "period_start": null,
    "period_end": 1420391704,
    "cancel_at_period_end": false,
    "canceled_at": null,
    "status": "active",
    "addons": [
        {
            "id": 3,
            "object": "subscription_addon",
            "catalog_item": "ipad-license",
            "quantity": 11,
            "description": "",
            "created_at": 1420391704
        }
    ],
    "discounts": [],
    "taxes": [],
    "url": "https://dundermifflin.invoiced.com/subscriptions/o2mAd2wWVfYy16XZto7xHwXX",
    "created_at": 1420391704,
    "metadata": {}
}
```

```ruby
#<Invoiced::Subscription:0x3fdbf95e4d08 id=595> JSON: {
    "id": 595,
    "object": "subscription",
    "customer": 15444,
    "plan": "starter",
    "cycles": null,
    "quantity": 1,
    "start_date": 1420391704,
    "period_start": null,
    "period_end": 1420391704,
    "cancel_at_period_end": false,
    "canceled_at": null,
    "status": "active",
    "addons": [
        {
            "id": 3,
            "object": "subscription_addon",
            "catalog_item": "ipad-license",
            "quantity": 11,
            "description": "",
            "created_at": 1420391704
        }
    ],
    "discounts": [],
    "taxes": [],
    "url": "https://dundermifflin.invoiced.com/subscriptions/o2mAd2wWVfYy16XZto7xHwXX",
    "created_at": 1420391704,
    "metadata": {}
}
```

```php
Invoiced\Subscription JSON: {
    "id": 595,
    "object": "subscription",
    "customer": 15444,
    "plan": "starter",
    "cycles": null,
    "quantity": 1,
    "start_date": 1420391704,
    "period_start": null,
    "period_end": 1420391704,
    "cancel_at_period_end": false,
    "canceled_at": null,
    "status": "active",
    "addons": [
        {
            "id": 3,
            "object": "subscription_addon",
            "catalog_item": "ipad-license",
            "quantity": 11,
            "description": "",
            "created_at": 1420391704
        }
    ],
    "discounts": [],
    "taxes": [],
    "url": "https://dundermifflin.invoiced.com/subscriptions/o2mAd2wWVfYy16XZto7xHwXX",
    "created_at": 1420391704,
    "metadata": {}
}
```

```python
<Subscription id=595 at 0x3fdbf95e4d08> JSON: {
    "id": 595,
    "object": "subscription",
    "customer": 15444,
    "plan": "starter",
    "cycles": null,
    "quantity": 1,
    "start_date": 1420391704,
    "period_start": null,
    "period_end": 1420391704,
    "cancel_at_period_end": false,
    "canceled_at": null,
    "status": "active",
    "addons": [
        {
            "id": 3,
            "object": "subscription_addon",
            "catalog_item": "ipad-license",
            "quantity": 11,
            "description": "",
            "created_at": 1420391704
        }
    ],
    "discounts": [],
    "taxes": [],
    "url": "https://dundermifflin.invoiced.com/subscriptions/o2mAd2wWVfYy16XZto7xHwXX",
    "created_at": 1420391704,
    "metadata": {}
}
```

```java
com.invoiced.entity.Subscription@46bbce72 JSON: {
    "id": 595,
    "object": "subscription",
    "customer": 15444,
    "plan": "starter",
    "cycles": null,
    "quantity": 1,
    "start_date": 1420391704,
    "period_start": null,
    "period_end": 1420391704,
    "cancel_at_period_end": false,
    "canceled_at": null,
    "status": "active",
    "addons": [
        {
            "id": 3,
            "object": "subscription_addon",
            "catalog_item": "ipad-license",
            "quantity": 11,
            "description": "",
            "created_at": 1420391704
        }
    ],
    "discounts": [],
    "taxes": [],
    "url": "https://dundermifflin.invoiced.com/subscriptions/o2mAd2wWVfYy16XZto7xHwXX",
    "created_at": 1420391704,
    "metadata": {}
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
**snap_to_nth_day** | *integer* | Snap billing cycles to a specific day of the month (also known as calendar billing), off by default
**discounts** | *array* | Collection of Coupon IDs
**taxes** | *array* | Collection of Tax Rate IDs
**addons** | *array* | Collection of optional Subscription Addons
**cancel_at_period_end** | *boolean* | When true the subscription will be canceled at the end of the current billing period
**metadata** | *object* | A hash of key/value pairs that can store additional information about this object.

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

```java
Subscription subscription = invoiced.newSubscription().retrieve({SUBSCRIPTION_ID});
```

> The above command returns JSON structured like this:

```shell
{
    "id": 595,
    "object": "subscription",
    "customer": 15444,
    "plan": "starter",
    "cycles": null,
    "quantity": 1,
    "start_date": 1420391704,
    "period_start": 1446657304,
    "period_end": 1449249304,
    "cancel_at_period_end": false,
    "canceled_at": null,
    "status": "active",
    "addons": [
        {
            "id": 3,
            "object": "subscription_addon",
            "catalog_item": "ipad-license",
            "quantity": 11,
            "description": "",
            "created_at": 1420391704
        }
    ],
    "discounts": [],
    "taxes": [],
    "url": "https://dundermifflin.invoiced.com/subscriptions/o2mAd2wWVfYy16XZto7xHwXX",
    "created_at": 1420391704,
    "metadata": {}
}
```

```ruby
#<Invoiced::Subscription:0x3fdbf95e4d08 id=595> JSON: {
    "id": 595,
    "object": "subscription",
    "customer": 15444,
    "plan": "starter",
    "cycles": null,
    "quantity": 1,
    "start_date": 1420391704,
    "period_start": 1446657304,
    "period_end": 1449249304,
    "cancel_at_period_end": false,
    "canceled_at": null,
    "status": "active",
    "addons": [
        {
            "id": 3,
            "object": "subscription_addon",
            "catalog_item": "ipad-license",
            "quantity": 11,
            "description": "",
            "created_at": 1420391704
        }
    ],
    "discounts": [],
    "taxes": [],
    "url": "https://dundermifflin.invoiced.com/subscriptions/o2mAd2wWVfYy16XZto7xHwXX",
    "created_at": 1420391704,
    "metadata": {}
}
```

```php
Invoiced\Subscription JSON: {
    "id": 595,
    "object": "subscription",
    "customer": 15444,
    "plan": "starter",
    "cycles": null,
    "quantity": 1,
    "start_date": 1420391704,
    "period_start": 1446657304,
    "period_end": 1449249304,
    "cancel_at_period_end": false,
    "canceled_at": null,
    "status": "active",
    "addons": [
        {
            "id": 3,
            "object": "subscription_addon",
            "catalog_item": "ipad-license",
            "quantity": 11,
            "description": "",
            "created_at": 1420391704
        }
    ],
    "discounts": [],
    "taxes": [],
    "url": "https://dundermifflin.invoiced.com/subscriptions/o2mAd2wWVfYy16XZto7xHwXX",
    "created_at": 1420391704,
    "metadata": {}
}
```

```python
<Subscription id=595 at 0x3fdbf95e4d08> JSON: {
    "id": 595,
    "object": "subscription",
    "customer": 15444,
    "plan": "starter",
    "cycles": null,
    "quantity": 1,
    "start_date": 1420391704,
    "period_start": 1446657304,
    "period_end": 1449249304,
    "cancel_at_period_end": false,
    "canceled_at": null,
    "status": "active",
    "addons": [
        {
            "id": 3,
            "object": "subscription_addon",
            "catalog_item": "ipad-license",
            "quantity": 11,
            "description": "",
            "created_at": 1420391704
        }
    ],
    "discounts": [],
    "taxes": [],
    "url": "https://dundermifflin.invoiced.com/subscriptions/o2mAd2wWVfYy16XZto7xHwXX",
    "created_at": 1420391704,
    "metadata": {}
}
```

```java
com.invoiced.entity.Subscription@46bbce72 JSON: {
    "id": 595,
    "object": "subscription",
    "customer": 15444,
    "plan": "starter",
    "cycles": null,
    "quantity": 1,
    "start_date": 1420391704,
    "period_start": 1446657304,
    "period_end": 1449249304,
    "cancel_at_period_end": false,
    "canceled_at": null,
    "status": "active",
    "addons": [
        {
            "id": 3,
            "object": "subscription_addon",
            "catalog_item": "ipad-license",
            "quantity": 11,
            "description": "",
            "created_at": 1420391704
        }
    ],
    "discounts": [],
    "taxes": [],
    "url": "https://dundermifflin.invoiced.com/subscriptions/o2mAd2wWVfYy16XZto7xHwXX",
    "created_at": 1420391704,
    "metadata": {}
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

```java
subscription.plan = "pro";
subscription.save();
```

> The above command returns JSON structured like this:

```shell
{
    "id": 595,
    "object": "subscription",
    "customer": 15444,
    "plan": "pro",
    "cycles": null,
    "quantity": 1,
    "start_date": 1420391704,
    "period_start": 1446657304,
    "period_end": 1449249304,
    "cancel_at_period_end": false,
    "canceled_at": null,
    "status": "active",
    "addons": [
        {
            "id": 3,
            "object": "subscription_addon",
            "catalog_item": "ipad-license",
            "quantity": 11,
            "description": "",
            "created_at": 1420391704
        }
    ],
    "discounts": [],
    "taxes": [],
    "url": "https://dundermifflin.invoiced.com/subscriptions/o2mAd2wWVfYy16XZto7xHwXX",
    "created_at": 1420391704,
    "metadata": {}
}
```

```ruby
#<Invoiced::Subscription:0x3fdbf95e4d08 id=595> JSON: {
    "id": 595,
    "object": "subscription",
    "customer": 15444,
    "plan": "pro",
    "cycles": null,
    "quantity": 1,
    "start_date": 1420391704,
    "period_start": 1446657304,
    "period_end": 1449249304,
    "cancel_at_period_end": false,
    "canceled_at": null,
    "status": "active",
    "addons": [
        {
            "id": 3,
            "object": "subscription_addon",
            "catalog_item": "ipad-license",
            "quantity": 11,
            "description": "",
            "created_at": 1420391704
        }
    ],
    "discounts": [],
    "taxes": [],
    "url": "https://dundermifflin.invoiced.com/subscriptions/o2mAd2wWVfYy16XZto7xHwXX",
    "created_at": 1420391704,
    "metadata": {}
}
```

```php
Invoiced\Subscription JSON: {
    "id": 595,
    "object": "subscription",
    "customer": 15444,
    "plan": "pro",
    "cycles": null,
    "quantity": 1,
    "start_date": 1420391704,
    "period_start": 1446657304,
    "period_end": 1449249304,
    "cancel_at_period_end": false,
    "canceled_at": null,
    "status": "active",
    "addons": [
        {
            "id": 3,
            "object": "subscription_addon",
            "catalog_item": "ipad-license",
            "quantity": 11,
            "description": "",
            "created_at": 1420391704
        }
    ],
    "discounts": [],
    "taxes": [],
    "url": "https://dundermifflin.invoiced.com/subscriptions/o2mAd2wWVfYy16XZto7xHwXX",
    "created_at": 1420391704,
    "metadata": {}
}
```

```python
<Subscription id=595 at 0x3fdbf95e4d08> JSON: {
    "id": 595,
    "object": "subscription",
    "customer": 15444,
    "plan": "pro",
    "cycles": null,
    "quantity": 1,
    "start_date": 1420391704,
    "period_start": 1446657304,
    "period_end": 1449249304,
    "cancel_at_period_end": false,
    "canceled_at": null,
    "status": "active",
    "addons": [
        {
            "id": 3,
            "object": "subscription_addon",
            "catalog_item": "ipad-license",
            "quantity": 11,
            "description": "",
            "created_at": 1420391704
        }
    ],
    "discounts": [],
    "taxes": [],
    "url": "https://dundermifflin.invoiced.com/subscriptions/o2mAd2wWVfYy16XZto7xHwXX",
    "created_at": 1420391704,
    "metadata": {}
}
```

```java
com.invoiced.entity.Subscription@46bbce72 JSON: {
    "id": 595,
    "object": "subscription",
    "customer": 15444,
    "plan": "pro",
    "cycles": null,
    "quantity": 1,
    "start_date": 1420391704,
    "period_start": 1446657304,
    "period_end": 1449249304,
    "cancel_at_period_end": false,
    "canceled_at": null,
    "status": "active",
    "addons": [
        {
            "id": 3,
            "object": "subscription_addon",
            "catalog_item": "ipad-license",
            "quantity": 11,
            "description": "",
            "created_at": 1420391704
        }
    ],
    "discounts": [],
    "taxes": [],
    "url": "https://dundermifflin.invoiced.com/subscriptions/o2mAd2wWVfYy16XZto7xHwXX",
    "created_at": 1420391704,
    "metadata": {}
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
**discounts** | *array* | Collection of Coupon IDs
**taxes** | *array* | Collection of Tax Rate IDs
**addons** | *array* | Collection of optional Subscription Addons
**cancel_at_period_end** | *boolean* | When true the subscription will be canceled at the end of the current billing period
**prorate** | *boolean* | Prorate changes to plan, quantities, or addons, defaults to *true*
**metadata** | *object* | A hash of key/value pairs that can store additional information about this object.

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

```java
subscription.cancel();
```

> The above command returns JSON structured like this:

```shell
{
    "id": 595,
    "object": "subscription",
    "customer": 15444,
    "plan": "pro",
    "cycles": null,
    "quantity": 1,
    "start_date": 1420391704,
    "period_start": null,
    "period_end": null,
    "cancel_at_period_end": false,
    "canceled_at": 1449162904,
    "status": "canceled",
    "addons": [
        {
            "id": 3,
            "object": "subscription_addon",
            "catalog_item": "ipad-license",
            "quantity": 11,
            "description": "",
            "created_at": 1420391704
        }
    ],
    "discounts": [],
    "taxes": [],
    "url": "https://dundermifflin.invoiced.com/subscriptions/o2mAd2wWVfYy16XZto7xHwXX",
    "created_at": 1420391704,
    "metadata": {}
}
```

```ruby
#<Invoiced::Subscription:0x3fdbf95e4d08 id=595> JSON: {
    "id": 595,
    "object": "subscription",
    "customer": 15444,
    "plan": "pro",
    "cycles": null,
    "quantity": 1,
    "start_date": 1420391704,
    "period_start": null,
    "period_end": null,
    "cancel_at_period_end": false,
    "canceled_at": 1449162904,
    "status": "canceled",
    "addons": [
        {
            "id": 3,
            "object": "subscription_addon",
            "catalog_item": "ipad-license",
            "quantity": 11,
            "description": "",
            "created_at": 1420391704
        }
    ],
    "discounts": [],
    "taxes": [],
    "url": "https://dundermifflin.invoiced.com/subscriptions/o2mAd2wWVfYy16XZto7xHwXX",
    "created_at": 1420391704,
    "metadata": {}
}
```

```php
Invoiced\Subscription JSON: {
    "id": 595,
    "object": "subscription",
    "customer": 15444,
    "plan": "pro",
    "cycles": null,
    "quantity": 1,
    "start_date": 1420391704,
    "period_start": null,
    "period_end": null,
    "cancel_at_period_end": false,
    "canceled_at": 1449162904,
    "status": "canceled",
    "addons": [
        {
            "id": 3,
            "object": "subscription_addon",
            "catalog_item": "ipad-license",
            "quantity": 11,
            "description": "",
            "created_at": 1420391704
        }
    ],
    "discounts": [],
    "taxes": [],
    "url": "https://dundermifflin.invoiced.com/subscriptions/o2mAd2wWVfYy16XZto7xHwXX",
    "created_at": 1420391704,
    "metadata": {}
}
```

```python
<Subscription id=595 at 0x3fdbf95e4d08> JSON: {
    "id": 595,
    "object": "subscription",
    "customer": 15444,
    "plan": "pro",
    "cycles": null,
    "quantity": 1,
    "start_date": 1420391704,
    "period_start": null,
    "period_end": null,
    "cancel_at_period_end": false,
    "canceled_at": 1449162904,
    "status": "canceled",
    "addons": [
        {
            "id": 3,
            "object": "subscription_addon",
            "catalog_item": "ipad-license",
            "quantity": 11,
            "description": "",
            "created_at": 1420391704
        }
    ],
    "discounts": [],
    "taxes": [],
    "url": "https://dundermifflin.invoiced.com/subscriptions/o2mAd2wWVfYy16XZto7xHwXX",
    "created_at": 1420391704,
    "metadata": {}
}
```

```java
com.invoiced.entity.Subscription@46bbce72 JSON: {
    "id": 595,
    "object": "subscription",
    "customer": 15444,
    "plan": "pro",
    "cycles": null,
    "quantity": 1,
    "start_date": 1420391704,
    "period_start": null,
    "period_end": null,
    "cancel_at_period_end": false,
    "canceled_at": 1449162904,
    "status": "canceled",
    "addons": [
        {
            "id": 3,
            "object": "subscription_addon",
            "catalog_item": "ipad-license",
            "quantity": 11,
            "description": "",
            "created_at": 1420391704
        }
    ],
    "discounts": [],
    "taxes": [],
    "url": "https://dundermifflin.invoiced.com/subscriptions/o2mAd2wWVfYy16XZto7xHwXX",
    "created_at": 1420391704,
    "metadata": {}
}
```

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

```java
EntityList<Subscription> subscriptions = invoiced.newSubscription().listAll();
```

> The above command returns JSON structured like this:

```shell
[
  {
    "id": 595,
    "object": "subscription",
    "customer": 15444,
    "plan": "pro",
    "cycles": null,
    "quantity": 1,
    "start_date": 1420391704,
    "period_start": 1446657304,
    "period_end": 1449249304,
    "cancel_at_period_end": false,
    "canceled_at": null,
    "status": "active",
    "addons": [
        {
            "id": 3,
            "object": "subscription_addon",
            "catalog_item": "ipad-license",
            "quantity": 11,
            "description": "",
            "created_at": 1420391704
        }
    ],
    "discounts": [],
    "taxes": [],
    "url": "https://dundermifflin.invoiced.com/subscriptions/o2mAd2wWVfYy16XZto7xHwXX",
    "created_at": 1420391704,
    "metadata": {}
  },
  { ... },
  { ... }
]
```

```ruby
[
  #<Invoiced::Subscription:0x3fdbf95e4d08 id=595> JSON: {
    "id": 595,
    "object": "subscription",
    "customer": 15444,
    "plan": "pro",
    "cycles": null,
    "quantity": 1,
    "start_date": 1420391704,
    "period_start": 1446657304,
    "period_end": 1449249304,
    "cancel_at_period_end": false,
    "canceled_at": null,
    "status": "active",
    "addons": [
        {
            "id": 3,
            "object": "subscription_addon",
            "catalog_item": "ipad-license",
            "quantity": 11,
            "description": "",
            "created_at": 1420391704
        }
    ],
    "discounts": [],
    "taxes": [],
    "url": "https://dundermifflin.invoiced.com/subscriptions/o2mAd2wWVfYy16XZto7xHwXX",
    "created_at": 1420391704,
    "metadata": {}
  },
  #<Invoiced::Subscription:0x3fdbf95e4d09 id=596> JSON: { ... },
  #<Invoiced::Subscription:0x3fdbf95e4d10 id=597> JSON: { ... }
]
```

```php
[
  Invoiced\Subscription JSON: {
    "id": 595,
    "object": "subscription",
    "customer": 15444,
    "plan": "pro",
    "cycles": null,
    "quantity": 1,
    "start_date": 1420391704,
    "period_start": 1446657304,
    "period_end": 1449249304,
    "cancel_at_period_end": false,
    "canceled_at": null,
    "status": "active",
    "addons": [
        {
            "id": 3,
            "object": "subscription_addon",
            "catalog_item": "ipad-license",
            "quantity": 11,
            "description": "",
            "created_at": 1420391704
        }
    ],
    "discounts": [],
    "taxes": [],
    "url": "https://dundermifflin.invoiced.com/subscriptions/o2mAd2wWVfYy16XZto7xHwXX",
    "created_at": 1420391704,
    "metadata": {}
  },
  Invoiced\Subscription JSON: { ... },
  Invoiced\Subscription JSON: { ... }
]
```

```python
[
  <Subscription id=595 at 0x3fdbf95e4d08> JSON: {
    "id": 595,
    "object": "subscription",
    "customer": 15444,
    "plan": "pro",
    "cycles": null,
    "quantity": 1,
    "start_date": 1420391704,
    "period_start": 1446657304,
    "period_end": 1449249304,
    "cancel_at_period_end": false,
    "canceled_at": null,
    "status": "active",
    "addons": [
        {
            "id": 3,
            "object": "subscription_addon",
            "catalog_item": "ipad-license",
            "quantity": 11,
            "description": "",
            "created_at": 1420391704
        }
    ],
    "discounts": [],
    "taxes": [],
    "url": "https://dundermifflin.invoiced.com/subscriptions/o2mAd2wWVfYy16XZto7xHwXX",
    "created_at": 1420391704,
    "metadata": {}
  },
  <Subscription id=596 at 0x3fdbf95e4d08> JSON: { ... },
  <Subscription id=597 at 0x3fdbf95e4d08> JSON: { ... }
]
```

```java
[
  com.invoiced.entity.Subscription@20b4fc7b JSON: {
    "id": 595,
    "object": "subscription",
    "customer": 15444,
    "plan": "pro",
    "cycles": null,
    "quantity": 1,
    "start_date": 1420391704,
    "period_start": 1446657304,
    "period_end": 1449249304,
    "cancel_at_period_end": false,
    "canceled_at": null,
    "status": "active",
    "addons": [
        {
            "id": 3,
            "object": "subscription_addon",
            "catalog_item": "ipad-license",
            "quantity": 11,
            "description": "",
            "created_at": 1420391704
        }
    ],
    "discounts": [],
    "taxes": [],
    "url": "https://dundermifflin.invoiced.com/subscriptions/o2mAd2wWVfYy16XZto7xHwXX",
    "created_at": 1420391704,
    "metadata": {}
  },
  com.invoiced.entity.Subscription@73f93614 JSON: {...},
  com.invoiced.entity.Subscription@735f9514 JSON: {...}
]
```

This endpoint retrieves all subscriptions. Unless specified, this endpoint will only return subscriptions that have an upcoming renewal.

### HTTP Request

`GET /subscriptions`

### Query Parameters

Parameter | Description
--------- | -----------
**sort** *string* | Column to sort by, i.e. `period_end asc`
**filter** *object* | Filter object
**metadata** *object* | Metadata filter object
**canceled** *boolean* | When true returns only canceled subscriptions
**finished** *boolean* | When true returns only finished subscriptions