# Payment Sources

A payment source represents a specific payment instrument owned by a customer that can be used for payments. We currently support credit cards and bank accounts as payment sources.

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
**object** | *string* | Object type, `card`
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
  "object": "bank_account",
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
  "object": "bank_account",
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
  "object": "bank_account",
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
  "object": "bank_account",
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
  "object": "bank_account",
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
**object** | *string* | Object type, `bank_account`
**bank_name** | *string* | Bank name
**last4** | *string* | Last 4 digits of bank account
**routing_number** | *string* | Bank routing number
**verified** | *boolean* | Whether the bank account has been verified with instant verification or micro-deposits
**currency** | *string* | [3-letter ISO code](https://en.wikipedia.org/wiki/ISO_4217)