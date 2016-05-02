# Customers

Customers represent the entity you are billing, whether this is an organization or a individual. Each customer has a collection mode, automatic or manual. In automatic collection mode any invoices will be charged to your customer's payment source. Currently we only support debit and credit cards as payment sources.

Conversely, manual collection mode will let your customers pay each invoice issued with one of the payment methods you accept.

## Customer Object

### Attributes

```shell
{
  "id": 15444,
  "name": "Acme",
  "number": "CUST-0001",
  "email": "billing@acmecorp.com",
  "collection_mode": "auto",
  "payment_terms": null,
  "payment_source": {
    "id": 850,
    "object": "card",
    "brand": "Visa",
    "last4": 4242,
    "exp_month": 2,
    "exp_year": 20,
    "funding": "credit"
  },
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
  "metadata": {}
}
```

```ruby
#<Invoiced::Customer:0x3fdbf95e4d08 id=15444> JSON: {
  "id": 15444,
  "name": "Acme",
  "number": "CUST-0001",
  "email": "billing@acmecorp.com",
  "collection_mode": "auto",
  "payment_terms": null,
  "payment_source": {
    "id": 850,
    "object": "card",
    "brand": "Visa",
    "last4": 4242,
    "exp_month": 2,
    "exp_year": 20,
    "funding": "credit"
  },
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
  "metadata": {}
}
```

```php
Invoiced\Customer JSON: {
  "id": 15444,
  "name": "Acme",
  "number": "CUST-0001",
  "email": "billing@acmecorp.com",
  "collection_mode": "auto",
  "payment_terms": null,
  "payment_source": {
    "id": 850,
    "object": "card",
    "brand": "Visa",
    "last4": 4242,
    "exp_month": 2,
    "exp_year": 20,
    "funding": "credit"
  },
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
  "metadata": {}
}
```

```python
<Customer id=15444 at 0x3fdbf95e4d08> JSON: {
  "id": 15444,
  "name": "Acme",
  "number": "CUST-0001",
  "email": "billing@acmecorp.com",
  "collection_mode": "auto",
  "payment_terms": null,
  "payment_source": {
    "id": 850,
    "object": "card",
    "brand": "Visa",
    "last4": 4242,
    "exp_month": 2,
    "exp_year": 20,
    "funding": "credit"
  },
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
  "metadata": {}
}
```

Parameter | Type | Description
--------- | ---- | -----------
**id** | *integer* | The customer's unique ID
**name** | *string* | Customer name
**number** | *string* | A unique ID to help tie your customer to your external systems
**email** | *string* | Email address
**collection_mode** | *string* | Invoice collection mode, `auto` or `manual`
**payment_terms** | *string* | Payment terms used for `manual` collection mode, i.e. "NET 30"
**payment_source** | *object* | Customer's payment source, if attached
**taxes** | *array* | Collection of Tax Rate IDs
**type** | *string* | Organization type, `company` or `person`
**attention_to** | *string* | Used for ATTN: address line if `company`
**address1** | *string* | First address line
**address2** | *string* | Optional second address line
**city** | *string* | City
**state** | *string* | State or province
**postal_code** | *string* | Zip or postal code
**country** | *string* | [Two-letter ISO code](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2)
**tax_id** | *string* | Tax ID to be displayed on documents
**phone** | *string* | Phone #
**notes** | *string* | Private customer notes
**statement_pdf_url** | *string* | URL to download the latest account statement
**created_at** | *timestamp* | Timestamp when created
**metadata** | *object* | A hash of key/value pairs that can store additional information about this object.

## Card Object

### Attributes

```shell
{
  "id": 850,
  "object": "card",
  "brand": "Visa",
  "last4": 4242,
  "exp_month": 2,
  "exp_year": 20,
  "funding": "credit"
}
```

```ruby
#<Invoiced::Card:0x3fdbf95e4d08 id=850> JSON: {
  "id": 850,
  "object": "card",
  "brand": "Visa",
  "last4": 4242,
  "exp_month": 2,
  "exp_year": 20,
  "funding": "credit"
}
```

```php
Invoiced\Card JSON: {
  "id": 850,
  "object": "card",
  "brand": "Visa",
  "last4": 4242,
  "exp_month": 2,
  "exp_year": 20,
  "funding": "credit"
}
```

```python
<Card id=850 at 0x3fdbf95e4d08> JSON: {
  "id": 850,
  "object": "card",
  "brand": "Visa",
  "last4": 4242,
  "exp_month": 2,
  "exp_year": 20,
  "funding": "credit"
}
```

Parameter | Type | Description
--------- | ---- | -----------
**id** | *integer* | The card's unique ID
**object** | *string* | `card`
**brand** | *string* | Card brand
**last4** | *integer* | Last 4 digits of card
**exp_month** | *integer* | Expiry month
**exp_year** | *integer* | Expiry year
**funding** | *string* | Funding instrument, can be `credit`, `debit`, `prepaid`, or `unknown`

## Bank Account Object

### Attributes

```shell
{
  "id": 4321,
  "object": "card",
  "bank_name": "Wells Fargo",
  "last4": 7890,
  "routing_number": 110000000,
  "verified": true,
  "currency": "usd"
}
```

```ruby
#<Invoiced::BankAccount:0x3fdbf95e4d08 id=4321> JSON: {
  "id": 4321,
  "object": "card",
  "bank_name": "Wells Fargo",
  "last4": 7890,
  "routing_number": 110000000,
  "verified": true,
  "currency": "usd"
}
```

```php
Invoiced\BankAccount JSON: {
  "id": 4321,
  "object": "card",
  "bank_name": "Wells Fargo",
  "last4": 7890,
  "routing_number": 110000000,
  "verified": true,
  "currency": "usd"
}
```

```python
<BankAccount id=4321 at 0x3fdbf95e4d08> JSON: {
  "id": 4321,
  "object": "card",
  "bank_name": "Wells Fargo",
  "last4": 7890,
  "routing_number": 110000000,
  "verified": true,
  "currency": "usd"
}
```

