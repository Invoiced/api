Customers
====

Customers represent the entity you are billing, whether this is an organization or a person. Contacts are individual contacts belonging to a Customer. They are used to represent people within an organization and also to tie user accounts to Customers. If the customer signs up in the client portal then their user ID will be associated with a Contact matching their account email address.

* [List Customers](#list-customers)
* [Creating a Customer](#creating-a-customer)
* [Fetch a Customer](#fetch-a-customer)
* [Creating a Customer Contact](#creating-a-customer-contact)
* [Fetch a Customer's Contacts](#fetch-a-customers-contacts)
* [Editing a Customer Contact](#editing-a-customer-contact)
* [Deleting a Customer Contact](#deleting-a-customer-contact)
* [Editing a Customer](#editing-a-customer)
* [Deleting a Customer](#deleting-a-customer)

### List Customers
  
  GET /customers

#### Parameters

Name | Type | Description
-----|------|-------------
`sort`|`string`|Column to sort by, i.e. `name asc`
`filter`|`object`|[Filter](../README.md#filter)

#### Response

```
Status: 200 OK
Link: <https://api.invoiced.com/customers?page=1&per_page=10>; rel="self",
    <https://api.invoiced.com/customers?page=1&per_page=10>; rel="first",
    <https://api.invoiced.com/customers?page=2&per_page=10>; rel="next",
    <https://api.invoiced.com/customers?page=3&per_page=10>; rel="last"
X-Total-Count: 30
```

```json
{
  "customers": [
    ...,
    {
      "created_at": 1415222128,
      "updated_at": 1417460942,
      "id": 15444,
      "number": "CUST-0001",
      "name": "Acme",
      "email": "billing@acmecorp.com",
      "address1": "342 Amber St",
      "address2": null,
      "city": "Hill Valley",
      "state": "CA",
      "postal_code": "94523",
      "country": "United States",
      "tax_id": "893-934835",
      "phone": "(820) 297-2983",
      "other_phone": null,
      "website": "acmecorp.com",
      "notes": null,
      "balance": 3395.47,
      "stripe_customer": null
    },
    ...
  ]
}
```

### Creating a Customer

  POST /customers

#### Input

```json
{
  "number": "CUST-0001",
  "name": "Acme",
  "email": "billing@acmecorp.com",
  "address1": "342 Amber St",
  "address2": null,
  "city": "Hill Valley",
  "state": "CA",
  "postal_code": "94523",
  "country": "United States",
  "tax_id": "893-934835",
  "phone": "(820) 297-2983",
  "other_phone": null,
  "website": "acmecorp.com",
  "notes": null
}
```

#### Response

  Status: 201 Created

```json
"customer": {
  "created_at": 1415222128,
  "updated_at": null,
  "id": 15444,
  "number": "CUST-0001",
  "name": "Acme",
  "email": "billing@acmecorp.com",
  "address1": "342 Amber St",
  "address2": null,
  "city": "Hill Valley",
  "state": "CA",
  "postal_code": "94523",
  "country": "United States",
  "tax_id": "893-934835",
  "phone": "(820) 297-2983",
  "other_phone": null,
  "website": "acmecorp.com",
  "notes": null,
  "balance": 0,
  "stripe_customer": null
}
```

### Fetch a Customer

  GET /customers/:id

#### Response

  Status: 200 OK

```json
"customer": {
  "created_at": 1415222128,
  "updated_at": 1417460942,
  "id": 15444,
  "number": "CUST-0001",
  "name": "Acme",
  "email": "billing@acmecorp.com",
  "address1": "342 Amber St",
  "address2": null,
  "city": "Hill Valley",
  "state": "CA",
  "postal_code": "94523",
  "country": "United States",
  "tax_id": "893-934835",
  "phone": "(820) 297-2983",
  "other_phone": null,
  "website": "acmecorp.com",
  "notes": null,
  "balance": 3395.47,
  "stripe_customer": null
}
```

### Creating a Customer Contact

  POST /customers/:customer_id/contacts


### Input

```json
{
  "customer": 15444,
  "name": "Tia Lesa Dunn",
  "email": "billings@acmecorp.com",
  "primary": true
}
```

### Response

  Status: 201 Created

```json
{
  "contact": {
    "created_at": 1415222128,
    "updated_at": 1418883302,
    "id": 22256,
    "customer": 15444,
    "name": "Tia Lesa Dunn",
    "email": "billings@acmecorp.com",
    "primary": true
  }
}
```

### Fetch a Customer's Contacts

  GET /customers/:customer_id/contacts

#### Parameters

Name | Type | Description
-----|------|-------------
`sort`|`string`|Column to sort by, i.e. `name asc`
`filter`|`object`|[Filter](../README.md#filter)

#### Response

```
Status: 200 OK
Link: <https://api.invoiced.com/customers/15444/contacts?page=1&per_page=10>; rel="self",
    <https://api.invoiced.com/customers/15444/contacts?page=1&per_page=10>; rel="first",
    <https://api.invoiced.com/customers/15444/contacts?page=1&per_page=10>; rel="last"
X-Total-Count: 5
```

```json
{
  "contacts": [
    ...,
    {
      "created_at": 1415222128,
      "updated_at": 1418883302,
      "id": 22256,
      "customer": 15444,
      "name": "Tia Lesa Dunn",
      "email": "billings@acmecorp.com",
      "primary": true
    },
    ...
  ]
}
```

### Editing a Customer Contact

  PATCH /customers/:customer_id/contacts/:id

#### Input

```json
{
  "primary": false
}
```

#### Response

  Status: 200 OK

```json
{
  "success": true
}
```

### Deleting a Customer Contact

  DELETE /customers/:customer_id/contacts/:id

#### Response

  Status: 204 No Content

### Editing a Customer

  PATCH /customers/:id

#### Input

```json
{
  "other_phone": "(820) 297-2984",
  "notes": "Notes about customer..."
}
```

#### Response

  Status: 200 OK

```json
{
  "success": true
}
```

### Deleting a Customer

  DELETE /customers/:id

#### Response

  Status: 204 No Content