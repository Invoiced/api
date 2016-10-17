# Events

Any important billing activity that happens within your Invoiced account creates an event. Our event system can be used to track changes to important objects in your account, like invoices and customers.

Events are also the basis of our webhooks feature. Webhooks are HTTP callbacks that notify your systems as events are produced. Please see the [Webhooks Guide](https://invoiced.com/docs/dev/webhooks) to learn more about webhooks.

## Event Object

### Attributes

```shell
{
    "id": 1228003,
    "type": "transaction.created",
    "timestamp": 1451500772,
    "data": {
        "object": {
            "amount": 55,
            "created_at": 1451500772,
            "currency": "usd",
            "customer": 15455,
            "date": 1451500771,
            "gateway": null,
            "gateway_id": null,
            "payment_source": null,
            "id": 212047,
            "invoice": 196539,
            "metadata": [],
            "method": "other",
            "notes": null,
            "parent_transaction": null,
            "status": "succeeded",
            "theme": null,
            "type": "payment",
            "pdf_url": "https://dundermifflin.invoiced.com/payments/59FHO96idoXFeiBDu1y5Zggg/pdf",
            "metadata": {}
        }
    }
}
```

```ruby
#<Invoiced::Event:0x3fdbf95e4d08 id=1228003> JSON: {
    "id": 1228003,
    "type": "transaction.created",
    "timestamp": 1451500772,
    "data": {
        "object": {
            "amount": 55,
            "created_at": 1451500772,
            "currency": "usd",
            "customer": 15455,
            "date": 1451500771,
            "gateway": null,
            "gateway_id": null,
            "payment_source": null,
            "id": 212047,
            "invoice": 196539,
            "metadata": [],
            "method": "other",
            "notes": null,
            "parent_transaction": null,
            "status": "succeeded",
            "theme": null,
            "type": "payment",
            "pdf_url": "https://dundermifflin.invoiced.com/payments/59FHO96idoXFeiBDu1y5Zggg/pdf",
            "metadata": {}
        }
    }
}
```

```php
Invoiced\Event JSON: {
    "id": 1228003,
    "type": "transaction.created",
    "timestamp": 1451500772,
    "data": {
        "object": {
            "amount": 55,
            "created_at": 1451500772,
            "currency": "usd",
            "customer": 15455,
            "date": 1451500771,
            "gateway": null,
            "gateway_id": null,
            "payment_source": null,
            "id": 212047,
            "invoice": 196539,
            "metadata": [],
            "method": "other",
            "notes": null,
            "parent_transaction": null,
            "status": "succeeded",
            "theme": null,
            "type": "payment",
            "pdf_url": "https://dundermifflin.invoiced.com/payments/59FHO96idoXFeiBDu1y5Zggg/pdf",
            "metadata": {}
        }
    }
}
```

```python
<Event id=1228003 at 0x3fdbf95e4d08> JSON: {
    "id": 1228003,
    "type": "transaction.created",
    "timestamp": 1451500772,
    "data": {
        "object": {
            "amount": 55,
            "created_at": 1451500772,
            "currency": "usd",
            "customer": 15455,
            "date": 1451500771,
            "gateway": null,
            "gateway_id": null,
            "payment_source": null,
            "id": 212047,
            "invoice": 196539,
            "metadata": [],
            "method": "other",
            "notes": null,
            "parent_transaction": null,
            "status": "succeeded",
            "theme": null,
            "type": "payment",
            "pdf_url": "https://dundermifflin.invoiced.com/payments/59FHO96idoXFeiBDu1y5Zggg/pdf",
            "metadata": {}
        }
    }
}
```

```java
com.invoiced.entity.Event@1c5119e JSON: {
      "id" : 1228003,
      "type" : "transaction.created",
      "timestamp" : 1451500772,
      "data" : {
        "object" : {
          "date" : 1451500771,
          "amount" : 55,
          "metadata" : { },
          "notes" : null,
          "method" : "other",
          "parent_transaction" : null,
          "created_at" : 1451500772,
          "pdf_url" : "https://dundermifflin.invoiced.com/payments/59FHO96idoXFeiBDu1y5Zggg/pdf",
          "type" : "payment",
          "gateway_id" : null,
          "currency" : "usd",
          "theme" : null,
          "payment_source" : null,
          "id" : 212047,
          "invoice" : 196539,
          "gateway" : null,
          "customer" : 15455,
          "status" : "succeeded"
        }
      }
    }
```

Parameter | Type | Description
--------- | ---- | -----------
**id** | *integer* | The event's unique ID
**type** | *string* | Event type
**timestamp** | *timestamp* | Time when event happened
**data** | *object* | Contains an `object` property with the object that was subject of the event and an optional `previous` property for `object.updated` events that is a hash of the old values that changed during the event

## Event Types

Events were named using the `object.action` pattern where `object` represents the subject of the event and `action` represents an operation on the object. You should expect to see the following event types:

- `customer.created`
- `customer.updated`
- `customer.deleted`
- `email.sent`
- `email.not_sent`
- `invoice.created`
- `invoice.updated`
- `invoice.deleted`
- `invoice.viewed`
- `invoice.commented`
- `invoice.payment_expected`
- `invoice.paid`
- `subscription.created`
- `subscription.updated`
- `subscription.deleted`
- `transaction.created`
- `transaction.updated`
- `transaction.deleted`

## List all events

```shell
curl "https://api.invoiced.com/events" \
  -u {API_KEY}:
```

```ruby
events, metadata = invoiced.Event.list(:per_page => 3)
```

```php
<?php

list($events, $metadata) = $invoiced->Event->all(['per_page' => 3]);
```

```python
events, metadata = invoiced.Event.list(per_page=3)
```

```java
EntityList<Event> events = connection.newEvent().listAll(null);
```

> The above command returns JSON structured like this:

```shell
[
  {
    "id": 1228003,
    "type": "transaction.created",
    "timestamp": 1451500772,
    "data": {
        "object": {
            "amount": 55,
            "created_at": 1451500772,
            "currency": "usd",
            "customer": 15455,
            "date": 1451500771,
            "gateway": null,
            "gateway_id": null,
            "payment_source": null,
            "id": 212047,
            "invoice": 196539,
            "metadata": [],
            "method": "other",
            "notes": null,
            "parent_transaction": null,
            "status": "succeeded",
            "theme": null,
            "type": "payment",
            "pdf_url": "https://dundermifflin.invoiced.com/payments/59FHO96idoXFeiBDu1y5Zggg/pdf",
            "metadata": {}
        }
    }
  },
  { ... },
  { ... }
]
```

```ruby
[
  #<Invoiced::Event:0x3fdbf95e4d08 id=212047> JSON: {
    "id": 1228003,
    "type": "transaction.created",
    "timestamp": 1451500772,
    "data": {
        "object": {
            "amount": 55,
            "created_at": 1451500772,
            "currency": "usd",
            "customer": 15455,
            "date": 1451500771,
            "gateway": null,
            "gateway_id": null,
            "payment_source": null,
            "id": 212047,
            "invoice": 196539,
            "metadata": [],
            "method": "other",
            "notes": null,
            "parent_transaction": null,
            "status": "succeeded",
            "theme": null,
            "type": "payment",
            "pdf_url": "https://dundermifflin.invoiced.com/payments/59FHO96idoXFeiBDu1y5Zggg/pdf",
            "metadata": {}
        }
    }
  },
  #<Invoiced::Event:0x3fdbf95e4d09 id=1228004> JSON: { ... },
  #<Invoiced::Event:0x3fdbf95e4d10 id=1228005> JSON: { ... }
]
```

```php
[
  Invoiced\Event JSON: {
    "id": 1228003,
    "type": "transaction.created",
    "timestamp": 1451500772,
    "data": {
        "object": {
            "amount": 55,
            "created_at": 1451500772,
            "currency": "usd",
            "customer": 15455,
            "date": 1451500771,
            "gateway": null,
            "gateway_id": null,
            "payment_source": null,
            "id": 212047,
            "invoice": 196539,
            "metadata": [],
            "method": "other",
            "notes": null,
            "parent_transaction": null,
            "status": "succeeded",
            "theme": null,
            "type": "payment",
            "pdf_url": "https://dundermifflin.invoiced.com/payments/59FHO96idoXFeiBDu1y5Zggg/pdf",
            "metadata": {}
        }
    }
  },
  Invoiced\Event JSON: { ... },
  Invoiced\Event JSON: { ... }
]
```

```python
[
  <Event id=1228003 at 0x3fdbf95e4d08> JSON: {
    "id": 1228003,
    "type": "transaction.created",
    "timestamp": 1451500772,
    "data": {
        "object": {
            "amount": 55,
            "created_at": 1451500772,
            "currency": "usd",
            "customer": 15455,
            "date": 1451500771,
            "gateway": null,
            "gateway_id": null,
            "payment_source": null,
            "id": 212047,
            "invoice": 196539,
            "metadata": [],
            "method": "other",
            "notes": null,
            "parent_transaction": null,
            "status": "succeeded",
            "theme": null,
            "type": "payment",
            "pdf_url": "https://dundermifflin.invoiced.com/payments/59FHO96idoXFeiBDu1y5Zggg/pdf",
            "metadata": {}
        }
    }
  },
  <Event id=1228004 at 0x3fdbf95e4d08> JSON: { ... },
  <Event id=1228005 at 0x3fdbf95e4d08> JSON: { ... }
]
```

```java
[com.invoiced.entity.Event@1c5119e JSON: {
      "id" : 1228003,
      "type" : "transaction.created",
      "timestamp" : 1451500772,
      "data" : {
        "object" : {
          "date" : 1451500771,
          "amount" : 55,
          "metadata" : { },
          "notes" : null,
          "method" : "other",
          "parent_transaction" : null,
          "created_at" : 1451500772,
          "pdf_url" : "https://dundermifflin.invoiced.com/payments/59FHO96idoXFeiBDu1y5Zggg/pdf",
          "type" : "payment",
          "gateway_id" : null,
          "currency" : "usd",
          "theme" : null,
          "payment_source" : null,
          "id" : 212047,
          "invoice" : 196539,
          "gateway" : null,
          "customer" : 15455,
          "status" : "succeeded"
        }
      }
    }, 
    com.invoiced.entity.Event@2d7f0598 JSON: {...},
    com.invoiced.entity.Event@3d7f0598 JSON: {...}
] 
```

This endpoint retrieves all events in reverse chronological order. You can also retrieve events related to a specific object.

### HTTP Request

`GET /events`

### Query Parameters

Parameter | Description
--------- | -----------
**related_to** *string* | Optional object to filter events that are returned. Format: `object type,object ID`, i.e. `customer,1234`