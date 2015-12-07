---
title: Invoiced API Documentation

language_tabs:
  - shell
  - ruby
  - php
  - python

toc_footers:
  - <a href='mailto:support@invoiced.com'>Contact Us</a>

includes:
  - customers
  - invoices
  - transactions
  - subscriptions

search: true
---

# Introduction

Invoiced is an API for businesses to invoice and get paid.

Our [RESTful](https://en.wikipedia.org/wiki/Representational_state_transfer) API was designed to supercharge the billing component of your workflow, application, or backoffice systems while making the integration process as painless as possible. Through the API you can create and send invoices, record payments, manage subscription billing, and much more.

Here's a few pages that might be helpful in addition to this API reference.

- [Sign up for Invoiced](https://invoiced.com/signup)
- [Developer Documentation](https://invoiced.com/docs/dev)

### API Endpoint

All API calls must be made to `https://api.invoiced.com`.

### JSON-only

All responses will be in [JSON](https://en.wikipedia.org/wiki/JSON). Input data passed through the request body can be form-encoded or JSON-encoded. If using a JSON body, please specify the `Content-Type` header as `application/json`.

In the API dates are represented as [UNIX timestamps](https://en.wikipedia.org/wiki/Unix_time). Each entity like customers or invoices has a unique integer ID.

### Client Libraries

We have client libraries available in several languages. If you don't see your language listed then please contact us and we would be happy to help.

- [Ruby](https://github.com/Invoiced/invoiced-ruby)
- [PHP](https://github.com/Invoiced/invoiced-php)
- [Python](https://github.com/Invoiced/invoiced-python)
- [Go](https://github.com/Invoiced/invoiced-go)

### Getting Help or Contributing

We've made this document open source. Please report any issues or suggestions in the [API doc issues](https://github.com/invoiced/api/issues). Any pull requests to improve this document are welcome too! If you need help using the API or need to discuss anything sensitive please message us at [support@invoiced.com](mailto:support@invoiced.com).


# Authentication

The API uses [HTTP Basic Authentication](https://en.wikipedia.org/wiki/Basic_access_authentication) to authenticate users. A valid API key is required for all requests.

<aside class="warning">
<strong>Use HTTPS only!</strong> Any HTTP requests will be ignored.
</aside>

### Obtaining an API Key

An API key can be obtained by signing in to [invoiced.com](https://invoiced.com), and then going to **Settings** > **API Keys**. Each business on Invoiced has its own set of API keys. We recommend creating a separate API key for each application that will be making calls on your behalf.

### Usage

```shell
curl https://api.invoiced.com/invoices \
  -u {YOUR_API_KEY}:
```

```ruby
require "invoiced"
invoiced = Invoiced::Client.new("{YOUR_API_KEY}")
```

```php
<?php

$invoiced = new Invoiced\Client("{YOUR_API_KEY}");
```

```python
import invoiced

client = invoiced.Client("{YOUR_API_KEY}")
```

The API key must be passed in through the username with the password left blank. The right sidebar has an example request with authorization

<aside class="notice">
You must replace <code>{API_KEY}</code> with your account API key.
</aside>

# Errors

Each API call returns an HTTP status code that reflects the nature of the response. We have done our best to follow the [HTTP status code](https://en.wikipedia.org/wiki/List_of_HTTP_status_codes) conventions.

Any request that did not succeed will return a 4xx or 5xx error. The 4xx range means there was a problem with the request, like a missing parameter. The 5xx range means that something went wrong on our end.

> The Invoiced API returns the following HTTP status codes:<br/><br/>
200 OK -- Request succeeded<br/>
201 Created -- A resource was created<br/>
204 No Content -- Request succeeded but there is no response body<br/><br/>
400 Bad Request -- Invalid request parameters<br/>
401 Unauthorized -- Incorrect or missing API key<br/>
403 Forbidden -- You do not have permission to view a resource or perform an action<br/>
404 Not Found -- The specified resource could not be found<br/>
429 Too Many Requests -- You're moving too fast! Slow down!<br/>
500 Internal Server Error -- There was a problem on our end

All error responses will contain an object with these attributes

Parameter | Description
--------- | -----------
**type** | Type of error, `invalid_request` or `api`
**message** | Explanation of the error
**param** | Available when a specific request parameter was responsible

# Pagination

```
Link: <https://api.invoiced.com/customers?page=3&per_page=10>; rel="self",
	  <https://api.invoiced.com/customers?page=1&per_page=10>; rel="first",
	  <https://api.invoiced.com/customers?page=2&per_page=10>; rel="previous",
	  <https://api.invoiced.com/customers?page=4&per_page=10>; rel="next",
	  <https://api.invoiced.com/customers?page=5&per_page=10>; rel="last"
```

All list operations will be paginated in similar fashion as the GitHub API. In most cases we will paginate requests returning more than 100 results. You can control pagination with the `page` and `per_page` parameters. Pages start at `1` and the first page will be returned if no page is specified.

When traversing the pages, we recommend using the `Link` and `X-Total-Count` headers. The [Link header](http://tools.ietf.org/html/rfc5988) will return URLs that you can use to traverse the API without having to write your own. It's preferred to use the links from the API because it protects against future updates.

# Versioning

Any future changes to the API will be versioned in order to maintain backwards compatibility with existing integrations.

# Special Parameters

### Expanding Relations

Usually you need to request more than just an invoice. Often, you might want data about the associated customer. There is a built-in way to do this that saves extra API requests.

Certain relational properties can be expanded by passing in a comma-separated list of properties to expand through the `expand` parameter. For example if you were requesting a payment and wanted to expand the associated customer and invoice objects you would set `expand=customer,invoice`. This will replace the ID on the `customer` and `invoice` properties with expanded objects.

The `expand` parameter works for any response that has relational properties.

### Filter

```shell
"filter": {
	"paid": false,
	"customer": 1234
}
```

```ruby
:filter => {
  :paid => false,
  :customer => 1234
}
```

```php
"filter" => [
  "paid" => false,
  "customer" => 1234
]
```

```python
"filter": {
  "paid": False,
  "customer": 1234
}
```

The `filter` parameter allows you to search entities based on an exact match. While it is not meant to replace a search API, the `filter` parameter can be useful if you need to look up a customer by name or want to list all overdue invoices. It can be used on many of the list endpoints.

The `filter` parameter is an object whose keys are the properties that should be matched:
