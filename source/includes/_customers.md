# Customers

Customers represent the entity you are billing, whether this is an organization or a individual. Each customer has a collection mode, automatic or manual. In automatic collection mode any invoices will be charged to your customer's payment source. Currently we support debit / credit cards and bank accounts (via ACH) as payment sources.

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
    "last4": "4242",
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
  "statement_pdf_url": "https://dundermifflin.invoiced.com/statements/t3NmhUomra3g3ueSNnbtUgrr/pdf",
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
    "last4": "4242",
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
  "statement_pdf_url": "https://dundermifflin.invoiced.com/statements/t3NmhUomra3g3ueSNnbtUgrr/pdf",
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
    "last4": "4242",
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
  "statement_pdf_url": "https://dundermifflin.invoiced.com/statements/t3NmhUomra3g3ueSNnbtUgrr/pdf",
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
    "last4": "4242",
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
  "statement_pdf_url": "https://dundermifflin.invoiced.com/statements/t3NmhUomra3g3ueSNnbtUgrr/pdf",
  "created_at": 1415222128,
  "metadata": {}
}
```

```java
com.invoiced.entity.Customer@d72919f JSON: {  
  "id": 15444,
  "name": "Acme",
  "number": "CUST-0001",
  "email": "billing@acmecorp.com",
  "collection_mode": "auto",
  "payment_source": {
    "id": 850,
    "object": "card",
    "brand": "Visa",
    "last4": "4242",
    "exp_month": 2,
    "exp_year": 20,
    "funding": "credit"
  },
  "type": "company",
  "country": "US",
  "statement_pdf_url": "https://dundermifflin.invoiced.com/statements/t3NmhUomra3g3ueSNnbtUgrr/pdf",
  "created_at": 1415222128
  }
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
  "last4": "4242",
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
  "last4": "4242",
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
  "last4": "4242",
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
  "last4": "4242",
  "exp_month": 2,
  "exp_year": 20,
  "funding": "credit"
}
```

```java
//PaymentSource can be used for both Card Object and Bank Account Object
com.invoiced.entity.PaymentSource@2fdf31f4 JSON: {
  "id": 850,
  "object": "card",
  "brand": "Visa",
  "last4": "4242",
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
**last4** | *string* | Last 4 digits of card
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
  "last4": "7890",
  "routing_number": "110000000",
  "verified": true,
  "currency": "usd"
}
```

```ruby
#<Invoiced::BankAccount:0x3fdbf95e4d08 id=4321> JSON: {
  "id": 4321,
  "object": "card",
  "bank_name": "Wells Fargo",
  "last4": "7890",
  "routing_number": "110000000",
  "verified": true,
  "currency": "usd"
}
```

```php
Invoiced\BankAccount JSON: {
  "id": 4321,
  "object": "card",
  "bank_name": "Wells Fargo",
  "last4": "7890",
  "routing_number": "110000000",
  "verified": true,
  "currency": "usd"
}
```

```python
<BankAccount id=4321 at 0x3fdbf95e4d08> JSON: {
  "id": 4321,
  "object": "card",
  "bank_name": "Wells Fargo",
  "last4": "7890",
  "routing_number": "110000000",
  "verified": true,
  "currency": "usd"
}
```

```java
//PaymentSource can be used for both Card Object and Bank Account Object
com.invoiced.entity.PaymentSource@3fdf31f4 JSON: {
  "id": 4321,
  "object": "card",
  "bank_name": "Wells Fargo",
  "last4": "7890",
  "routing_number": "110000000",
  "verified": true,
  "currency": "usd"
}
```

Parameter | Type | Description
--------- | ---- | -----------
**id** | *integer* | The bank account's unique ID
**object** | *string* | `bank_account`
**bank_name** | *string* | Bank name
**last4** | *string* | Last 4 digits of bank account
**routing_number** | *string* | Bank routing number
**verified** | *boolean* | Whether the bank account has been verified with instant verification or micro-deposits
**currency** | *string* | [3-letter ISO code](https://en.wikipedia.org/wiki/ISO_4217)

## Contact Object

Contacts can be attached to customers. A contact could represent an additional email recipient for a customer, or perhaps an address in addition to the billing address, like a shipping address.

### Attributes

```shell
{
  "id": 10403,
  "name": "Nancy Talty",
  "email": "nancy.talty@example.com",
  "primary": true,
  "address1": null,
  "address2": null,
  "city": null,
  "state": null,
  "postal_code": null,
  "country": null,
  "created_at": 1463510889
}
```

```ruby
#<Invoiced::Contact:0x3fdbf95e4d08 id=10403> JSON: {
  "id": 10403,
  "name": "Nancy Talty",
  "email": "nancy.talty@example.com",
  "primary": true,
  "address1": null,
  "address2": null,
  "city": null,
  "state": null,
  "postal_code": null,
  "country": null,
  "created_at": 1463510889
}
```

```php
Invoiced\Contact JSON: {
  "id": 10403,
  "name": "Nancy Talty",
  "email": "nancy.talty@example.com",
  "primary": true,
  "address1": null,
  "address2": null,
  "city": null,
  "state": null,
  "postal_code": null,
  "country": null,
  "created_at": 1463510889
}
```

```python
<Contact id=10403 at 0x3fdbf95e4d08> JSON: {
  "id": 10403,
  "name": "Nancy Talty",
  "email": "nancy.talty@example.com",
  "primary": true,
  "address1": null,
  "address2": null,
  "city": null,
  "state": null,
  "postal_code": null,
  "country": null,
  "created_at": 1463510889
}
```

```java
com.invoiced.entity.Contact@3a0fa320 JSON: {
  "id": 10403,
  "name": "Nancy Talty",
  "email": "nancy.talty@example.com",
  "primary": true,
  "created_at": 1463510889
}
```

Parameter | Type | Description
--------- | ---- | -----------
**id** | *integer* | The contact's unique ID
**name** | *string* | Contact name
**email** | *string* | Email address
**primary** | *boolean* | When true the contact will be copied on any account communications
**address1** | *string* | First address line
**address2** | *string* | Optional second address line
**city** | *string* | City
**state** | *string* | State or province
**postal_code** | *string* | Zip or postal code
**country** | *string* | [Two-letter ISO code](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2)
**created_at** | *timestamp* | Timestamp when created

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

```java
Customer customer = invoiced.newCustomer();
customer.name = "Acme";
customer.email = "billing@acmecorp.com";
customer.collectionMode = "manual";
customer.paymentTerms = "NET 30";
customer.type = "company";
customer.create();
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
  "statement_pdf_url": "https://dundermifflin.invoiced.com/statements/t3NmhUomra3g3ueSNnbtUgrr/pdf",
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
  "statement_pdf_url": "https://dundermifflin.invoiced.com/statements/t3NmhUomra3g3ueSNnbtUgrr/pdf",
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
  "statement_pdf_url": "https://dundermifflin.invoiced.com/statements/t3NmhUomra3g3ueSNnbtUgrr/pdf",
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
  "statement_pdf_url": "https://dundermifflin.invoiced.com/statements/t3NmhUomra3g3ueSNnbtUgrr/pdf",
  "created_at": 1415222128,
  "metadata": {}
}
```

```java
com.invoiced.entity.Customer@cb8fd57 JSON :{
  "id": 15444,
  "number": "CUST-0001",
  "name": "Acme",
  "email": "billing@acmecorp.com",
  "collection_mode": "manual",
  "payment_terms": "NET 30",
  "type": "company",
  "country": "US",
  "statement_pdf_url": "https://dundermifflin.invoiced.com/statements/t3NmhUomra3g3ueSNnbtUgrr/pdf",
  "created_at": 1415222128
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

```java
Customer customer = invoiced.newCustomer();
Customer customerToRetrieve = customer.retrieve({CUSTOMER_ID});
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
  "statement_pdf_url": "https://dundermifflin.invoiced.com/statements/t3NmhUomra3g3ueSNnbtUgrr/pdf",
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
  "statement_pdf_url": "https://dundermifflin.invoiced.com/statements/t3NmhUomra3g3ueSNnbtUgrr/pdf",
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
  "statement_pdf_url": "https://dundermifflin.invoiced.com/statements/t3NmhUomra3g3ueSNnbtUgrr/pdf",
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
  "statement_pdf_url": "https://dundermifflin.invoiced.com/statements/t3NmhUomra3g3ueSNnbtUgrr/pdf",
  "created_at": 1415222128,
  "metadata": {}
}
```

```java
com.invoiced.entity.Customer@cb8fd58 JSON: {
  "id": 15444,
  "number": "CUST-0001",
  "name": "Acme",
  "email": "billing@acmecorp.com",
  "collection_mode": "manual",
  "payment_terms": "NET 30",
  "type": "company",
  "country": "US",
  "statement_pdf_url": "https://dundermifflin.invoiced.com/statements/t3NmhUomra3g3ueSNnbtUgrr/pdf",
  "created_at": 1415222128  
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

```java
customer.paymentTerms = "NET 14";
customer.attentionTo = "Sarah Fisher";
customer.address1 = "342 Amber St";
customer.city = "Hill Valley";
customer.state = "CA";
customer.postalCode = "94523";
customer.taxId = "893-934835";
customer.phone = "(820) 297-2983";
customer.save();
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
  "statement_pdf_url": "https://dundermifflin.invoiced.com/statements/t3NmhUomra3g3ueSNnbtUgrr/pdf",
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
  "statement_pdf_url": "https://dundermifflin.invoiced.com/statements/t3NmhUomra3g3ueSNnbtUgrr/pdf",
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
  "statement_pdf_url": "https://dundermifflin.invoiced.com/statements/t3NmhUomra3g3ueSNnbtUgrr/pdf",
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
  "statement_pdf_url": "https://dundermifflin.invoiced.com/statements/t3NmhUomra3g3ueSNnbtUgrr/pdf",
  "created_at": 1415222128,
  "metadata": {}
}
```

```java
com.invoiced.entity.Customer@cb8fd59 JSON: {
  "id": 15444,
  "number": "CUST-0001",
  "name": "Acme",
  "email": "billing@acmecorp.com",
  "collection_mode": "manual",
  "payment_terms": "NET 14",
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
  "statement_pdf_url": "https://dundermifflin.invoiced.com/statements/t3NmhUomra3g3ueSNnbtUgrr/pdf",
  "created_at": 1415222128,
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

```java
Balance balance = customer.getBalance();
```

> The above command returns JSON structured like this:

```shell
{
  "available_credits": 50,
  "history": [
    {
      "timestamp": 1464041624,
      "balance": 50
    },
    {
      "timestamp": 1464040550,
      "balance": 100
    }
  ],
  "past_due": false,
  "total_outstanding": 470
}
```

```ruby
{
  "available_credits": 50,
  "history": [
    {
      "timestamp": 1464041624,
      "balance": 50
    },
    {
      "timestamp": 1464040550,
      "balance": 100
    }
  ],
  "past_due": false,
  "total_outstanding": 470
}
```

```php
{
  "available_credits": 50,
  "history": [
    {
      "timestamp": 1464041624,
      "balance": 50
    },
    {
      "timestamp": 1464040550,
      "balance": 100
    }
  ],
  "past_due": false,
  "total_outstanding": 470
}
```

```python
{
  "available_credits": 50,
  "history": [
    {
      "timestamp": 1464041624,
      "balance": 50
    },
    {
      "timestamp": 1464040550,
      "balance": 100
    }
  ],
  "past_due": false,
  "total_outstanding": 470
}
```

```java
com.invoiced.entity.Balance@cb8fd60 JSON: {
 "available_credits": 50,
  "history": [
    {
      "timestamp": 1464041624,
      "balance": 50
    },
    {
      "timestamp": 1464040550,
      "balance": 100
    }
  ],
  "past_due": false,
  "total_outstanding": 470
}
```

This endpoint returns the customer's current credit balance, credit balance history, and the current amount outstanding.

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

```java
EmailRequest emailRequest = new EmailRequest();
EmailRecipient[] emailRecipients = new EmailRecipient[1];
emailRecipients[0] = new EmailRecipient();
emailRecipients[0].name = "Client";
emailRecipients[0].email = "client@example.com";
emailRequest.to = emailRecipients;
emailRequest.subject = "Statement from Dunder Mifflin, Inc.";
emailRequest.message = "Dear Client, we have attached your latest account statement. Thank you!";
Email[] emails = customer.sendStatement(emailRequest);
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
```java
//To pretty print a array of Objects use Arrays.toString(Object[]);
[
  com.invoiced.entity.Email@1bfbb8ee JSON: {
    "id": "f45382c6fbc44d44aa7f9a55eb2ce731",
    "state": "sent",
    "email": "client@example.com",
    "template": "statement_email",
    "subject": "Statement from Dunder Mifflin, Inc.",
    "message": "Dear Client, we have attached your latest account statement. Thank you!",
    "opens": 0,
    "clicks": 0,
    "created_at": 1436890047
  }, 
  com.invoiced.entity.Email@2afbb8ee JSON: {...},
  com.invoiced.entity.Email@3bfbb8ee JSON: {...}
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

## Create a contact

```shell
curl "https://api.invoiced.com/customers/:customer_id/contacts" \
  -u {API_KEY}: \
  -d name="Nancy Talty" \
  -d email="nancy.talty@example.com"
```

```ruby
customer = invoiced.Customer.retrieve("{CUSTOMER_ID}")
customer.contacts.create(
  :name => "Nancy Talty",
  :email => "nancy.talty@example.com"
)
```

```php
<?php

$customer = $invoiced->Customer->retrieve("{CUSTOMER_ID}");
$customer->contacts()->create([
  'name' => "Nancy Talty",
  'email' => "nancy.talty@example.com"
]);
```

```python
customer = client.Customer.retrieve("{CUSTOMER_ID}")
customer.contacts().create(
  name="Nancy Talty",
  email="nancy.talty@example.com"
)
```

```java
Customer customer = invoiced.newCustomer().retrieve({CUSTOMER_ID});
Contact contact = customer.newContact();
contact.name = "Nancy Talty";
contact.email = "nancy.talty@example.com";
contact.create();
```

> The above command returns JSON structured like this:

```shell
{
  "id": 10403,
  "name": "Nancy Talty",
  "email": "nancy.talty@example.com",
  "primary": true,
  "address1": null,
  "address2": null,
  "city": null,
  "state": null,
  "postal_code": null,
  "country": null,
  "created_at": 1463510889
}
```

```ruby
#<Invoiced::Contact:0x3fdbf95e4d08 id=10403> JSON: {
  "id": 10403,
  "name": "Nancy Talty",
  "email": "nancy.talty@example.com",
  "primary": true,
  "address1": null,
  "address2": null,
  "city": null,
  "state": null,
  "postal_code": null,
  "country": null,
  "created_at": 1463510889
}
```

```php
Invoiced\Contact JSON: {
  "id": 10403,
  "name": "Nancy Talty",
  "email": "nancy.talty@example.com",
  "primary": true,
  "address1": null,
  "address2": null,
  "city": null,
  "state": null,
  "postal_code": null,
  "country": null,
  "created_at": 1463510889
}
```

```python
<Contact id=10403 at 0x3fdbf95e4d08> JSON: {
  "id": 10403,
  "name": "Nancy Talty",
  "email": "nancy.talty@example.com",
  "primary": true,
  "address1": null,
  "address2": null,
  "city": null,
  "state": null,
  "postal_code": null,
  "country": null,
  "created_at": 1463510889
}
```

```java
com.invoiced.entity.Contact@cb8fd89 JSON: {
  "id": 10403,
  "name": "Nancy Talty",
  "email": "nancy.talty@example.com",
  "primary": true,
  "created_at": 1463510889
}
```

Create a new contact with this endpoint.

### HTTP Request

`POST /customers/:customer_id/contacts`

### Attributes

Parameter | Type | Description
--------- | ---- | -----------
**name** | *string* | Contact name
**email** | *string* | Email address
**primary** | *boolean* | When true the contact will be copied on any account communications
**address1** | *string* | First address line
**address2** | *string* | Optional second address line
**city** | *string* | City
**state** | *string* | State or province
**postal_code** | *string* | Zip or postal code
**country** | *string* | [Two-letter ISO code](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2)

## Retrieve a contact

```shell
curl "https://api.invoiced.com/customers/:customer_id/contacts/:id" \
  -u {API_KEY}:
```

```ruby
customer = invoiced.Customer.retrieve("{CUSTOMER_ID}")
contact = customer.contacts.retrieve("{CONTACT_ID}")
```

```php
<?php

$customer = $invoiced->Customer->retrieve("{CUSTOMER_ID}");
$contact = $customer->contacts()->retrieve("{CONTACT_ID}");
```

```python
customer = client.Customer.retrieve("{CUSTOMER_ID}")
contact = customer.contacts().retrieve("{CONTACT_ID}")
```

```java
Customer customer = invoiced.newCustomer().retrieve({CUSTOMER_ID});
Contact contact = customer.newContact().retrieve({CONTACT_ID});
```

> The above command returns JSON structured like this:

```shell
{
  "id": 10403,
  "name": "Nancy Talty",
  "email": "nancy.talty@example.com",
  "primary": true,
  "address1": null,
  "address2": null,
  "city": null,
  "state": null,
  "postal_code": null,
  "country": null,
  "created_at": 1463510889
}
```

```ruby
#<Invoiced::Contact:0x3fdbf95e4d08 id=10403> JSON: {
  "id": 10403,
  "name": "Nancy Talty",
  "email": "nancy.talty@example.com",
  "primary": true,
  "address1": null,
  "address2": null,
  "city": null,
  "state": null,
  "postal_code": null,
  "country": null,
  "created_at": 1463510889
}
```

```php
Invoiced\Contact JSON: {
  "id": 10403,
  "name": "Nancy Talty",
  "email": "nancy.talty@example.com",
  "primary": true,
  "address1": null,
  "address2": null,
  "city": null,
  "state": null,
  "postal_code": null,
  "country": null,
  "created_at": 1463510889
}
```

```python
<Contact id=10403 at 0x3fdbf95e4d08> JSON: {
  "id": 10403,
  "name": "Nancy Talty",
  "email": "nancy.talty@example.com",
  "primary": true,
  "address1": null,
  "address2": null,
  "city": null,
  "state": null,
  "postal_code": null,
  "country": null,
  "created_at": 1463510889
}
```

```java
com.invoiced.entity.Contact@cb8fd89 JSON: {
  "id": 10403,
  "name": "Nancy Talty",
  "email": "nancy.talty@example.com",
  "primary": true,
  "created_at": 1463510889
}
```


This endpoint retrieves a specific contact.

### HTTP Request

`GET /customers/:customer_id/contacts/:id`

## Update a contact

```shell
curl "https://api.invoiced.com/customers/:customer_id/contacts/:id" \
  -u {API_KEY}: \
  -d address1="507 Grove Avenue" \
  -d city="Oklahoma City" \
  -d state="OK" \
  -d postal_code="73102" \
  -X PATCH
```

```ruby
contact.address1 = "507 Grove Avenue"
contact.city = "Oklahoma City"
contact.state = "OK"
contact.postal_code = "73102"
contact.save
```

```php
<?php

contact->address1 = "507 Grove Avenue"
contact->city = "Oklahoma City"
contact->state = "OK"
contact->postal_code = "73102"
$contact->save();
```

```python
contact.address1 = "507 Grove Avenue"
contact.city = "Oklahoma City"
contact.state = "OK"
contact.postal_code = "73102"
contact.save()
```

```java 
contact.address1 = "507 Grove Avenue"
contact.city = "Oklahoma City"
contact.state = "OK"
contact.postalCode = "73102"
contact.save()
```

> The above command returns JSON structured like this:

```shell
{
  "id": 10403,
  "name": "Nancy Talty",
  "email": "nancy.talty@example.com",
  "primary": true,
  "address1": "507 Grove Avenue",
  "address2": null,
  "city": "Oklahoma City",
  "state": "OK",
  "postal_code": "73102",
  "country": null,
  "created_at": 1463510889
}
```

```ruby
#<Invoiced::Contact:0x3fdbf95e4d08 id=10403> JSON: {
  "id": 10403,
  "name": "Nancy Talty",
  "email": "nancy.talty@example.com",
  "primary": true,
  "address1": "507 Grove Avenue",
  "address2": null,
  "city": "Oklahoma City",
  "state": "OK",
  "postal_code": "73102",
  "country": null,
  "created_at": 1463510889
}
```

```php
Invoiced\Contact JSON: {
  "id": 10403,
  "name": "Nancy Talty",
  "email": "nancy.talty@example.com",
  "primary": true,
  "address1": "507 Grove Avenue",
  "address2": null,
  "city": "Oklahoma City",
  "state": "OK",
  "postal_code": "73102",
  "country": null,
  "created_at": 1463510889
}
```

```python
<Contact id=10403 at 0x3fdbf95e4d08> JSON: {
  "id": 10403,
  "name": "Nancy Talty",
  "email": "nancy.talty@example.com",
  "primary": true,
  "address1": "507 Grove Avenue",
  "address2": null,
  "city": "Oklahoma City",
  "state": "OK",
  "postal_code": "73102",
  "country": null,
  "created_at": 1463510889
}
```

```java
com.invoiced.entity.Contact@cb8fd89 JSON: {
  "id": 10403,
  "name": "Nancy Talty",
  "email": "nancy.talty@example.com",
  "primary": true,
  "address1": "507 Grove Avenue",
  "city": "Oklahoma City",
  "state": "OK",
  "postal_code": "73102",
  "created_at": 1463510889
}
```

Use this endpoint to update a contact.

### HTTP Request

`PATCH /customers/:customer_id/contacts/:id`

### Request Parameters

Parameter | Type | Description
--------- | ---- | -----------
**name** | *string* | Contact name
**email** | *string* | Email address
**primary** | *boolean* | When true the contact will be copied on any account communications
**address1** | *string* | First address line
**address2** | *string* | Optional second address line
**city** | *string* | City
**state** | *string* | State or province
**postal_code** | *string* | Zip or postal code
**country** | *string* | [Two-letter ISO code](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2)

## Delete a contact

```shell
curl "https://api.invoiced.com/customers/:customer_id/contacts/:id" \
  -u {API_KEY}: \
  -X DELETE
```

```ruby
contact.delete
```

```php
<?php

$contact->delete();
```

```python
contact.delete()
```

```java
contact.delete();
```

> The above command returns `204 No Content`

This endpoint deletes a specific contact.

### HTTP Request

`DELETE /customers/:customer_id/contacts/:id`

## List all contacts

```shell
curl "https://api.invoiced.com/customers/:customer_id/contacts" \
  -u {API_KEY}:
```

```ruby
customer = invoiced.Customer.retrieve("{CUSTOMER_ID}")
contacts, metadata = customer.contacts.list(:per_page => 3)
```

```php
<?php

$customer = $invoiced->Customer->retrieve("{CUSTOMER_ID}");
list($contacts, $metadata) = $customer->contacts()->all(['per_page' => 3]);
```

```python
customer = client.Customer.retrieve("{CUSTOMER_ID}")
contacts, metadata = customer.contacts().list(per_page=3)
```

```java
Customer customer = conn.newCustomer().retrieve({CUSTOMER_ID});
EntityList<Contact> contacts = customer.newContact().listAll();
```

> The above command returns JSON structured like this:

```shell
[
  {
    "id": 10403,
    "name": "Nancy Talty",
    "email": "nancy.talty@example.com",
    "primary": true,
    "address1": null,
    "address2": null,
    "city": null,
    "state": null,
    "postal_code": null,
    "country": null,
    "created_at": 1463510889
  },
  { ... },
  { ... }
]
```

```ruby
[
  #<Invoiced::Contact:0x3fdbf95e4d08 id=10403> JSON: {
    "id": 10403,
    "name": "Nancy Talty",
    "email": "nancy.talty@example.com",
    "primary": true,
    "address1": null,
    "address2": null,
    "city": null,
    "state": null,
    "postal_code": null,
    "country": null,
    "created_at": 1463510889
  },
  #<Invoiced::Contact:0x3fdbf95e4d09 id=10404> JSON: { ... },
  #<Invoiced::Contact:0x3fdbf95e4d10 id=10405> JSON: { ... }
]
```

```php
[
  Invoiced\Contact JSON: {
    "id": 10403,
    "name": "Nancy Talty",
    "email": "nancy.talty@example.com",
    "primary": true,
    "address1": null,
    "address2": null,
    "city": null,
    "state": null,
    "postal_code": null,
    "country": null,
    "created_at": 1463510889
  },
  Invoiced\Contact JSON: { ... },
  Invoiced\Contact JSON: { ... }
]
```

```python
[
  <Contact id=10403 at 0x3fdbf95e4d08> JSON: {
    "id": 10403,
    "name": "Nancy Talty",
    "email": "nancy.talty@example.com",
    "primary": true,
    "address1": null,
    "address2": null,
    "city": null,
    "state": null,
    "postal_code": null,
    "country": null,
    "created_at": 1463510889
  },
  <Contact id=10404 at 0x3fdbf95e4d08> JSON: { ... },
  <Contact id=10405 at 0x3fdbf95e4d08> JSON: { ... }
]
```

```java
[
  com.invoiced.entity.Contact@1701e31a JSON: { 
    "id": 10403,
    "name": "Nancy Talty",
    "email": "nancy.talty@example.com",
    "primary": true,
    "address1": null,
    "address2": null,
    "city": null,
    "state": null,
    "postal_code": null,
    "country": null,
    "created_at": 1463510889
  },
  com.invoiced.entity.Contact@2701e31a JSON: {...},
  com.invoiced.entity.Contact@3701e31a JSON: {...}
]
```

This endpoint retrieves all contacts.

### HTTP Request

`GET /customers/:customer_id/contacts`

### Query Parameters

Parameter | Description
--------- | -----------
**sort** *string* | Column to sort by, i.e. `name asc`
**filter** *object* | Filter object

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

```java
customer.delete();
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

```java
EntityList<Customer> customers = connection.newCustomer().listAll();
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
    "statement_pdf_url": "https://dundermifflin.invoiced.com/statements/t3NmhUomra3g3ueSNnbtUgrr/pdf",
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
    "statement_pdf_url": "https://dundermifflin.invoiced.com/statements/t3NmhUomra3g3ueSNnbtUgrr/pdf",
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
    "statement_pdf_url": "https://dundermifflin.invoiced.com/statements/t3NmhUomra3g3ueSNnbtUgrr/pdf",
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
    "statement_pdf_url": "https://dundermifflin.invoiced.com/statements/t3NmhUomra3g3ueSNnbtUgrr/pdf",
    "created_at": 1415222128,
    "metadata": {}
  },
  <Customer id=15445 at 0x3fdbf95e4d08> JSON: { ... },
  <Customer id=15446 at 0x3fdbf95e4d08> JSON: { ... }
]
```

```java
[
  com.invoiced.entity.Customer@1701d31a JSON: {
    "id": 15444,
    "number": "CUST-0001",
    "name": "Acme",
    "email": "billing@acmecorp.com",
    "collection_mode": "manual",
    "payment_terms": "NET 30",
    "type": "company",
    "attention_to": "Sarah Fisher",
    "address1": "342 Amber St",
    "city": "Hill Valley",
    "state": "CA",
    "postal_code": "94523",
    "country": "US",
    "tax_id": "893-934835",
    "phone": "(820) 297-2983",
    "statement_pdf_url": "https://dundermifflin.invoiced.com/statements/t3NmhUomra3g3ueSNnbtUgrr/pdf",
    "created_at": 1415222128
  },
  com.invoiced.entity.Customer@2701d31a JSON: { ... },
  com.invoiced.entity.Customer@3701d31a JSON: { ... }
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
**metadata** *object* | Metadata filter object
**payment_source** *boolean* | When set only returns customers with (or without) a payment source
**balance** *boolean* | When set only returns customers with (or without) a credit balance