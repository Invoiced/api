Plans
====

Plans are a blueprint to bill your customer on a recurring basis. Customers can be subscribed to plans and will have invoices generated according to the Plan.

**The amount and interval on Plans cannot be changed while the Plan has active subscriptions.**

* [List Plans](#list-plans)
* [Creating a Plan](#creating-a-plan)
* [Fetch a Plan](#fetch-a-plan)
* [Editing a Plan](#editing-a-plan)
* [Deleting a Plan](#deleting-a-plan)

### List Plans

  GET /plans

#### Parameters

Name | Type | Description
-----|------|-------------
`sort`|`string`|Column to sort by, i.e. `name asc`
`filter`|`object`|[Filter](../README.md#filter)

#### Response

```
Status: 200 OK
Link: <https://api.invoiced.com/plans?page=1&per_page=10>; rel="self",
    <https://api.invoiced.com/plans?page=1&per_page=10>; rel="first",
    <https://api.invoiced.com/plans?page=2&per_page=10>; rel="next",
    <https://api.invoiced.com/plans?page=3&per_page=10>; rel="last"
X-Total-Count: 30
```

```json
{
    "plans": [
        ...,
        {
            "created_at": 1415229884,
            "updated_at": 1429285176,
            "id": 420,
            "name": "Starter",
            "theme": null,
            "chase": true,
            "currency": "usd",
            "amount": 55,
            "interval": "month",
            "interval_count": 1,
            "description": "Plan description that will populate line item description...",
            "type": "product",
            "notes": null,
            "terms": null,
            "send_invoice_after_renewal": false,
            "disabled_payment_methods": []
        },
        ...
    ]
}
```

### Creating a Plan

  POST /plans

#### Input

```json
{
    "name": "Starter",
    "theme": null,
    "chase": true,
    "currency": "usd",
    "amount": 55,
    "interval": "month",
    "interval_count": 1,
    "description": "Plan description that will populate line item description...",
    "type": "product",
    "notes": null,
    "terms": null,
    "send_invoice_after_renewal": false,
    "disabled_payment_methods": []
}
```

#### Response

  Status: 201 Created

```json
{
    "plan": {
        "created_at": 1415229884,
        "updated_at": 1429285176,
        "id": 420,
        "name": "Starter",
        "theme": null,
        "chase": true,
        "currency": "usd",
        "amount": 55,
        "interval": "month",
        "interval_count": 1,
        "description": "Plan description that will populate line item description...",
        "type": "product",
        "notes": null,
        "terms": null,
        "send_invoice_after_renewal": false,
        "disabled_payment_methods": []
    }
}
```

### Fetch a Plan

  GET /plans/:id

#### Response

  Status: 200 OK

```json
{
    "plan": {
        "created_at": 1415229884,
        "updated_at": 1429285176,
        "id": 420,
        "name": "Starter",
        "theme": null,
        "chase": true,
        "currency": "usd",
        "amount": 55,
        "interval": "month",
        "interval_count": 1,
        "description": "Plan description that will populate line item description...",
        "type": "product",
        "notes": null,
        "terms": null,
        "send_invoice_after_renewal": false,
        "disabled_payment_methods": []
    }
}
```

### Editing a Plan

  PATCH /plans/:id

#### Input

```json
{
  "notes": "Notes that populate the invoice",
  "terms": "Terms & Conditions..."
}
```

#### Response

  Status: 200 OK

```json
{
  "success": true
}
```

### Deleting a Plan

  DELETE /plans/:id

#### Response

  Status: 204 No Content