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
  "type": "company",
  "collection_mode": "auto",
  "payment_terms": null,
  "payment_source": {
    "id": 850,
    "brand": "Visa",
    "last4": 4242,
    "exp_month": 2,
    "exp_year": 20,
    "funding": "credit"
  },
  "attention_to": null,
  "address1": null,
  "address2": null,
  "city": null,
  "state": null,
  "postal_code": null,
  "country": "United States",
  "tax_id": null,
  "phone": null,
  "other_phone": null,
  "website": null,
  "notes": null,
  "statement_pdf_url": "https://dundermifflin.invoiced.com/statements/15444/pdf",
  "created_at": 1415222128
}
```

```ruby
#<Invoiced::Customer:0x3fdbf95e4d08 id=15444> JSON: {
  "id": 15444,
  "name": "Acme",
  "number": "CUST-0001",
  "email": "billing@acmecorp.com",
  "type": "company",
  "collection_mode": "auto",
  "payment_terms": null,
  "payment_source": {
    "id": 850,
    "brand": "Visa",
    "last4": 4242,
    "exp_month": 2,
    "exp_year": 20,
    "funding": "credit"
  },
  "attention_to": null,
  "address1": null,
  "address2": null,
  "city": null,
  "state": null,
  "postal_code": null,
  "country": "United States",
  "tax_id": null,
  "phone": null,
  "other_phone": null,
  "website": null,
  "notes": null,
  "statement_pdf_url": "https://dundermifflin.invoiced.com/statements/15444/pdf",
  "created_at": 1415222128
}
```

Parameter | Type | Description
--------- | ---- | -----------
**id** | *integer* | The customer's unique ID
**name** | *string* | Customer name
**number** | *string* | The reference number assigned to the customer for use in the dashboard
**type** | *string* | Organization type, `company` or `person`
**email** | *string* | Email address
**collection_mode** | *string* | Invoice collection mode, `auto` or `manual`
**payment_terms** | *string* | Payment terms used for `manual` collection mode, i.e. "NET 30"
**payment_source** | *object* | Summary of the customer's payment source, if attached
**attention_to** | *string* | Used for ATTN: address line if `company`
**address1** | *string* | First address line
**address2** | *string* | Optional second address line
**city** | *string* | City
**state** | *string* | State or province
**postal_code** | *string* | Zip or postal code
**country** | *string* | Country
**tax_id** | *string* | Tax ID to be displayed on documents
**phone** | *string* | Phone #
**other_phone** | *string* | Second phone #
**website** | *string* | Website
**notes** | *string* | Private customer notes
**statement_pdf_url** | *string* | URL to download the latest account statement
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
  "type": "company",
  "attention_to": null,
  "address1": null,
  "address2": null,
  "city": null,
  "state": null,
  "postal_code": null,
  "country": "United States",
  "tax_id": null,
  "phone": null,
  "other_phone": null,
  "website": null,
  "notes": null,
  "statement_pdf_url": "https://dundermifflin.invoiced.com/statements/15444/pdf",
  "created_at": 1415222128
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
  "type": "company",
  "attention_to": null,
  "address1": null,
  "address2": null,
  "city": null,
  "state": null,
  "postal_code": null,
  "country": "United States",
  "tax_id": null,
  "phone": null,
  "other_phone": null,
  "website": null,
  "notes": null,
  "statement_pdf_url": "https://dundermifflin.invoiced.com/statements/15444/pdf",
  "created_at": 1415222128
}
```

Create a new customer profile with this endpoint.

### Attributes

Parameter | Type | Description
--------- | ---- | -----------
**name** | *string* | Customer name - **required**
**number** | *string* | The reference number assigned to the customer for use in the dashboard. We will generate one if not supplied.
**type** | *string* | Organization type, `company` or `person`. Defaults to `company`
**email** | *string* | Email address
**collection_mode** | *string* | Invoice collection mode, `auto` or `manual`. Defaults to `manual`
**payment_terms** | *string* | Payment terms used for `manual` collection mode, i.e. "NET 30"
**stripe_token** | *string* | When provided sets the customer's payment source to the tokenized Stripe card
**attention_to** | *string* | Used for ATTN: address line if `company`
**address1** | *string* | First address line
**address2** | *string* | Optional second address line
**city** | *string* | City
**state** | *string* | State or province
**postal_code** | *string* | Zip or postal code
**country** | *string* | Country
**tax_id** | *string* | Tax ID to be displayed on documents
**phone** | *string* | Phone #
**other_phone** | *string* | Second phone #
**website** | *string* | Website
**notes** | *string* | Private customer notes

## Retrieve a customer

```shell
curl "https://api.invoiced.com/customers/:id" \
  -u {API_KEY}:
```

