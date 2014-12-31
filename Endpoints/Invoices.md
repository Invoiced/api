Invoices
====

* [List Invoices](#list-invoices)
* [Creating an Invoice](#creating-an-invoice)
* [Fetch an Invoice](#fetch-an-invoice)
* [Editing an Invoice](#editing-an-invoice)
* [Sending an Invoice](#sending-an-invoice)
* [Deleting a Customer](#deleting-an-invoice)

### List Invoices

	GET /invoices

#### Parameters

Name | Type | Description
-----|------|-------------
`sort`|`string`|Column to sort by, i.e. `name asc`
`filter`|`object`|[Filter](../README.md#filter)
`status`|`string`|Can be `paid`,`sent`,`overdue`,`not_sent`, or `unpaid`

#### Response

```
Status: 200 OK
Link: <https://api.invoiced.com/invoices?page=1&per_page=10>; rel="self",
	  <https://api.invoiced.com/invoices?page=1&per_page=10>; rel="first",
	  <https://api.invoiced.com/invoices?page=2&per_page=10>; rel="next",
	  <https://api.invoiced.com/invoices?page=3&per_page=10>; rel="last"
X-Total-Count: 10
```

```json
{
	"invoices": [
		{
	        "created_at": 1415229884,
	        "updated_at": 1416291302,
	        "id": 46225,
	        "company": 3694,
	        "customer": 15444,
	        "name": "Invoice # INV-0016",
	        "currency": "USD",
	        "date_format": "M j, Y",
	        "template": null,
	        "estimate": null,
	        "subscription": 410,
	        "late_payment_reminders_disabled": false,
	        "number": "INV-0016",
	        "date": 1416290400,
	        "due_date": 1416549600,
	        "purchase_order": null,
	        "items": [
	            {
	                "id": 79,
	                "type": "product",
	                "name": "Copy Paper, Case",
	                "description": "20 lb., 92 US / 104 Euro Bright, Ideal for toner-based copiers, plain-paper fax machines,and printers",
	                "quantity": 1,
	                "unit_cost": 45,
					"amount": 45,
	                "fields": []
	            },
	            {
	            	"id": 83,
	                "type": "service",
	                "name": "Delivery",
	                "description": "",
	                "quantity": 1,
	                "unit_cost": 10,
	                "amount": 10,
	                "fields": []
	            }
	        ],
	        "terms": null,
	        "notes": null,
	        "subtotal": 55,
	        "total": 55,
	        "amount_paid": 0,
	        "balance": 55,
	        "fields": [],
	        "sent": false,
	        "closed": false,
	        "paid": false,
	        "client_view_url": "https://invoiced.com/dundermifflin/CUST-0001/INV-0016",
	        "pdf_url": "https://invoiced.com/dundermifflin/CUST-0001/INV-0016/pdf",
	        "status": "overdue"
	    },
	    {...}
	]
}
```

### Creating an Invoice

	POST /invoices

#### Input

```json
{
    "customer": 15444,
    "name": null,
    "currency": "USD",
    "template": null,
    "estimate": null,
    "late_payment_reminders_disabled": false,
    "number": "INV-0016",
    "date": 1416290400,
    "due_date": 1416549600,
    "purchase_order": null,
    "items": [
        {
            "id": 79,
            "type": "product",
            "name": "Copy Paper, Case",
            "description": "20 lb., 92 US / 104 Euro Bright, Ideal for toner-based copiers, plain-paper fax machines,and printers",
            "quantity": 1,
            "unit_cost": 45,
            "fields": []
        },
        {
        	"id": 83,
            "type": "service",
            "name": "Delivery",
            "description": "",
            "quantity": 1,
            "unit_cost": 10,
            "fields": []
        }
    ],
    "terms": null,
    "notes": null,    
    "fields": [],
    "sent": false,
    "closed": false
}
```

#### Response

	Status: 201 Created

```json
{
	"invoice": {
	    "customer": 15444,
	    "name": "Invoice # INV-0016",
	    "currency": "USD",
	    "date_format": "M j, Y",
	    "template": null,
	    "estimate": null,
	    "subscription": null,
	    "late_payment_reminders_disabled": false,
	    "number": "INV-0016",
	    "date": 1416290400,
	    "due_date": 1416549600,
	    "purchase_order": null,
	    "items": [
	        {
	            "id": 79,
	            "type": "product",
	            "name": "Copy Paper, Case",
	            "description": "20 lb., 92 US / 104 Euro Bright, Ideal for toner-based copiers, plain-paper fax machines,and printers",
	            "quantity": 1,
	            "unit_cost": 45,
	"amount": 45,
	            "fields": []
	        },
	        {
	        	"id": 83,
	            "type": "service",
	            "name": "Delivery",
	            "description": "",
	            "quantity": 1,
	            "unit_cost": 10,
	            "amount": 10,
	            "fields": []
	        }
	    ],
	    "terms": null,
	    "notes": null,
	    "total": 55,
	    "amount_paid": 0,
	    "balance": 55,
	    "fields": [],
	    "sent": false,
	    "closed": false,
	    "paid": false,
	    "client_view_url": "https://invoiced.com/dundermifflin/CUST-0001/INV-0016",
	    "pdf_url": "https://invoiced.com/dundermifflin/CUST-0001/INV-0016/pdf",
	    "status": "overdue"
	}
}
```

### Fetch an Invoice
	
	GET /invoices/:id

#### Response

	Status: 200 OK

```json
{
	"invoice": {
	    "customer": 15444,
	    "name": "Invoice # INV-0016",
	    "currency": "USD",
	    "date_format": "M j, Y",
	    "template": null,
	    "estimate": null,
	    "subscription": null,
	    "late_payment_reminders_disabled": false,
	    "number": "INV-0016",
	    "date": 1416290400,
	    "due_date": 1416549600,
	    "purchase_order": null,
	    "items": [
	        {
	            "id": 79,
	            "type": "product",
	            "name": "Copy Paper, Case",
	            "description": "20 lb., 92 US / 104 Euro Bright, Ideal for toner-based copiers, plain-paper fax machines,and printers",
	            "quantity": 1,
	            "unit_cost": 45,
	"amount": 45,
	            "fields": []
	        },
	        {
	        	"id": 83,
	            "type": "service",
	            "name": "Delivery",
	            "description": "",
	            "quantity": 1,
	            "unit_cost": 10,
	            "amount": 10,
	            "fields": []
	        }
	    ],
	    "terms": null,
	    "notes": null,
	    "total": 55,
	    "amount_paid": 0,
	    "balance": 55,
	    "fields": [],
	    "sent": false,
	    "closed": false,
	    "paid": false,
	    "client_view_url": "https://invoiced.com/dundermifflin/CUST-0001/INV-0016",
	    "pdf_url": "https://invoiced.com/dundermifflin/CUST-0001/INV-0016/pdf",
	    "status": "overdue"
	}
}
```

### Editing an Invoice

	PATCH /invoices/:id

#### Input

```json
{
	"sent": true
}
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
{
	"to": [
		{
			"name": "Client",
			"email": "client@example.com"
		}
	],
	"bcc": "billing@acmecorp.com,jan@acmecorp.com",
	"subject": "optional subject...",
	"message": "optional message...",
	"attach_pdf": false
}
```

#### Response

	Status: 201 Created

```json
{
	"success": true
}
```

### Deleting an Invoice

	DELETE /invoices/:id

#### Response

	Status: 204 No Content