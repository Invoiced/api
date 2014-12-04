## Customers

### List Customers
	
	GET /customers

#### Parameters

Name | Type | Description
-----|------|-------------
`sort`|`string`|Column to sort by, i.e. `name asc`
`filter`|`object`|[Filter](#filter) - can be `company`

#### Response

```
Status: 200 OK
Link: <>; rel="self", <>; rel="first", ...
X-Total-Count: 10
```

```json
{
    "customers": [
        {
            "created_at": 1415222128,
            "updated_at": 1417460942,
            "id": 15444,
            "company": 3694,
            "number": "CUST-0001",
            "name": "Acme",
            "primary_contact": "Lesa Dunn",
            "email": "billings@acmecorp.com",
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
        {...}
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
    "primary_contact": "Lesa Dunn",
    "email": "billings@acmecorp.com",
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
    "company": 3694,
    "number": "CUST-0001",
    "name": "Acme",
    "primary_contact": "Lesa Dunn",
    "email": "billings@acmecorp.com",
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
    "company": 3694,
    "number": "CUST-0001",
    "name": "Acme",
    "primary_contact": "Lesa Dunn",
    "email": "billings@acmecorp.com",
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