Parameter | Type | Description
--------- | ---- | -----------
**id** | *integer* | The bank account's unique ID
**object** | *string* | `bank_account`
**bank_name** | *string* | Bank name
**last4** | *integer* | Last 4 digits of bank account
**routing_number** | *integer* | Bank routing number
**verified** | *boolean* | Whether the bank account has been verified with instant verification or micro-deposits
**currency** | *string* | [3-letter ISO code](https://en.wikipedia.org/wiki/ISO_4217)

## Create a customer

```shell
curl "https://api.invoiced.com/customers" \
  -u {API_KEY}: \
  -d name="Acme" \
  -d email="billing@acmecorp.com" \
  -d collection_mode="manual" \
  -d payment_terms="NET 30" \
  -d type="company"
```

```ruby
invoiced.Customer.create(
  :name => "Acme",
  :email => "billing@acmecorp.com",
  :collection_mode => "manual",
  :payment_terms => "NET 30",
  :type => "company"
)
```

```php
<?php

$invoiced->Customer->create([
  'name' => "Acme",
  'email' => "billing@acmecorp.com",
  'collection_mode' => "manual",
  'payment_terms' => "NET 30",
  'type' => "company"
]);
```

```python
client.Customer.create(
  name="Acme",
  email="billing@acmecorp.com",
  collection_mode="manual",
  payment_terms="NET 30",
  type="company"
)
```

> The above command returns JSON structured like this:

```shell
{
  "id": 15444,
  "number": "CUST-0001",
  "name": "Acme",
  "email": "billing@acmecorp.com",
  "collection_mode": "manual",
  "payment_terms": "NET 30",
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
  "metadata": {}
}
```

```ruby
#<Invoiced::Customer:0x3fdbf95e4d08 id=15444> JSON: {
  "id": 15444,
  "number": "CUST-0001",
  "name": "Acme",
  "email": "billing@acmecorp.com",
  "collection_mode": "manual",
  "payment_terms": "NET 30",
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
  "metadata": {}
}
```

```php
Invoiced\Customer JSON: {
  "id": 15444,
  "number": "CUST-0001",
  "name": "Acme",
  "email": "billing@acmecorp.com",
  "collection_mode": "manual",
  "payment_terms": "NET 30",
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
  "metadata": {}
}
```

```python
<Customer id=15444 at 0x3fdbf95e4d08> JSON: {
  "id": 15444,
  "number": "CUST-0001",
  "name": "Acme",
  "email": "billing@acmecorp.com",
  "collection_mode": "manual",
  "payment_terms": "NET 30",
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
  "metadata": {}
}
```

Create a new customer profile with this endpoint.

### HTTP Request

`POST /customers`

### Attributes

Parameter | Type | Description
--------- | ---- | -----------
**name** | *string* | Customer name - **required**
**number** | *string* | A unique ID to help tie your customer to your external systems. We will generate one if not supplied.
**email** | *string* | Email address
**collection_mode** | *string* | Invoice collection mode, `auto` or `manual`. Defaults to `manual`
**payment_terms** | *string* | Payment terms used for `manual` collection mode, i.e. "NET 30"
**stripe_token** | *string* | When provided sets the customer's payment source to the tokenized Stripe card
**taxes** | *array* | Collection of Tax Rate IDs
**type** | *string* | Organization type, `company` or `person`. Defaults to `company`
**attention_to** | *string* | Used for ATTN: address line if `company`
**address1** | *string* | First address line
**address2** | *string* | Optional second address line
**city** | *string* | City
**state** | *string* | State or province
**postal_code** | *string* | Zip or postal code
**country** | *string* | [Two-letter ISO code](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2)
**tax_id** | *string* | Tax ID to be displayed on documents
**phone** | *string* | Phone #
**notes** | *string* | Private customer notes
**metadata** | *object* | A hash of key/value pairs that can store additional information about this object.

## Retrieve a customer

```shell
curl "https://api.invoiced.com/customers/:id" \
  -u {API_KEY}:
```

```ruby
customer = invoiced.Customer.retrieve("{CUSTOMER_ID}")
```

```php
<?php

$customer = $invoiced->Customer->retrieve("{CUSTOMER_ID}");
```

```python
customer = client.Customer.retrieve("{CUSTOMER_ID}")
```

> The above command returns JSON structured like this:

```shell
{
  "id": 15444,
  "number": "CUST-0001",
  "name": "Acme",
  "email": "billing@acmecorp.com",
  "collection_mode": "manual",
  "payment_terms": "NET 30",
  "payment_source": null,
  "taxes": [],
  "type": "company",
  "attention_to": "Sarah Fisher",
  "address1": "342 Amber St",
  "address2": null,
  "city": "Hill Valley",
  "state": "CA",
  "postal_code": "94523",
  "country": "US",
  "tax_id": "893-934835",
  "phone": "(820) 297-2983",
  "notes": null,
  "statement_pdf_url": "https://dundermifflin.invoiced.com/statements/15444/pdf",
  "created_at": 1415222128,
  "metadata": {}
}
```

```ruby
#<Invoiced::Customer:0x3fdbf95e4d08 id=15444> JSON: {
  "id": 15444,
  "number": "CUST-0001",
  "name": "Acme",
  "email": "billing@acmecorp.com",
  "collection_mode": "manual",
  "payment_terms": "NET 30",
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
  "metadata": {}
}
```

```php
Invoiced\Customer JSON: {
  "id": 15444,
  "number": "CUST-0001",
  "name": "Acme",
  "email": "billing@acmecorp.com",
  "collection_mode": "manual",
  "payment_terms": "NET 30",
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
  "metadata": {}
}
```

```python
<Customer id=15444 at 0x3fdbf95e4d08> JSON: {
  "id": 15444,
  "number": "CUST-0001",
  "name": "Acme",
  "email": "billing@acmecorp.com",
  "collection_mode": "manual",
  "payment_terms": "NET 30",
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
  "metadata": {}
}
```

This endpoint retrieves a specific customer.

### HTTP Request

`GET /customers/:id`

## Update a customer

```shell
curl "https://api.invoiced.com/customers/:id" \
  -u {API_KEY}: \
  -d payment_terms="NET 14" \
  -d attention_to="Sarah Fisher" \
  -d address1="342 Amber St" \
  -d city="Hill Valley" \
  -d state="CA" \
  -d postal_code="94523" \
  -d tax_id="893-934835" \
  -d phone="(820) 297-2983" \
  -X PATCH
```

```ruby
customer.payment_terms = "NET 14"
customer.attention_to = "Sarah Fisher"
customer.address1 = "342 Amber St"
customer.city = "Hill Valley"
customer.state = "CA"
customer.postal_code = "94523"
customer.tax_id = "893-934835"
customer.phone = "(820) 297-2983"
customer.save
```

```php
<?php

$customer->payment_terms = "NET 14";
$customer->attention_to = "Sarah Fisher";
$customer->address1 = "342 Amber St";
$customer->city = "Hill Valley";
$customer->state = "CA";
$customer->postal_code = "94523";
$customer->tax_id = "893-934835";
$customer->phone = "(820) 297-2983";
$customer->save();
```

```python
customer.payment_terms = "NET 14"
customer.attention_to = "Sarah Fisher"
customer.address1 = "342 Amber St"
customer.city = "Hill Valley"
customer.state = "CA"
customer.postal_code = "94523"
customer.tax_id = "893-934835"
customer.phone = "(820) 297-2983"
customer.save()
```

> The above command returns JSON structured like this:

```shell
{
  "id": 15444,
  "number": "CUST-0001",
  "name": "Acme",
  "email": "billing@acmecorp.com",
  "collection_mode": "manual",
  "payment_terms": "NET 14",
  "payment_source": null,
  "taxes": [],
  "type": "company",
  "attention_to": "Sarah Fisher",
  "address1": "342 Amber St",
  "address2": null,
  "city": "Hill Valley",
  "state": "CA",
  "postal_code": "94523",
  "country": "US",
  "tax_id": "893-934835",
  "phone": "(820) 297-2983",
  "notes": null,
  "statement_pdf_url": "https://dundermifflin.invoiced.com/statements/15444/pdf",
  "created_at": 1415222128,
  "metadata": {}
}
```

```ruby
#<Invoiced::Customer:0x3fdbf95e4d08 id=15444> JSON: {
  "id": 15444,
  "number": "CUST-0001",
  "name": "Acme",
  "email": "billing@acmecorp.com",
  "collection_mode": "manual",
  "payment_terms": "NET 14",
  "payment_source": null,
  "taxes": [],
  "type": "company",
  "attention_to": "Sarah Fisher",
  "address1": "342 Amber St",
  "address2": null,
  "city": "Hill Valley",
  "state": "CA",
  "postal_code": "94523",
  "country": "US",
  "tax_id": "893-934835",
  "phone": "(820) 297-2983",
  "notes": null,
  "statement_pdf_url": "https://dundermifflin.invoiced.com/statements/15444/pdf",
  "created_at": 1415222128,
  "metadata": {}
}
```

```php
Invoiced\Customer JSON: {
  "id": 15444,
  "number": "CUST-0001",
  "name": "Acme",
  "email": "billing@acmecorp.com",
  "collection_mode": "manual",
  "payment_terms": "NET 14",
  "payment_source": null,
  "taxes": [],
  "type": "company",
  "attention_to": "Sarah Fisher",
  "address1": "342 Amber St",
  "address2": null,
  "city": "Hill Valley",
  "state": "CA",
  "postal_code": "94523",
  "country": "US",
  "tax_id": "893-934835",
  "phone": "(820) 297-2983",
  "notes": null,
  "statement_pdf_url": "https://dundermifflin.invoiced.com/statements/15444/pdf",
  "created_at": 1415222128,
  "metadata": {}
}
```

```python
<Customer id=15444 at 0x3fdbf95e4d08> JSON: {
  "id": 15444,
  "number": "CUST-0001",
  "name": "Acme",
  "email": "billing@acmecorp.com",
  "collection_mode": "manual",
  "payment_terms": "NET 14",
  "payment_source": null,
  "taxes": [],
  "type": "company",
  "attention_to": "Sarah Fisher",
  "address1": "342 Amber St",
  "address2": null,
  "city": "Hill Valley",
  "state": "CA",
  "postal_code": "94523",
  "country": "US",
  "tax_id": "893-934835",
  "phone": "(820) 297-2983",
  "notes": null,
  "statement_pdf_url": "https://dundermifflin.invoiced.com/statements/15444/pdf",
  "created_at": 1415222128,
  "metadata": {}
}
```

Use this endpoint to update a customer profile.

### HTTP Request

`PATCH /customers/:id`

### Request Parameters

Parameter | Type | Description
--------- | ---- | -----------
**name** | *string* | Customer name
**number** | *string* | A unique ID to help tie your customer to your external systems
**email** | *string* | Email address
**collection_mode** | *string* | Invoice collection mode, `auto` or `manual`
**payment_terms** | *string* | Payment terms used for `manual` collection mode, i.e. "NET 30"
**stripe_token** | *string* | When provided sets the customer's payment source to the tokenized Stripe card
**taxes** | *array* | Collection of Tax Rate IDs
**type** | *string* | Organization type, `company` or `person`
**attention_to** | *string* | Used for ATTN: address line if `company`
**address1** | *string* | First address line
**address2** | *string* | Optional second address line
**city** | *string* | City
**state** | *string* | State or province
**postal_code** | *string* | Zip or postal code
**country** | *string* | [Two-letter ISO code](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2)
**tax_id** | *string* | Tax ID to be displayed on documents
**phone** | *string* | Phone #
**notes** | *string* | Private customer notes
**metadata** | *object* | A hash of key/value pairs that can store additional information about this object.

## List customer subscriptions

```shell
curl "https://api.invoiced.com/customers/:id/subscriptions" \
  -u {API_KEY}:
```

```ruby
subscriptions, metadata = customer.subscriptions
```

```php
<?php

list($subscriptions, $metadata) = $customer->subscriptions();
```

```python
subscriptions, metadata = customer.subscriptions()
```

> The above command returns JSON structured like this:

```shell
[
  {
      "id": 412,
      "customer": 15444,
      "plan": "starter",
      "start_date": 1415230038,
      "quantity": 1,
      "cycles": null,
      "period_end": 1438813638,
      "period_start": 1436135238,
      "status": "past_due",
      "addons": [
        {
          "catalog_item": "ipad_license",
          "quantity": 5
        }
      ],
      "url": "https://dundermifflin.invoiced.com/subscriptions/ClfLz70YiFSgu5E2dA5qrwXX",
      "created_at": 1415230041,
      "metadata": {}
  },
  {
      "id": 594,
      "customer": 15444,
      "plan": "pro",
      "start_date": 1425572792,
      "quantity": 1,
      "cycles": null,
      "period_end": 1438788392,
      "period_start": 1436109992,
      "status": "active",
      "addons": [],
      "url": "https://dundermifflin.invoiced.com/subscriptions/ir5n8vGRTcsJyBNS8lzR6gXX",
      "created_at": 1425572798,
      "metadata": {}
  }
]
```

```ruby
[
  #<Invoiced::Subscription:0x3fdbf9sf9e4d08 id=412> JSON: {
      "id": 412,
      "customer": 15444,
      "plan": "starter",
      "start_date": 1415230038,
      "quantity": 1,
      "cycles": null,
      "period_end": 1438813638,
      "period_start": 1436135238,
      "status": "past_due",
      "addons": [
        {
          "catalog_item": "ipad_license",
          "quantity": 5
        }
      ],
      "url": "https://dundermifflin.invoiced.com/subscriptions/ClfLz70YiFSgu5E2dA5qrwXX",
      "created_at": 1415230041,
      "metadata": {}
  },
  #<Invoiced::Subscription:0x3fdbf95as4d08 id=594> JSON: {
      "id": 594,
      "customer": 15444,
      "plan": "pro",
      "start_date": 1425572792,
      "quantity": 1,
      "cycles": null,
      "period_end": 1438788392,
      "period_start": 1436109992,
      "status": "active",
      "addons": [],
      "url": "https://dundermifflin.invoiced.com/subscriptions/ir5n8vGRTcsJyBNS8lzR6gXX",
      "created_at": 1425572798,
      "metadata": {}
  }
]
```

```php
[
  Invoiced\Subscription JSON: {
      "id": 412,
      "customer": 15444,
      "plan": "starter",
      "start_date": 1415230038,
      "quantity": 1,
      "cycles": null,
      "period_end": 1438813638,
      "period_start": 1436135238,
      "status": "past_due",
      "addons": [
        {
          "catalog_item": "ipad_license",
          "quantity": 5
        }
      ],
      "url": "https://dundermifflin.invoiced.com/subscriptions/ClfLz70YiFSgu5E2dA5qrwXX",
      "created_at": 1415230041,
      "metadata": {}
  },
  Invoiced\Subscription JSON: {
      "id": 594,
      "customer": 15444,
      "plan": "pro",
      "start_date": 1425572792,
      "quantity": 1,
      "cycles": null,
      "period_end": 1438788392,
      "period_start": 1436109992,
      "status": "active",
      "addons": [],
      "url": "https://dundermifflin.invoiced.com/subscriptions/ir5n8vGRTcsJyBNS8lzR6gXX",
      "created_at": 1425572798,
      "metadata": {}
  }
]
```

```python
[
  <Subscription id=412 at 0x3fdbf95e4d08> JSON: {
      "id": 412,
      "customer": 15444,
      "plan": "starter",
      "start_date": 1415230038,
      "quantity": 1,
      "cycles": null,
      "period_end": 1438813638,
      "period_start": 1436135238,
      "status": "past_due",
      "addons": [
        {
          "catalog_item": "ipad_license",
          "quantity": 5
        }
      ],
      "url": "https://dundermifflin.invoiced.com/subscriptions/ClfLz70YiFSgu5E2dA5qrwXX",
      "created_at": 1415230041,
      "metadata": {}
  },
  <Subscription id=594 at 0x3fdbf95e4d08> JSON: {
      "id": 594,
      "customer": 15444,
      "plan": "pro",
      "start_date": 1425572792,
      "quantity": 1,
      "cycles": null,
      "period_end": 1438788392,
      "period_start": 1436109992,
      "status": "active",
      "addons": [],
      "url": "https://dundermifflin.invoiced.com/subscriptions/ir5n8vGRTcsJyBNS8lzR6gXX",
      "created_at": 1425572798,
      "metadata": {}
  }
]
```

This endpoint lists all the subscriptions for a specific customer.

### HTTP Request

`GET /customers/:id/subscriptions`

### Query Parameters

Parameter | Type | Description
--------- | ---- | -----------
**expand** | *string* | Properties to expand


## Get current balance

```shell
curl "https://api.invoiced.com/customers/balance" \
  -u {API_KEY}:
```

```ruby
customer.balance
```

```php
<?php

$customer->balance();
```

```python
customer.balance()
```

> The above command returns JSON structured like this:

```shell
{
  "available_credits": 50,
  "past_due": false,
  "total_outstanding": 470
}
```

```ruby
{
  :available_credits => 50,
  :past_due => false,
  :total_outstanding => 470
}
```

```php
stdClass {
  "available_credits": 50,
  "past_due": false,
  "total_outstanding": 470
}
```

```python
{
  :available_credits => 50,
  :past_due => false,
  :total_outstanding => 470
}
```

This endpoint calculates the customer's current balance.

### HTTP Request

`GET /customers/:id/balance`

## Send a statement

```shell
curl "https://api.invoiced.com/customers/:id/emails" \
  -u {API_KEY}: \
  -X POST
```

```ruby
emails = customer.send_statement
```

```php
<?php

$emails = $customer->sendStatement();
```

```python
emails = customer.send_statement()
```

> The above command returns JSON structured like this:

```shell
[
  {
    "id": "f45382c6fbc44d44aa7f9a55eb2ce731",
    "state": "sent",
    "reject_reason": null,
    "email": "client@example.com",
    "template": "statement_email",
    "subject": "Statement from Dunder Mifflin, Inc.",
    "message": "Dear Client, we have attached your latest account statement. Thank you!",
    "opens": 0,
    "opens_detail": [],
    "clicks": 0,
    "clicks_detail": [],
    "created_at": 1436890047
  },
  { ... },
  { ... }
]
```

```ruby
[
  #<Invoiced::Email:0x3fdbf95e4d08 id=f45382c6fbc44d44aa7f9a55eb2ce731> JSON: {
    "id": "f45382c6fbc44d44aa7f9a55eb2ce731",
    "state": "sent",
    "reject_reason": null,
    "email": "client@example.com",
    "template": "statement_email",
    "subject": "Statement from Dunder Mifflin, Inc.",
    "message": "Dear Client, we have attached your latest account statement. Thank you!",
    "opens": 0,
    "opens_detail": [],
    "clicks": 0,
    "clicks_detail": [],
    "created_at": 1436890047
  },
  #<Invoiced::Email:0x3fdasdf95e09 id=a0s36fbc44d44aa7f9a55easdfi8ce731> JSON: { ... },
  #<Invoiced::Email:0x3fdbffge4d10 id=s90f2c6fbc44sdfj8aa7f9a55eb2ce731> JSON: { ... }
]
```

```php
[
  Invoiced\Email JSON: {
    "id": "f45382c6fbc44d44aa7f9a55eb2ce731",
    "state": "sent",
    "reject_reason": null,
    "email": "client@example.com",
    "template": "statement_email",
    "subject": "Statement from Dunder Mifflin, Inc.",
    "message": "Dear Client, we have attached your latest account statement. Thank you!",
    "opens": 0,
    "opens_detail": [],
    "clicks": 0,
    "clicks_detail": [],
    "created_at": 1436890047
  },
  Invoiced\Email JSON: { ... },
  Invoiced\Email JSON: { ... }
]
```

```python
[
  <Email id=f45382c6fbc44d44aa7f9a55eb2ce731 at 0x3fdbf95e4d08> JSON: {
    "id": "f45382c6fbc44d44aa7f9a55eb2ce731",
    "state": "sent",
    "reject_reason": null,
    "email": "client@example.com",
    "template": "statement_email",
    "subject": "Statement from Dunder Mifflin, Inc.",
    "message": "Dear Client, we have attached your latest account statement. Thank you!",
    "opens": 0,
    "opens_detail": [],
    "clicks": 0,
    "clicks_detail": [],
    "created_at": 1436890047
  },
  <Email id=a0s36fbc44d44aa7f9a55easdfi8ce731 at 0x3fdasdf95e09> JSON: { ... },
  <Email id=s90f2c6fbc44sdfj8aa7f9a55eb2ce731 at 0x3fdbffge4d10> JSON: { ... }
]
```

This endpoint sends a PDF account statement to a customer.

### HTTP Request

`POST /customers/:id/emails`

### Request Parameters

Parameter | Type | Description
--------- | ---- | -----------
**to** | *array* | Optional array of recipients like:<br/>`[{"name": "Client", "email": "client@example.com"}]`
**bcc** | *string* | Optional comma-separated list of email addresses to be blind carbon copied
**subject** | *string* | Optional subject
**message** | *string* | Optional message body, otherwise the *Statement Email* template is used

<aside class="info">
A successful response means that your email has been added to the send queue.
</aside>

## Delete a customer

```shell
curl "https://api.invoiced.com/customers/:id" \
  -u {API_KEY}: \
  -X DELETE
```

```ruby
customer.delete
```

```php
<?php

$customer->delete();
```

```python
customer.delete()
```

> The above command returns `204 No Content`

This endpoint deletes a specific customer.

### HTTP Request

`DELETE /customers/:id`

## List all customers

```shell
curl "https://api.invoiced.com/customers" \
  -u {API_KEY}:
```

```ruby
customers, metadata = invoiced.Customer.list(:per_page => 3)
```

```php
<?php

list($customers, $metadata) = $invoiced->Customer->all(['per_page' => 3]);
```

```python
customers, metadata = invoiced.Customer.list(per_page=3)
```

> The above command returns JSON structured like this:

```shell
[
  {
    "id": 15444,
    "number": "CUST-0001",
    "name": "Acme",
    "email": "billing@acmecorp.com",
    "collection_mode": "manual",
    "payment_terms": "NET 30",
    "payment_source": null,
    "taxes": [],
    "type": "company",
    "attention_to": "Sarah Fisher",
    "address1": "342 Amber St",
    "address2": null,
    "city": "Hill Valley",
    "state": "CA",
    "postal_code": "94523",
    "country": "US",
    "tax_id": "893-934835",
    "phone": "(820) 297-2983",
    "notes": null,
    "statement_pdf_url": "https://dundermifflin.invoiced.com/statements/15444/pdf",
    "created_at": 1415222128,
    "metadata": {}
  },
  { ... },
  { ... }
]
```

```ruby
[
  #<Invoiced::Customer:0x3fdbf95e4d08 id=15444> JSON: {
    "id": 15444,
    "number": "CUST-0001",
    "name": "Acme",
    "email": "billing@acmecorp.com",
    "collection_mode": "manual",
    "payment_terms": "NET 30",
    "payment_source": null,
    "taxes": [],
    "type": "company",
    "attention_to": "Sarah Fisher",
    "address1": "342 Amber St",
    "address2": null,
    "city": "Hill Valley",
    "state": "CA",
    "postal_code": "94523",
    "country": "US",
    "tax_id": "893-934835",
    "phone": "(820) 297-2983",
    "notes": null,
    "statement_pdf_url": "https://dundermifflin.invoiced.com/statements/15444/pdf",
    "created_at": 1415222128,
    "metadata": {}
  },
  #<Invoiced::Customer:0x3fdbf95e4d09 id=15445> JSON: { ... },
  #<Invoiced::Customer:0x3fdbf95e4d10 id=15446> JSON: { ... }
]
```

```php
[
  Invoiced\Customer JSON: {
    "id": 15444,
    "number": "CUST-0001",
    "name": "Acme",
    "email": "billing@acmecorp.com",
    "collection_mode": "manual",
    "payment_terms": "NET 30",
    "payment_source": null,
    "taxes": [],
    "type": "company",
    "attention_to": "Sarah Fisher",
    "address1": "342 Amber St",
    "address2": null,
    "city": "Hill Valley",
    "state": "CA",
    "postal_code": "94523",
    "country": "US",
    "tax_id": "893-934835",
    "phone": "(820) 297-2983",
    "notes": null,
    "statement_pdf_url": "https://dundermifflin.invoiced.com/statements/15444/pdf",
    "created_at": 1415222128,
    "metadata": {}
  },
  Invoiced\Customer JSON: { ... },
  Invoiced\Customer JSON: { ... }
]
```

```python
[
  <Customer id=15444 at 0x3fdbf95e4d08> JSON: {
    "id": 15444,
    "number": "CUST-0001",
    "name": "Acme",
    "email": "billing@acmecorp.com",
    "collection_mode": "manual",
    "payment_terms": "NET 30",
    "payment_source": null,
    "taxes": [],
    "type": "company",
    "attention_to": "Sarah Fisher",
    "address1": "342 Amber St",
    "address2": null,
    "city": "Hill Valley",
    "state": "CA",
    "postal_code": "94523",
    "country": "US",
    "tax_id": "893-934835",
    "phone": "(820) 297-2983",
    "notes": null,
    "statement_pdf_url": "https://dundermifflin.invoiced.com/statements/15444/pdf",
    "created_at": 1415222128,
    "metadata": {}
  },
  <Customer id=15445 at 0x3fdbf95e4d08> JSON: { ... },
  <Customer id=15446 at 0x3fdbf95e4d08> JSON: { ... }
]
```

This endpoint retrieves all customers.

### HTTP Request

`GET /customers`

### Query Parameters

Parameter | Description
--------- | -----------
**sort** *string* | Column to sort by, i.e. `name asc`
**filter** *object* | Filter object
