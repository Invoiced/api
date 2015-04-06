Templates
====

Templates are used as shortcuts when drafting Estimates and Invoices in the dashboard.

* [List Templates](#list-templates)
* [Creating a Template](#creating-a-template)
* [Fetch a Template](#fetch-a-template)
* [Editing a Template](#editing-a-template)
* [Deleting a Template](#deleting-a-template)

### List Templates

  GET /templates

#### Parameters

Name | Type | Description
-----|------|-------------
`sort`|`string`|Column to sort by, i.e. `name asc`
`filter`|`object`|[Filter](../README.md#filter)

#### Response

```
Status: 200 OK
Link: <https://api.invoiced.com/templates?page=1&per_page=10>; rel="self",
    <https://api.invoiced.com/templates?page=1&per_page=10>; rel="first",
    <https://api.invoiced.com/templates?page=2&per_page=10>; rel="next",
    <https://api.invoiced.com/templates?page=3&per_page=10>; rel="last"
X-Total-Count: 30
```

```json
{
    "templates": [
        ...,
        {
            "created_at": 1415228628,
            "updated_at": 1422902098,
            "id": 812,
            "name": "Pencil Order Template",
            "currency": null,
            "payment_terms": "NET 30",
            "items": [
                {
                    "name": "Pencil",
                    "description": "Just an ordinary pencil...",
                    "quantity": 100,
                    "unit_cost": 1,
                    "discounts": [],
                    "taxes": [],
                    "shipping": []
                }
            ],
            "discounts": [
                {
                    "id": 12,
                    "type": "discount",
                    "name": "Being awesome",
                    "number": null,
                    "is_percent": true,
                    "value": 5
                }
            ],
            "taxes": [
                {
                    "id": 304,
                    "type": "tax",
                    "name": "Sales Tax",
                    "number": "FI-8200",
                    "is_percent": true,
                    "value": 7
                },
            ],
            "shipping": [],
            "notes": "Thank you for your business",
            "terms": "Failure to pay by the due date will result in a 1.5% late fee every 30 days.",
        },
        ...
    ]
}
```

### Creating a Template

  POST /templates

#### Input

```json
{
    "name": "Pencil Order Template",
    "currency": null,
    "payment_terms": "NET 30",
    "items": [
        {
            "name": "Pencil",
            "description": "Just an ordinary pencil...",
            "quantity": 100,
            "unit_cost": 1,
            "discounts": [],
            "taxes": [],
            "shipping": []
        }
    ],
    "discounts": [12],
    "taxes": [304],
    "shipping": [],
    "notes": "Thank you for your business",
    "terms": "Failure to pay by the due date will result in a 1.5% late fee every 30 days.",
}
```

#### Response

  Status: 201 Created

```json
{
    "template": {
        "created_at": 1415228628,
        "updated_at": 1422902098,
        "id": 812,
        "name": "Pencil Order Template",
        "currency": null,
        "payment_terms": "NET 30",
        "items": [
            {
                "name": "Pencil",
                "description": "Just an ordinary pencil...",
                "quantity": 100,
                "unit_cost": 1,
                "discounts": [],
                "taxes": [],
                "shipping": []
            }
        ],
        "discounts": [
            {
                "id": 12,
                "type": "discount",
                "name": "Being awesome",
                "number": null,
                "is_percent": true,
                "value": 5
            }
        ],
        "taxes": [
            {
                "id": 304,
                "type": "tax",
                "name": "Sales Tax",
                "number": "FI-8200",
                "is_percent": true,
                "value": 7
            },
        ],
        "shipping": [],
        "notes": "Thank you for your business",
        "terms": "Failure to pay by the due date will result in a 1.5% late fee every 30 days.",
    },
}
```

### Fetch a Template

  GET /templates/:id

#### Response

  Status: 200 OK

```json
{
    "template": {
        "created_at": 1415228628,
        "updated_at": 1422902098,
        "id": 812,
        "name": "Pencil Order Template",
        "currency": null,
        "payment_terms": "NET 30",
        "items": [
            {
                "name": "Pencil",
                "description": "Just an ordinary pencil...",
                "quantity": 100,
                "unit_cost": 1,
                "discounts": [],
                "taxes": [],
                "shipping": []
            }
        ],
        "discounts": [
            {
                "id": 12,
                "type": "discount",
                "name": "Being awesome",
                "number": null,
                "is_percent": true,
                "value": 5
            }
        ],
        "taxes": [
            {
                "id": 304,
                "type": "tax",
                "name": "Sales Tax",
                "number": "FI-8200",
                "is_percent": true,
                "value": 7
            },
        ],
        "shipping": [],
        "notes": "Thank you for your business",
        "terms": "Failure to pay by the due date will result in a 1.5% late fee every 30 days.",
    },
}
```

### Editing a Template

  PATCH /templates/:id

#### Input

```json
{
  "payment_terms": "NET 14"
}
```

#### Response

  Status: 200 OK

```json
{
  "success": true
}
```

### Deleting a Template

  DELETE /templates/:id

#### Response

  Status: 204 No Content