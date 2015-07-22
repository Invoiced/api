Subscriptions
====

Subscriptions allow you to set up recurring billing for your customers. Creating a Subscription will bill a customer according to a given Plan.

Subscriptions can be ongoing or a fixed duration. Setting the `cycles` property will end the subscription after a fixed number of billing cycles. Otherwise, subscriptions must be canceled in order to be stopped.

* [List Subscriptions](#list-subscriptions)
* [Creating a Subscription](#creating-a-subscription)
* [Fetch a Subscription](#fetch-a-subscription)
* [Editing a Subscription](#editing-a-subscription)
* [Canceling a Subscription](#canceling-a-subscription)

### List Subscriptions

  GET /subscriptions

#### Parameters

Name | Type | Description
-----|------|-------------
`sort`|`string`|Column to sort by, i.e. `name asc`
`filter`|`object`|[Filter](../README.md#filter)

#### Response

```
Status: 200 OK
Link: <https://api.invoiced.com/subscriptions?page=1&per_page=10>; rel="self",
    <https://api.invoiced.com/subscriptions?page=1&per_page=10>; rel="first",
    <https://api.invoiced.com/subscriptions?page=2&per_page=10>; rel="next",
    <https://api.invoiced.com/subscriptions?page=3&per_page=10>; rel="last"
X-Total-Count: 30
```

```json
[
    {
        "created_at": 1425572798,
        "updated_at": 1433520901,
        "id": 595,
        "customer": 15444,
        "plan": 420,
        "start_date": 1425572792,
        "quantity": 1,
        "cycles": null,
        "renews_next": 1436109992,
        "renewed_last": 1433517992,
        "status": "active",
        "discounts": [],
        "taxes": [],
        "shipping": []
    },
    { ... },
    { .. }
]
```

### Creating a Subscription

  POST /subscriptions

#### Input

```json
{
    "customer": 15444,
    "plan": 420,
    "start_date": 1425572792
}
```

#### Response

  Status: 201 Created

```json
{
    "created_at": 1425572798,
    "updated_at": 1433520901,
    "id": 595,
    "customer": 15444,
    "plan": 420,
    "start_date": 1425572792,
    "quantity": 1,
    "cycles": null,
    "renews_next": 1436109992,
    "renewed_last": 1433517992,
    "status": "active",
    "discounts": [],
    "taxes": [],
    "shipping": []
}
```

### Fetch a Subscription

  GET /subscriptions/:id

#### Response

  Status: 200 OK

```json
{
    "created_at": 1425572798,
    "updated_at": 1433520901,
    "id": 595,
    "customer": 15444,
    "plan": 420,
    "start_date": 1425572792,
    "quantity": 1,
    "cycles": null,
    "renews_next": 1436109992,
    "renewed_last": 1433517992,
    "status": "active",
    "discounts": [],
    "taxes": [],
    "shipping": []
}
```

### Editing a Subscription

  PATCH /subscriptions/:id

#### Input

```json
{
  "plan": 500,
  "quantity": 2
}
```

#### Response

  Status: 200 OK

```json
{
    "created_at": 1425572798,
    "updated_at": 1433520901,
    "id": 595,
    "customer": 15444,
    "plan": 420,
    "start_date": 1425572792,
    "quantity": 1,
    "cycles": null,
    "renews_next": 1436109992,
    "renewed_last": 1433517992,
    "status": "active",
    "discounts": [],
    "taxes": [],
    "shipping": []
}
```

### Canceling a Subscription

  DELETE /subscriptions/:id

#### Response

  Status: 204 No Content