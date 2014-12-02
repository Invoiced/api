Invoiced API
===

Documentation for the Invoiced API

## Table of Contents
* [Introduction](#introduction)
* [Authentication](#authentication)
* [Errors](#errors)
* [Special Parameters](#special-parameters)
* [Customers](#customers)
* [Estimates](#estimates)
* [Invoices](#invoices)
* [Payments](#payments)

## Introduction

Invoiced is simple invoicing for freelancers and small businesses. Our HTTP API was designed to be easy to integrate into your workflow.

We have done our best to follow [REST](https://en.wikipedia.org/wiki/Representational_state_transfer) principles when designing the API. **Please note that this API is currently in beta and subject to change.** Any changes or new additions will be announced in the [changelog](CHANGELOG.md).

### API Endpoint

    https://api.invoiced.com

### Formatting

All responses will be in [JSON](https://en.wikipedia.org/wiki/JSON). Input data passed through the request body can be form-encoded or JSON-encoded. If using a JSON body, please specify the `Content-Type` header as `application/json`.

Dates are input and displayed as [UNIX timestamps](https://en.wikipedia.org/wiki/Unix_time) in the API. Entity IDs are represented by integers.

### Issues, Suggestions, and Contributions

Please report any issues or suggestions in the [issues](https://github.com/invoiced/api/issues). If you need help using the API or need to discuss anything sensitive please message us at api@invoiced.com. Any pull requests to improve this document are welcome!

## Authentication

The API uses [HTTP Basic Authentication](https://en.wikipedia.org/wiki/Basic_access_authentication) to authenticate users. A valid API key is required for all requests. Also, **all requests must use HTTPS.** Any HTTP requests will be ignored.

### Obtaining an API Key

An API key can be obtained by signing in to [invoiced.com](https://invoiced.com), and then going to **Settings** -> **API Keys**. Each business on Invoiced has its own set of API keys. We recommend creating a separate API key for each application that will be making calls on your behalf.

### Usage

The API key must be passed in through the username with the password left blank. Here is an example using [curl](http://curl.haxx.se/):

    curl -u {YOUR_API_KEY}: https://api.invoiced.com/invoices

## Errors

A 4xx or 5xx status code will be returned upon a failed request.

Possible error codes:

* `401` Unauthorized - missing or invalid API key
* `403` Forbidden - correctly authenticated but missing permission to execute the request
* `404` Not Found - returned when trying to access an entity that does not exist
* `500` Internal Server Error - something has broke on our end

## Special Parameters

### Expanding Relations

Usually you need to request more than just an invoice. Often, you might want data about the associated customer. There is a built-in way to do this that saves extra API requests.

Relational properties can be expanded by passing in a comma-separated list of properties to expand through the `expand` parameter i.e. `expand=customer,invoice`. This will replace the ID with an object containing the entity's properties.

The `expand` parameter works on most requests that return one or more entities.

### Human-readable JSON

Set the `pretty` parameter to true to get a readable response, i.e. `pretty=1`.

### Filter

With the `filter` parameter allows you to search entities based on an exact match. While it is not meant to replace a search API, the `filter` parameter can be useful if you need to look up a customer by name or want to list all overdue invoices. It can be used on many of the list endpoints.

The `filter` parameter is an object whose keys are the properties that should be matched:

```
filter: {
	paid: false,
	customer: 1234
}
```

## Customers

### List Customers
	
	GET /customers

#### Parameters

Name | Type | Description
-----|------|-------------
`sort`|`string`|Column to sort by, i.e. `name asc`
`filter`|`object`|[Filter](#filter)

#### Response

```
Status: 200 OK
Link: <>; rel="self", <>; rel="first", ...
X-Total-Count: 10
```

```json
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
        ...
    ]
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

## Estimates

### List Estimates

	GET /estimates

#### Parameters

Name | Type | Description
-----|------|-------------
`sort`|`string`|Column to sort by, i.e. `name asc`
`filter`|`object`|[Filter](#filter)

#### Response

```
Status: 200 OK
Link: <>; rel="self", <>; rel="first", ...
X-Total-Count: 10
```

```json
TODO
```

### Creating an Estimate

	POST /estimates

#### Input

```json
TODO
```

#### Response

	Status: 201 Created

```json
TODO
```

### Fetch an Estimate

	GET /estimates/:id

#### Response

	Status: 200 OK

```json
TODO
```

### Editing an Estimate

	PATCH /estimates/:id

#### Input

```json
TODO
```

#### Response

	Status: 200 OK

```json
{
	"success": true
}
```

### Sending an Estimate

	POST /estimates/:id/emails

#### Input

```json
TODO
```

#### Response

	Status: 200 OK

```json
{
	"success": true
}
```

### Converting an Estimate into an Invoice

	POST /estimates/:id/invoice

### Deleting an Estimate

	DELETE /estimates/:id

#### Response

	Status: 204 No Content

## Invoices

### List Invoices

	GET /invoices

#### Parameters

Name | Type | Description
-----|------|-------------
`sort`|`string`|Column to sort by, i.e. `name asc`
`filter`|`object`|[Filter](#filter)
`status`|`string`|Can be `paid`,`sent`,`overdue`,`not_sent`, or `unpaid`

#### Response

```
Status: 200 OK
Link: <>; rel="self", <>; rel="first", ...
X-Total-Count: 10
```

```json
```

### Creating an Invoice

	POST /invoices

#### Input

```json
TODO
```

#### Response

	Status: 201 Created

```json
TODO
```

### Fetch an Invoice
	
	GET /invoices/:id

#### Response

	Status: 200 OK

```json
TODO
```

### Editing an Invoice

	PATCH /invoices/:id

#### Input

```json
TODO
```

#### Response

	Status: 200 OK

```json
{
	"success": true
}
```

### Sending an Invoice

	POST /invoices/:id/emails

#### Input

```json
TODO
```

#### Response

	Status: 200 OK

```json
{
	"success": true
}
```

### Deleting an Invoice

	DELETE /invoices/:id

#### Response

	Status: 204 No Content

## Payments

### List Payments

	GET /payments

#### Parameters

Name | Type | Description
-----|------|-------------
`sort`|`string`|Column to sort by, i.e. `name asc`
`filter`|`object`|[Filter](#filter)

#### Response

```
Status: 200 OK
Link: <>; rel="self", <>; rel="first", ...
X-Total-Count: 10
```

```json
payments: [
	{
           "created_at": 1415228628,
           "updated_at": 1415228642,
           "id": 20939,
           "company": 3694,
           "customer": 15460,
           "invoice": 44648,
           "date": 1410843600,
           "type": "check",
           "currency": "USD",
           "amount": 800,
           "fee": 0,
           "net": 800,
           "notes": null,
           "check_no": null,
           "stripe_charge": "",
           "paypal_transaction_id": "",
		   "pdf_url": "https://invoiced.com/dundermifflin/CUST-001/INV-001/20939/pdf"
	},
    ...
   ]
```

### Creating a Payment

	POST /payments

#### Input

```json
TODO
```

#### Response

	Status: 201 Created

```json
TODO
```

### Fetch a Payment

	GET /payments/:id

#### Response

	Status: 200 OK

```json
payment: {
    "created_at": 1415228628,
    "updated_at": 1415228642,
    "id": 20939,
    "company": 3694,
    "customer": 15460,
    "invoice": 44648,
    "date": 1410843600,
    "type": "check",
    "currency": "USD",
    "amount": 800,
    "fee": 0,
    "net": 800,
    "notes": null,
    "check_no": null,
    "stripe_charge": "",
    "paypal_transaction_id": "",
    "pdf_url": "https://invoiced.com/dundermifflin/CUST-001/INV-001/20939/pdf"
}
```

### Editing a Payment

	PATCH /payments/:id

#### Input

```json
TODO
```

#### Response

	Status: 200 OK

```json
{
	"success": true
}
```

### Sending a Payment Receipt

	POST /payments/:id/emails

#### Input

```json
TODO
```

#### Response

	Status: 200 OK

```json
{
	"success": true
}
```

### Deleting a Payment

	DELETE /payments/:id

#### Response

	Status: 204 No Content