Payment Methods
====

Payment Methods control how your clients are able to pay on the payment page in the client portal.

* [Intro](#intro)
* [List Payment Methods](#list-payment-methods)
* [Creating a Payment Method](#creating-a-payment-method)
* [Fetch a Payment Method](#fetch-a-payment-method)
* [Editing a Payment Method](#editing-a-payment-method)
* [Deleting a Payment Method](#deleting-a-payment-method)

### Intro

Available payment methods:
- `credit_card`
- `ach`
- `bitcoin`
- `paypal`
- `check` - offline
- `wire_transfer` - offline
- `cash` - offline
- `other` - offline

**Notes** You must specify your PayPal email address with the `paypal` method. You can add instructions for offline payment methods, like where to mail a check, using the `meta` property.

### List Payment Methods

  GET /payment_methods

#### Parameters

Name | Type | Description
-----|------|-------------
`sort`|`string`|Column to sort by, i.e. `method asc`
`filter`|`object`|[Filter](../README.md#filter)

#### Response

```
Status: 200 OK
Link: <https://api.invoiced.com/payment_methods?page=1&per_page=10>; rel="self",
    <https://api.invoiced.com/payment_methods?page=1&per_page=10>; rel="first",
    <https://api.invoiced.com/payment_methods?page=2&per_page=10>; rel="next",
    <https://api.invoiced.com/payment_methods?page=3&per_page=10>; rel="last"
X-Total-Count: 30
```

```json
payment_methods: [
  ...
  {
    "created_at": 1415228628,
    "updated_at": 1415228642,
    "method": "check",
    "enabled": true,
    "meta": "Please mail any checks to 701 Brazos St\nAustin, TX 78748"
  },
  ...
]
```

### Creating a Payment Method

  POST /payment_methods

#### Input

```json
{
    "method": "check",
    "enabled": true,
    "meta": "Please mail any checks to 701 Brazos St\nAustin, TX 78748"
}
```

#### Response

  Status: 201 Created

```json
{
  "payment_method": {
    "created_at": 1415228628,
    "updated_at": 1415228642,
    "method": "check",
    "enabled": true,
    "meta": "Please mail any checks to 701 Brazos St\nAustin, TX 78748"
  },
}
```

### Fetch a Payment Method

  GET /payment_methods/:method

#### Response

  Status: 200 OK

```json
{
  "payment_method": {
    "created_at": 1415228628,
    "updated_at": 1415228642,
    "method": "check",
    "enabled": true,
    "meta": "Please mail any checks to 701 Brazos St\nAustin, TX 78748"
  },
}
```

### Editing a Payment Method

  PATCH /payment_methods/:method

#### Input

```json
{
  "enabled": false
}
```

#### Response

  Status: 200 OK

```json
{
  "success": true
}
```

### Deleting a Payment Method

  DELETE /payment_methods/:method

#### Response

  Status: 204 No Content