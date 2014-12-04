Invoiced API
===

## Table of Contents
* [Introduction](#introduction)
* [Authentication](#authentication)
* [Errors](#errors)
* [Special Parameters](#special-parameters)
* [Endpoints](#endpoints)
	* [Customers](Endpoints/Customers.md)
	* [Estimates](Endpoints/Estimates.md)
	* [Invoices](Endpoints/Invoices.md)
	* [Payments](Endpoints/Payments.md)

## Introduction

Invoiced is simple invoicing for freelancers and small businesses. Our HTTP API was designed to be easy to integrate into your workflow.

We have done our best to follow [REST](https://en.wikipedia.org/wiki/Representational_state_transfer) principles when designing the API. **Please note that this API is currently in beta and subject to change.** Any changes or new additions will be announced in the [changelog](CHANGELOG.md). You can also receive API-related announcements [@invoicedapi](https://twitter.com/invoicedapi).

### API Endpoint

    https://api.invoiced.com

### JSON-only

All responses will be in [JSON](https://en.wikipedia.org/wiki/JSON). Input data passed through the request body can be form-encoded or JSON-encoded. If using a JSON body, please specify the `Content-Type` header as `application/json`.

In the API dates are represented as [UNIX timestamps](https://en.wikipedia.org/wiki/Unix_time). Each entity like customers or invoices has a unique integer id.

### Getting Help or Contributing

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

The `filter` parameter allows you to search entities based on an exact match. While it is not meant to replace a search API, the `filter` parameter can be useful if you need to look up a customer by name or want to list all overdue invoices. It can be used on many of the list endpoints.

The `filter` parameter is an object whose keys are the properties that should be matched:

```json
filter: {
	"paid": false,
	"customer": 1234
}
```

## Endpoints
* [Customers](Endpoints/Customers.md)
* [Estimates](Endpoints/Estimates.md)
* [Invoices](Endpoints/Invoices.md)
* [Payments](Endpoints/Payments.md)