Stored Items
====

Stored Items represent a reusable line item. They are used to prepoulate line items for saving time and to associate matching line items. **Stored Items cannot be deleted, only archived.**

* [List Stored Items](#list-stored-items)
* [Creating a Stored Item](#creating-a-stored-item)
* [Fetch a Stored Item](#fetch-a-stored-item)
* [Editing a Stored Item](#editing-a-stored-item)

### List Stored Items

  GET /stored_items

#### Parameters

Name | Type | Description
-----|------|-------------
`sort`|`string`|Column to sort by, i.e. `name asc`
`filter`|`object`|[Filter](../README.md#filter)

#### Response

```
Status: 200 OK
Link: <https://api.invoiced.com/stored_items?page=1&per_page=10>; rel="self",
    <https://api.invoiced.com/stored_items?page=1&per_page=10>; rel="first",
    <https://api.invoiced.com/stored_items?page=2&per_page=10>; rel="next",
    <https://api.invoiced.com/stored_items?page=3&per_page=10>; rel="last"
X-Total-Count: 30
```

```json
stored_items: [
  {
    "created_at": 1415228628,
    "updated_at": 1415228642,
    "id": 2804,
    "type": "service",
    "name": "Web Site Starter",
    "description": "The most affordable way to get an online presence.",
    "unit_cost": 1000,
    "fields": [],
    "archived": false
  },
  {...}
]
```

### Creating a Stored Item

  POST /stored_items

#### Input

```json
{
    "type": "service",
    "name": "Web Site Starter",
    "description": "The most affordable way to get an online presence.",
    "unit_cost": 1000,
    "fields": []
}
```

#### Response

  Status: 201 Created

```json
{
  "stored_item": {
    "created_at": 1415228628,
    "updated_at": 1415228642,
    "id": 2804,
    "type": "service",
    "name": "Web Site Starter",
    "description": "The most affordable way to get an online presence.",
    "unit_cost": 1000,
    "fields": [],
    "archived": false
  },
}
```

### Fetch a Stored Item

  GET /stored_items/:id

#### Response

  Status: 200 OK

```json
{
  "stored_item": {
    "created_at": 1415228628,
    "updated_at": 1415228642,
    "id": 2804,
    "type": "service",
    "name": "Web Site Starter",
    "description": "The most affordable way to get an online presence.",
    "unit_cost": 1000,
    "fields": [],
    "archived": false
  },
}
```

### Editing a Stored Item

  PATCH /stored_items/:id

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