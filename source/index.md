---
title: Invoiced API Documentation

language_tabs:
  - shell
  - ruby
  - php
  - python
  - java

toc_footers:
  - <a href="mailto:support@invoiced.com">Contact Us</a>

includes:
  - customers
  - invoicing
  - payments
  - subscription_billing
  - metered_billing
  - pricing
  - events
  - files

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

We also have a sandbox environment for testing available at `https://api.sandbox.invoiced.com`.

### JSON-only

All responses will be in [JSON](https://en.wikipedia.org/wiki/JSON). Input data passed through the request body can be form-encoded or JSON-encoded. If using a JSON body, please specify the `Content-Type` header as `application/json`.

In the API dates are represented as [UNIX timestamps](https://en.wikipedia.org/wiki/Unix_time). Each entity like customers or invoices has a unique integer ID.

### Client Libraries

We have client libraries available in several languages. If you don't see your language listed then please contact us and we would be happy to help.

- [Ruby](https://github.com/Invoiced/invoiced-ruby)
- [PHP](https://github.com/Invoiced/invoiced-php)
- [Python](https://github.com/Invoiced/invoiced-python)
- [Go](https://github.com/Invoiced/invoiced-go)
- [Java](https://github.com/Invoiced/invoiced-java)

### Getting Help or Contributing

We've made this document open source. Please report any issues or suggestions in the [API doc issues](https://github.com/invoiced/api/issues). Any pull requests to improve this document are welcome too! If you need help using the API or need to discuss anything sensitive please message us at [support@invoiced.com](mailto:support@invoiced.com).


# Authentication

The API uses [HTTP Basic Authentication](https://en.wikipedia.org/wiki/Basic_access_authentication) to authenticate users. A valid API key is required for all requests.

<aside class="warning">
<strong>Use HTTPS only!</strong> Any HTTP requests will be ignored.
</aside>

### Obtaining an API Key

An API key can be obtained by signing in to [invoiced.com](https://invoiced.com), and then going to **Settings** > **Developers** > **API Keys**. Each business on Invoiced has its own set of API keys. We recommend creating a separate API key for each application that will be making calls on your behalf.

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

```java
import com.invoiced.entity.Connection;

Connection invoiced = new Connection("{YOUR_API_KEY}",false);
```

The API key must be passed in through the username with the password left blank. The right sidebar has an example request with authorization

<aside class="notice">
You must replace <code>{API_KEY}</code> with your account API key.
</aside>

### Sandbox API

```shell
curl https://api.sandbox.invoiced.com/invoices \
  -u {YOUR_SANDBOX_API_KEY}:
```

```ruby
require "invoiced"
invoiced = Invoiced::Client.new("{YOUR_SANDBOX_API_KEY}", true)
```

```php
<?php

$invoiced = new Invoiced\Client("{YOUR_SANDBOX_API_KEY}", true);
```

```python
import invoiced

client = invoiced.Client("{YOUR_SANDBOX_API_KEY}", True)
```

```java
import com.invoiced.entity.Connection;

Connection invoiced = new Connection("{YOUR_API_KEY}",true);
```

You can sign up for a sandbox account at [sandbox.invoiced.com](https://sandbox.invoiced.com) and request an API key there. The steps for requesting an API key are the same as production.

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

# Metadata

```shell
curl "https://api.invoiced.com/customers" \
  -u {API_KEY}: \
  -d name="Acme" \
  -d metadata[icp_number]="1234567890" \
  -d metadata[account_rep]="Jan"
```

```ruby
invoiced.Customer.create(
  :name => "Acme",
  :metadata => {
    :icp_number => "1234567890",
    :account_rep => "Jan"
  }
)
```

```php
<?php

$invoiced->Customer->create([
  'name' => "Acme",
  'metadata' => [
    'icp_number' => "1234567890",
    'account_rep' => "Jan"
  ]
]);
```

```python
client.Customer.create(
  name="Acme",
  metadata={
    'icp_number': "1234567890",
    'account_rep': "Jan"
  }
)
```

```java 
HashMap<String, Object> params = new HashMap<String, Object>();
params.put("icp_number", "1234567890");
params.put("account_rep","Jan");
Customer customer = invoiced.newCustomer();
customer.name = "Acme";
customer.metaData = params;
customer.create();
```

> The above command returns JSON structured like this:

```shell
{
  "id": 15444,
  "number": "CUST-0001",
  "name": "Acme",
  "email": null,
  "collection_mode": "manual",
  "payment_terms": null,
  "payment_source": null,
  "taxes": [],
  "type": "company",
  "attention_to": null,
  "address1": null,
  "address2": null,
  "city": null,
  "state": null,
  "postal_code": null,
  "country": "US",
  "tax_id": null,
  "phone": null,
  "notes": null,
  "statement_pdf_url": "https://dundermifflin.invoiced.com/statements/15444/pdf",
  "created_at": 1415222128,
  "metadata": {
    "icp_number": "1234567890",
    "account_rep": "Jan"
  }
}
```

```ruby
#<Invoiced::Customer:0x3fdbf95e4d08 id=15444> JSON: {
  "id": 15444,
  "number": "CUST-0001",
  "name": "Acme",
  "email": null,
  "collection_mode": "manual",
  "payment_terms": null,
  "payment_source": null,
  "taxes": [],
  "type": "company",
  "attention_to": null,
  "address1": null,
  "address2": null,
  "city": null,
  "state": null,
  "postal_code": null,
  "country": "US",
  "tax_id": null,
  "phone": null,
  "notes": null,
  "statement_pdf_url": "https://dundermifflin.invoiced.com/statements/15444/pdf",
  "created_at": 1415222128,
  "metadata": {
    "icp_number": "1234567890",
    "account_rep": "Jan"
  }
}
```

```php
Invoiced\Customer JSON: {
  "id": 15444,
  "number": "CUST-0001",
  "name": "Acme",
  "email": null,
  "collection_mode": "manual",
  "payment_terms": null,
  "payment_source": null,
  "taxes": [],
  "type": "company",
  "attention_to": null,
  "address1": null,
  "address2": null,
  "city": null,
  "state": null,
  "postal_code": null,
  "country": "US",
  "tax_id": null,
  "phone": null,
  "notes": null,
  "statement_pdf_url": "https://dundermifflin.invoiced.com/statements/15444/pdf",
  "created_at": 1415222128,
  "metadata": {
    "icp_number": "1234567890",
    "account_rep": "Jan"
  }
}
```

```python
<Customer id=15444 at 0x3fdbf95e4d08> JSON: {
  "id": 15444,
  "number": "CUST-0001",
  "name": "Acme",
  "email": null,
  "collection_mode": "manual",
  "payment_terms": null,
  "payment_source": null,
  "taxes": [],
  "type": "company",
  "attention_to": null,
  "address1": null,
  "address2": null,
  "city": null,
  "state": null,
  "postal_code": null,
  "country": "US",
  "tax_id": null,
  "phone": null,
  "notes": null,
  "statement_pdf_url": "https://dundermifflin.invoiced.com/statements/15444/pdf",
  "created_at": 1415222128,
  "metadata": {
    "icp_number": "1234567890",
    "account_rep": "Jan"
  }
}
```

```java
com.invoiced.entity.Customer@cb8fd59 JSON: {
  "id": 15444,
  "number": "CUST-0001",
  "name": "Acme",
  "collection_mode": "manual",
  "type": "company",
  "country": "US",
  "statement_pdf_url": "https://dundermifflin.invoiced.com/statements/15444/pdf",
  "created_at": 1415222128,
  "metadata": {
    "icp_number": "1234567890",
    "account_rep": "Jan"
  }
}
```

Most Invoices objects have a `metadata` attribute. This parameter allows you to store custom key-value data on supported objects.

The use cases for metadata are many. Any time you want to store custom, structured data on an object, like a Customer, Invoice, or Transaction, then metadata is a great fit. Metadata is only visible within the API and on the dashboard. Customers will not see this data unless you choose to display it.

Metadata can include up to **10 keys per object**. Each key can be up to 40 characters long and values may be up to 255 characters long.

# Special Parameters

### Expanding Relations

```shell
curl "https://api.invoiced.com/invoices/:id?expand=customer" \
  -u {API_KEY}:
```

```ruby
invoice = invoiced.Invoice.retrieve("{INVOICE_ID}", {
  :expand => "customer"
})
```

```php
<?php

$invoice = $invoiced->Invoice->retrieve("{INVOICE_ID}", [
  'expand' => "customer"
]);
```

```python
invoice = client.Invoice.retrieve("{INVOICE_ID}", {
  'expand': "customer"
})
```

```java
HashMap<String, Object> params = new HashMap<String, Object>();
params.put("expand", "customer");
Invoice invoice = invoiced.newInvoice().retrieve("{INVOICE_ID}", params);
```

Usually you need to request more than just an invoice. Often, you might want data about the associated customer. There is a built-in way to do this that saves extra API requests.

Certain relational properties can be expanded by passing in a comma-separated list of properties to expand through the `expand` parameter. For example if you were requesting a payment and wanted to expand the associated customer and invoice objects you would set `expand=customer,invoice`. This will replace the ID on the `customer` and `invoice` properties with expanded objects.

The `expand` parameter works for any response that has relational properties.

### Filter

> Example retrieving a list of outstanding invoices for a customer:

```shell
curl "https://api.invoiced.com/invoices?filter%5Bpaid%5D=0&filter%5Bclosed%5D=0&filter%5Bcustomer%5D=1234" \
  -u {API_KEY}:
```

```ruby
invoices = invoiced.Invoice.list(
  :filter => {
    :paid => false,
    :closed => false,
    :customer => 1234
  }
)
```

```php
<?php

$invoices = $invoiced->Invoice->all([
  'filter' => [
    'paid' => false,
    'closed' => false,
    'customer' => 1234
  ]
]);
```

```python
invoices = client.Invoice.list(
  filter={
    'paid': False,
    'closed': False,
    'customer': 1234
  }
)
```

```java
HashMap<String, Object> params = new HashMap<String, Object>();
params.put("filter[paid]", false);
params.put("filter[closed]", false);
params.put("filter[customer]", 1234);
EntityList<Invoice> invoices = invoiced.newInvoice().listAll(filter);
```

The `filter` parameter allows you to search entities based on an exact match. While it is not meant to replace a search API, the `filter` parameter can be useful if you need to look up a customer by name or want to list all overdue invoices. It can be used on many of the list endpoints.

The `filter` parameter is an object whose keys are the properties that should be matched.

### Metadata Filter

> Example retrieving customers with a matching `account-rep` metadata value:

```shell
curl "https://api.invoiced.com/customers?metadata%5Baccount-rep%5D=Jan" \
  -u {API_KEY}:
```

```ruby
customer = invoiced.Customer.list(
  :metadata => {
    'account-rep' => "Jan"
  }
)
```

```php
<?php

$customer = $invoiced->Customer->all([
  'metadata' => [
    'account-rep' => "Jan"
  ]
]);
```

```python
customer = client.Customer.list(
  metadata={
    'account-rep': "Jan"
  }
)
```

```java
HashMap<String, Object> params = new HashMap<String, Object>();
params.put("metadata[account-rep]", "Jan");
EntityList<Customer> customers = invoiced.newCustomer().listAll(params);
```

The `metadata` parameter behaves in a similar fashion to the `filter` parameter. It allows you to search entities that have an exactly matching metadata value for each constraint given. It can be used on any of the list endpoints for objects that support metadata.

The `metadata` parameter is an object whose keys should exactly match the metadata of the objects returned. If an object does not have a metadata value for a given key then the object will not be included in the result set, with no error being thrown.