```ruby
customer = invoiced.Customer.retrieve("{CUSTOMER_ID}")
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
  "type": "company",
  "attention_to": "Sarah Fisher",
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
  "statement_pdf_url": "https://dundermifflin.invoiced.com/statements/15444/pdf",
  "created_at": 1415222128
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
  "type": "company",
  "attention_to": null,
  "address1": null,
  "address2": null,
  "city": null,
  "state": null,
  "postal_code": null,
  "country": "United States",
  "tax_id": null,
  "phone": null,
  "other_phone": null,
  "website": null,
  "notes": null,
  "statement_pdf_url": "https://dundermifflin.invoiced.com/statements/15444/pdf",
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
  -d website="acmecorp.com" \
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
customer.website = "acmecorp.com"
customer.save
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
  "type": "company",
  "attention_to": "Sarah Fisher",
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
  "statement_pdf_url": "https://dundermifflin.invoiced.com/statements/15444/pdf",
  "created_at": 1415222128
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
  "type": "company",
  "attention_to": "Sarah Fisher",
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
  "statement_pdf_url": "https://dundermifflin.invoiced.com/statements/15444/pdf",
  "created_at": 1415222128
}
```

Use this endpoint to update a customer profile.

### HTTP Request

`PATCH /customers/:id`

### Request Parameters

Parameter | Type | Description
--------- | ---- | -----------
**name** | *string* | Customer name
**number** | *string* | The reference number assigned to the customer for use in the dashboard
**type** | *string* | Organization type, `company` or `person`
**email** | *string* | Email address
**collection_mode** | *string* | Invoice collection mode, `auto` or `manual`
**payment_terms** | *string* | Payment terms used for `manual` collection mode, i.e. "NET 30"
**stripe_token** | *string* | When provided sets the customer's payment source to the tokenized Stripe card
**attention_to** | *string* | Used for ATTN: address line if `company`
**address1** | *string* | First address line
**address2** | *string* | Optional second address line
**city** | *string* | City
**state** | *string* | State or province
**postal_code** | *string* | Zip or postal code
**country** | *string* | Country
**tax_id** | *string* | Tax ID to be displayed on documents
**phone** | *string* | Phone #
**other_phone** | *string* | Second phone #
**website** | *string* | Website
**notes** | *string* | Private customer notes

## List customer subscriptions

```shell
curl "https://api.invoiced.com/customers/:id/subscriptions" \
  -u {API_KEY}:
```

```ruby
subscriptions, metadata = customer.subscriptions
```

> The above command returns JSON structured like this:

```shell
[
  {
      "id": 412,
      "customer": 15444,
      "plan": 418,
      "start_date": 1415230038,
      "quantity": 1,
      "cycles": null,
      "renews_next": 1438813638,
      "renewed_last": 1436135238,
      "status": "past_due",
      "url": "https:\/\/dundermifflin.invoiced.com\/subscriptions\/ClfLz70YiFSgu5E2dA5qrwXX",
      "created_at": 1415230041
  },
  {
      "id": 595,
      "customer": 15444,
      "plan": 420,
      "start_date": 1425572792,
      "quantity": 1,
      "cycles": null,
      "renews_next": 1438788392,
      "renewed_last": 1436109992,
      "status": "active",
      "url": "https:\/\/dundermifflin.invoiced.com\/subscriptions\/ir5n8vGRTcsJyBNS8lzR6gXX",
      "created_at": 1425572798
  }
]
```

```ruby
[
  #<Invoiced::Subscription:0x3fdbf9sf9e4d08 id=412> JSON: {
      "id": 412,
      "customer": 15444,
      "plan": 418,
      "start_date": 1415230038,
      "quantity": 1,
      "cycles": null,
      "renews_next": 1438813638,
      "renewed_last": 1436135238,
      "status": "past_due",
      "url": "https:\/\/dundermifflin.invoiced.com\/subscriptions\/ClfLz70YiFSgu5E2dA5qrwXX",
      "created_at": 1415230041
  },
  #<Invoiced::Subscription:0x3fdbf95as4d08 id=595> JSON: {
      "id": 595,
      "customer": 15444,
      "plan": 420,
      "start_date": 1425572792,
      "quantity": 1,
      "cycles": null,
      "renews_next": 1438788392,
      "renewed_last": 1436109992,
      "status": "active",
      "url": "https:\/\/dundermifflin.invoiced.com\/subscriptions\/ir5n8vGRTcsJyBNS8lzR6gXX",
      "created_at": 1425572798
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
emails, metadata = customer.send_statement
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
  #<Invoiced::Email:0x3fdbf95e4d08 id="f45382c6fbc44d44aa7f9a55eb2ce731"> JSON: {
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
  #<Invoiced::Email:0x3fdasdf95e09 id="a0s36fbc44d44aa7f9a55easdfi8ce731"> JSON: { ... },
  #<Invoiced::Email:0x3fdbffge4d10 id="s90f2c6fbc44sdfj8aa7f9a55eb2ce731"> JSON: { ... }
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
    "type": "company",
    "attention_to": "Sarah Fisher",
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
    "statement_pdf_url": "https://dundermifflin.invoiced.com/statements/15444/pdf",
    "created_at": 1415222128
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
    "type": "company",
    "attention_to": "Sarah Fisher",
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
    "statement_pdf_url": "https://dundermifflin.invoiced.com/statements/15444/pdf",
    "created_at": 1415222128
  },
  #<Invoiced::Customer:0x3fdbf95e4d09 id=15445> JSON: { ... },
  #<Invoiced::Customer:0x3fdbf95e4d10 id=15446> JSON: { ... }
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