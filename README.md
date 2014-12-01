Invoiced API
===

Documentation for the Invoiced API

## Table of Contents
* [Introduction](#introduction)
* [Authentication](#authentication)
* [Errors](#errors)
* [Customers](#customers)
* [Estimates](#estimates)
* [Invoices](#invoices)
* [Payments](#payments)

## Introduction

Invoiced is simple invoicing for freelancers and small businesses. Our HTTP API was designed to be easy to integrate into your workflow.

We have done our best to follow [REST](https://en.wikipedia.org/wiki/Representational_state_transfer) principles when designing the API. **Please note that this API is currently in beta and subject to change.** Any changes or new additions will be announced in the [changelog](CHANGELOG.md).

All responses will be in [JSON](https://en.wikipedia.org/wiki/JSON). Input data passed through the request body can be form-encoded or JSON-encoded. If using a JSON body, please specify the `Content-Type` header as `application/json`.

### API Endpoint

```
https://api.invoiced.com
```

## Authentication

The API uses [HTTP Basic Authentication](https://en.wikipedia.org/wiki/Basic_access_authentication) to authenticate users. A valid API key is required for all requests. Also, **all requests must use HTTPS.** Any HTTP requests will be ignored.

### Obtaining an API Key

An API key can be obtained by signing in to [invoiced.com](https://invoiced.com), and then going to **Settings** -> **API Keys**. Each business on Invoiced has its own set of API keys. We recommend creating a separate API key for each application that will be making calls on your behalf.

### Usage

The API key must be passed in through the username with the password left blank. Here is an example using [curl](http://curl.haxx.se/):

```bash
curl -u {YOUR_API_KEY}: https://api.invoiced.com/invoices
```

## Errors

A 4xx or 5xx status code will be returned upon a failed request.

Common error codes:

* `401` Unauthorized - missing or invalid API key
* `403` Forbidden - correctly authenticated but missing permission to execute the request
* `404` Not Found - returned when trying to access an entity that does not exist
* `500` Internal Server Error - something has broke on our end

## Customers

### Creating a Customer

### Editing a Customer

### Deleting a Customer

## Estimates

### Creating an Estimate

### Sending an Estimate

### Downloading an Estimate PDF

### Editing an Estimate

### Deleting an Estimate

## Invoices

### Creating an Invoice

### Sending an Invoice

### Downloading an Invoice PDF

### Editing an Invoice

### Deleting an Invoice

## Payments

### Creating a Payment

### Sending a Payment Receipt

### Downloading a Payment Receipt PDF

### Deleting a Payment
