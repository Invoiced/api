# Payment Plans

Payment plans allow you to collect an invoice balance over multiple installments. You can learn more about payment plans in our [Payment Plans Guide](https://invoiced.com/docs/guides/payment-plans).

## Payment Plan Object

Describes and tracks the status of a payment plan.

### Attributes

```shell
{
    "id": 6,
    "object": "payment_plan",
    "status": "active",
    "installments": [
        {
            "id": 23,
            "date": 1480572000,
            "amount": 500,
            "balance": 500
        },
        {
            "id": 24,
            "date": 1481176800,
            "amount": 500,
            "balance": 500
        },
        {
            "id": 25,
            "date": 1481781600,
            "amount": 500,
            "balance": 500,
        },
        {
            "id": 26,
            "date": 1482386400,
            "amount": 500,
            "balance": 500
        }
    ],
    "approval": {
        "id": 12,
        "ip": "217.15.151.36",
        "timestamp": 1479827803,
        "user_agent": "Mozilla\/5.0 (Macintosh; Intel Mac OS X 10.12; rv:50.0) Gecko\/20100101 Firefox
\/50.0"
    },
    "created_at": 1479827791
}
```

```ruby
#<Invoiced::PaymentPlan:0x3fdbf95e4d08 id=6> JSON: {
    "id": 6,
    "object": "payment_plan",
    "status": "active",
    "installments": [
        {
            "id": 23,
            "date": 1480572000,
            "amount": 500,
            "balance": 500
        },
        {
            "id": 24,
            "date": 1481176800,
            "amount": 500,
            "balance": 500
        },
        {
            "id": 25,
            "date": 1481781600,
            "amount": 500,
            "balance": 500,
        },
        {
            "id": 26,
            "date": 1482386400,
            "amount": 500,
            "balance": 500
        }
    ],
    "approval": {
        "id": 12,
        "ip": "217.15.151.36",
        "timestamp": 1479827803,
        "user_agent": "Mozilla\/5.0 (Macintosh; Intel Mac OS X 10.12; rv:50.0) Gecko\/20100101 Firefox
\/50.0"
    },
    "created_at": 1479827791
}
```

```php
Invoiced\PaymentPlan JSON: {
    "id": 6,
    "object": "payment_plan",
    "status": "active",
    "installments": [
        {
            "id": 23,
            "date": 1480572000,
            "amount": 500,
            "balance": 500
        },
        {
            "id": 24,
            "date": 1481176800,
            "amount": 500,
            "balance": 500
        },
        {
            "id": 25,
            "date": 1481781600,
            "amount": 500,
            "balance": 500,
        },
        {
            "id": 26,
            "date": 1482386400,
            "amount": 500,
            "balance": 500
        }
    ],
    "approval": {
        "id": 12,
        "ip": "217.15.151.36",
        "timestamp": 1479827803,
        "user_agent": "Mozilla\/5.0 (Macintosh; Intel Mac OS X 10.12; rv:50.0) Gecko\/20100101 Firefox
\/50.0"
    },
    "created_at": 1479827791
}
```

```python
<PaymentPlan id=6 at 0x3fdbf95e4d08> JSON: {
    "id": 6,
    "object": "payment_plan",
    "status": "active",
    "installments": [
        {
            "id": 23,
            "date": 1480572000,
            "amount": 500,
            "balance": 500
        },
        {
            "id": 24,
            "date": 1481176800,
            "amount": 500,
            "balance": 500
        },
        {
            "id": 25,
            "date": 1481781600,
            "amount": 500,
            "balance": 500,
        },
        {
            "id": 26,
            "date": 1482386400,
            "amount": 500,
            "balance": 500
        }
    ],
    "approval": {
        "id": 12,
        "ip": "217.15.151.36",
        "timestamp": 1479827803,
        "user_agent": "Mozilla\/5.0 (Macintosh; Intel Mac OS X 10.12; rv:50.0) Gecko\/20100101 Firefox
\/50.0"
    },
    "created_at": 1479827791
}
```

```java
com.invoiced.entity.PaymentPlan@754f2c43 JSON: {
    "id": 6,
    "object": "payment_plan",
    "status": "active",
    "installments": [
        {
            "id": 23,
            "date": 1480572000,
            "amount": 500,
            "balance": 500
        },
        {
            "id": 24,
            "date": 1481176800,
            "amount": 500,
            "balance": 500
        },
        {
            "id": 25,
            "date": 1481781600,
            "amount": 500,
            "balance": 500,
        },
        {
            "id": 26,
            "date": 1482386400,
            "amount": 500,
            "balance": 500
        }
    ],
    "approval": {
        "id": 12,
        "ip": "217.15.151.36",
        "timestamp": 1479827803,
        "user_agent": "Mozilla\/5.0 (Macintosh; Intel Mac OS X 10.12; rv:50.0) Gecko\/20100101 Firefox
\/50.0"
    },
    "created_at": 1479827791
}
```

Parameter | Type | Description
--------- | ---- | -----------
**id** | *integer* | The payment plan's unique ID
**object** | *string* | Object type, `payment_plan`
**status** | *string* | Payment plan state, one of `pending_signup`, `active`, `finished`, `canceled`
**installments** | *array* | Payment plan installments
**approval** | *object* | Payment plan approval, if approved
**created_at** | *timestamp* | Timestamp when created

## Create a payment plan

```shell
curl "https://api.invoiced.com/invoices/:invoice_id/payment_plan" \
  -u {API_KEY}: \
  -X PUT \
  -d installments[0][date]=1480572000 \
  -d installments[0][amount]=500 \
  -d installments[1][date]=1481176800 \
  -d installments[1][amount]=500 \
  -d installments[2][date]=1481781600 \
  -d installments[2][amount]=500 \
  -d installments[3][date]=1480572000 \
  -d installments[3][amount]=500
```

```ruby
invoice = invoiced.Invoice.retrieve("{INVOICE_ID}")
payment_plan = invoice.payment_plan.create(
  :installments => [
    {
      :date => 1480572000,
      :amount => 500
    },
    {
      :date => 1481176800,
      :amount => 500
    },
    {
      :date => 1481781600,
      :amount => 500
    },
    {
      :date => 1480572000,
      :amount => 500
    }
  ]
)
```

```php
<?php

$invoice = $invoiced->Invoice->retrieve("{INVOICE_ID}");
$paymentPlan = $invoice->paymentPlan()->create([
  'installments' => [
    [
      'date' => 1480572000,
      'amount' => 500
    ],
    [
      'date' => 1481176800,
      'amount' => 500
    ],
    [
      'date' => 1481781600,
      'amount' => 500
    ],
    [
      'date' => 1480572000,
      'amount' => 500
    ]
  ]
]);
```

```python
invoice = client.Invoice.retrieve("{INVOICE_ID}")
payment_plan = invoice.payment_plan().create(
  installments=[
    {
      'date': 1480572000,
      'amount': 500
    },
    {
      'date': 1481176800,
      'amount': 500
    },
    {
      'date': 1481781600,
      'amount': 500
    },
    {
      'date': 1480572000,
      'amount': 500
    }
  ]
)
```

```java
Invoice invoice = invoiced.newInvoice().retrieve({INVOICE_ID});
PaymentPlan paymentPlan = invoice.newPaymentPlan();
PaymentPlanInstallment[] installments = new PaymentPlanInstallment[4];
installments[0] = new PaymentPlanInstallment();
installments[0].date = 1480572000L;
installments[0].amount = 500D;
installments[1] = new PaymentPlanInstallment();
installments[1].date = 1481176800L;
installments[1].amount = 500D;
installments[2] = new PaymentPlanInstallment();
installments[2].date = 1481781600L;
installments[2].amount = 500D;
installments[3] = new PaymentPlanInstallment();
installments[3].date = 1480572000L;
installments[3].amount = 500D;
paymentPlan.installments = installments;
paymentPlan.create();
```

> The above command returns JSON structured like this:

```shell
{
    "id": 6,
    "object": "payment_plan",
    "status": "active",
    "installments": [
        {
            "id": 23,
            "date": 1480572000,
            "amount": 500,
            "balance": 500
        },
        {
            "id": 24,
            "date": 1481176800,
            "amount": 500,
            "balance": 500
        },
        {
            "id": 25,
            "date": 1481781600,
            "amount": 500,
            "balance": 500,
        },
        {
            "id": 26,
            "date": 1482386400,
            "amount": 500,
            "balance": 500
        }
    ],
    "approval": {
        "id": 12,
        "ip": "217.15.151.36",
        "timestamp": 1479827803,
        "user_agent": "Mozilla\/5.0 (Macintosh; Intel Mac OS X 10.12; rv:50.0) Gecko\/20100101 Firefox
\/50.0"
    },
    "created_at": 1479827791
}
```

```ruby
#<Invoiced::PaymentPlan:0x3fdbf95e4d08 id=6> JSON: {
    "id": 6,
    "object": "payment_plan",
    "status": "active",
    "installments": [
        {
            "id": 23,
            "date": 1480572000,
            "amount": 500,
            "balance": 500
        },
        {
            "id": 24,
            "date": 1481176800,
            "amount": 500,
            "balance": 500
        },
        {
            "id": 25,
            "date": 1481781600,
            "amount": 500,
            "balance": 500,
        },
        {
            "id": 26,
            "date": 1482386400,
            "amount": 500,
            "balance": 500
        }
    ],
    "approval": {
        "id": 12,
        "ip": "217.15.151.36",
        "timestamp": 1479827803,
        "user_agent": "Mozilla\/5.0 (Macintosh; Intel Mac OS X 10.12; rv:50.0) Gecko\/20100101 Firefox
\/50.0"
    },
    "created_at": 1479827791
}
```

```php
Invoiced\PaymentPlan JSON: {
    "id": 6,
    "object": "payment_plan",
    "status": "active",
    "installments": [
        {
            "id": 23,
            "date": 1480572000,
            "amount": 500,
            "balance": 500
        },
        {
            "id": 24,
            "date": 1481176800,
            "amount": 500,
            "balance": 500
        },
        {
            "id": 25,
            "date": 1481781600,
            "amount": 500,
            "balance": 500,
        },
        {
            "id": 26,
            "date": 1482386400,
            "amount": 500,
            "balance": 500
        }
    ],
    "approval": {
        "id": 12,
        "ip": "217.15.151.36",
        "timestamp": 1479827803,
        "user_agent": "Mozilla\/5.0 (Macintosh; Intel Mac OS X 10.12; rv:50.0) Gecko\/20100101 Firefox
\/50.0"
    },
    "created_at": 1479827791
}
```

```python
<PaymentPlan id=6 at 0x3fdbf95e4d08> JSON: {
    "id": 6,
    "object": "payment_plan",
    "status": "active",
    "installments": [
        {
            "id": 23,
            "date": 1480572000,
            "amount": 500,
            "balance": 500
        },
        {
            "id": 24,
            "date": 1481176800,
            "amount": 500,
            "balance": 500
        },
        {
            "id": 25,
            "date": 1481781600,
            "amount": 500,
            "balance": 500,
        },
        {
            "id": 26,
            "date": 1482386400,
            "amount": 500,
            "balance": 500
        }
    ],
    "approval": {
        "id": 12,
        "ip": "217.15.151.36",
        "timestamp": 1479827803,
        "user_agent": "Mozilla\/5.0 (Macintosh; Intel Mac OS X 10.12; rv:50.0) Gecko\/20100101 Firefox
\/50.0"
    },
    "created_at": 1479827791
}
```

```java
com.invoiced.entity.PaymentPlan@754f2c43 JSON: {
    "id": 6,
    "object": "payment_plan",
    "status": "active",
    "installments": [
        {
            "id": 23,
            "date": 1480572000,
            "amount": 500,
            "balance": 500
        },
        {
            "id": 24,
            "date": 1481176800,
            "amount": 500,
            "balance": 500
        },
        {
            "id": 25,
            "date": 1481781600,
            "amount": 500,
            "balance": 500,
        },
        {
            "id": 26,
            "date": 1482386400,
            "amount": 500,
            "balance": 500
        }
    ],
    "approval": {
        "id": 12,
        "ip": "217.15.151.36",
        "timestamp": 1479827803,
        "user_agent": "Mozilla\/5.0 (Macintosh; Intel Mac OS X 10.12; rv:50.0) Gecko\/20100101 Firefox
\/50.0"
    },
    "created_at": 1479827791
}
```

### HTTP Request

`PUT /invoices/:id/payment_plan`

### Attributes

Parameter | Type | Description
--------- | ---- | -----------
**installments** | *array* | Payment plan installments

## Retrieve a payment plan

```shell
curl "https://api.invoiced.com/invoices/:invoice_id/payment_plan" \
  -u {API_KEY}:
```

```ruby
invoice = invoiced.Invoice.retrieve("{INVOICE_ID}")
payment_plan = invoice.payment_plan.retrieve()
```

```php
<?php

$invoice = $invoiced->Invoice->retrieve("{INVOICE_ID}");
$paymentPlan = $invoice->paymentPlan()->get();
```

```python
invoice = client.Invoice.retrieve("{INVOICE_ID}")
payment_plan = invoice.payment_plan().retrieve()
```

```java
Invoice invoice = invoiced.newInvoice().retrieve({INVOICE_ID});
PaymentPlan paymentPlan = invoice.newPaymentPlan().retrieve();
```

> The above command returns JSON structured like this:

```shell
{
    "id": 6,
    "object": "payment_plan",
    "status": "active",
    "installments": [
        {
            "id": 23,
            "date": 1480572000,
            "amount": 500,
            "balance": 500
        },
        {
            "id": 24,
            "date": 1481176800,
            "amount": 500,
            "balance": 500
        },
        {
            "id": 25,
            "date": 1481781600,
            "amount": 500,
            "balance": 500,
        },
        {
            "id": 26,
            "date": 1482386400,
            "amount": 500,
            "balance": 500
        }
    ],
    "approval": {
        "id": 12,
        "ip": "217.15.151.36",
        "timestamp": 1479827803,
        "user_agent": "Mozilla\/5.0 (Macintosh; Intel Mac OS X 10.12; rv:50.0) Gecko\/20100101 Firefox
\/50.0"
    },
    "created_at": 1479827791
}
```

```ruby
#<Invoiced::PaymentPlan:0x3fdbf95e4d08 id=6> JSON: {
    "id": 6,
    "object": "payment_plan",
    "status": "active",
    "installments": [
        {
            "id": 23,
            "date": 1480572000,
            "amount": 500,
            "balance": 500
        },
        {
            "id": 24,
            "date": 1481176800,
            "amount": 500,
            "balance": 500
        },
        {
            "id": 25,
            "date": 1481781600,
            "amount": 500,
            "balance": 500,
        },
        {
            "id": 26,
            "date": 1482386400,
            "amount": 500,
            "balance": 500
        }
    ],
    "approval": {
        "id": 12,
        "ip": "217.15.151.36",
        "timestamp": 1479827803,
        "user_agent": "Mozilla\/5.0 (Macintosh; Intel Mac OS X 10.12; rv:50.0) Gecko\/20100101 Firefox
\/50.0"
    },
    "created_at": 1479827791
}
```

```php
Invoiced\PaymentPlan JSON: {
    "id": 6,
    "object": "payment_plan",
    "status": "active",
    "installments": [
        {
            "id": 23,
            "date": 1480572000,
            "amount": 500,
            "balance": 500
        },
        {
            "id": 24,
            "date": 1481176800,
            "amount": 500,
            "balance": 500
        },
        {
            "id": 25,
            "date": 1481781600,
            "amount": 500,
            "balance": 500,
        },
        {
            "id": 26,
            "date": 1482386400,
            "amount": 500,
            "balance": 500
        }
    ],
    "approval": {
        "id": 12,
        "ip": "217.15.151.36",
        "timestamp": 1479827803,
        "user_agent": "Mozilla\/5.0 (Macintosh; Intel Mac OS X 10.12; rv:50.0) Gecko\/20100101 Firefox
\/50.0"
    },
    "created_at": 1479827791
}
```

```python
<PaymentPlan id=6 at 0x3fdbf95e4d08> JSON: {
    "id": 6,
    "object": "payment_plan",
    "status": "active",
    "installments": [
        {
            "id": 23,
            "date": 1480572000,
            "amount": 500,
            "balance": 500
        },
        {
            "id": 24,
            "date": 1481176800,
            "amount": 500,
            "balance": 500
        },
        {
            "id": 25,
            "date": 1481781600,
            "amount": 500,
            "balance": 500,
        },
        {
            "id": 26,
            "date": 1482386400,
            "amount": 500,
            "balance": 500
        }
    ],
    "approval": {
        "id": 12,
        "ip": "217.15.151.36",
        "timestamp": 1479827803,
        "user_agent": "Mozilla\/5.0 (Macintosh; Intel Mac OS X 10.12; rv:50.0) Gecko\/20100101 Firefox
\/50.0"
    },
    "created_at": 1479827791
}
```

```java
com.invoiced.entity.PaymentPlan@754f2c43 JSON: {
    "id": 6,
    "object": "payment_plan",
    "status": "active",
    "installments": [
        {
            "id": 23,
            "date": 1480572000,
            "amount": 500,
            "balance": 500
        },
        {
            "id": 24,
            "date": 1481176800,
            "amount": 500,
            "balance": 500
        },
        {
            "id": 25,
            "date": 1481781600,
            "amount": 500,
            "balance": 500,
        },
        {
            "id": 26,
            "date": 1482386400,
            "amount": 500,
            "balance": 500
        }
    ],
    "approval": {
        "id": 12,
        "ip": "217.15.151.36",
        "timestamp": 1479827803,
        "user_agent": "Mozilla\/5.0 (Macintosh; Intel Mac OS X 10.12; rv:50.0) Gecko\/20100101 Firefox
\/50.0"
    },
    "created_at": 1479827791
}
```

This endpoint retrieves the payment plan for a given invoice.

### HTTP Request

`GET /invoices/:id/payment_plan`

## Cancel a payment plan

```shell
curl "https://api.invoiced.com/invoices/:invoice_id/payment_plan" \
  -u {API_KEY}: \
  -X DELETE
```

```ruby
payment_plan.cancel
```

```php
<?php

$paymentPlan->cancel();
```

```python
payment_plan.cancel()
```

```java
paymentPlan.cancel();
```

> The above command returns `204 No Content`

This endpoint cancels an active payment plan.

### HTTP Request

`DELETE /invoices/:id/payment_plan`