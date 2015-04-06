Rates
====

Rates represent a discount, tax, or shipping rate on Invoiced. A Rate can be a percentage or fixed amount. Rates can be applied to Estimates, Invoices, and Line Items. Whenever a Rate is applied to any of these a corresponding Applied Rate object is created. **Rates cannot be deleted, only archived.** Also, once a Rate is created the value or type cannot be changed.

* [List Rates](#list-rates)
* [Creating a Rate](#creating-a-rate)
* [Fetch a Rate](#fetch-a-rate)
* [Editing a Rate](#editing-a-rate)

### List Rates

  GET /rates

#### Parameters

Name | Type | Description
-----|------|-------------
`sort`|`string`|Column to sort by, i.e. `name asc`
`filter`|`object`|[Filter](../README.md#filter)

#### Response

```
Status: 200 OK
Link: <https://api.invoiced.com/rates?page=1&per_page=10>; rel="self",
    <https://api.invoiced.com/rates?page=1&per_page=10>; rel="first",
    <https://api.invoiced.com/rates?page=2&per_page=10>; rel="next",
    <https://api.invoiced.com/rates?page=3&per_page=10>; rel="last"
X-Total-Count: 30
```

```json
{
    "rates": [
        ...,
        {
          "created_at": 1415228628,
          "updated_at": 1415228642,
          "id": 304,
          "type": "tax",
          "name": "Sales Tax",
          "number": "FI-8200",
          "is_percent": true,
          "value": 7,
          "archived": false
        },
        ...
    ]
}
```

### Creating a Rate

  POST /rates

#### Input

```json
{
    "type": "discount",
    "name": "Referred A Friend",
    "is_percent": false,
    "value": 50
}
```

#### Response

  Status: 201 Created

```json
{
  "rate": {
    "created_at": 1415228628,
    "updated_at": 1415228642,
    "id": 305,
    "type": "discount",
    "name": "Referred a Friend",
    "number": null,
    "is_percent": false,
    "value": 50,
    "archived": false
  },
}
```

### Fetch a Rate

  GET /rates/:id

#### Response

  Status: 200 OK

```json
{
  "rate": {
    "created_at": 1415228628,
    "updated_at": 1415228642,
    "id": 304,
    "type": "tax",
    "name": "Sales Tax",
    "number": "FI-8200",
    "is_percent": true,
    "value": 7,
    "archived": false
  },
}
```

### Editing a Rate

  PATCH /rates/:id

#### Input

```json
{
  "archived": true
}
```

#### Response

  Status: 200 OK

```json
{
  "success": true
}
```