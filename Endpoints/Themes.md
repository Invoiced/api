Themes
====

Themes control the appearance of Estimates, Invoices, and Receipts. A theme specifies field titles and any custom HTML/CSS for use when rendering the document as a PDF or in the browser.

Whenever the HTML or CSS properties are null or `custom_appearance` is `false`, the latest stock themes will be used when rendering documents. Otherwise, the `custom_appearance` property may be set to `true` in order to use the non-null from `estimate_html`, `estimate_css`, `invoice_html`, `invoice_css`, `receipt_html`, and `receipt_css`.

The HTML templates use Mustache for templating awesomeness. Please consult the [Mustache documentation](https://mustache.github.io/mustache.5.html) to learn more. You can use [this tool](http://trymustache.com/) to validate your HTML templates. 

* [List Themes](#list-themes)
* [Creating a Theme](#creating-a-theme)
* [Fetch a Theme](#fetch-a-theme)
* [Editing a Theme](#editing-a-theme)
* [Deleting a Theme](#deleting-a-theme)

### List Themes

  GET /themes

#### Parameters

Name | Type | Description
-----|------|-------------
`sort`|`string`|Column to sort by, i.e. `name asc`
`filter`|`object`|[Filter](../README.md#filter)

#### Response

```
Status: 200 OK
Link: <https://api.invoiced.com/themes?page=1&per_page=10>; rel="self",
    <https://api.invoiced.com/themes?page=1&per_page=10>; rel="first",
    <https://api.invoiced.com/themes?page=2&per_page=10>; rel="next",
    <https://api.invoiced.com/themes?page=3&per_page=10>; rel="last"
X-Total-Count: 30
```

```json
themes: [
  {
    "created_at": 1415228628,
    "updated_at": 1422902098,
    "id": 6,
    "name": "My Theme",
    "from_title": "From",
    "to_title": "Client",
    "tax_id_title": null,
    "customer_number_title": "Customer Number",
    "show_customer_no": false,
    "invoice_number_title": "Invoice Number",
    "date_title": "Date",
    "due_date_title": "Due Date",
    "date_format": null,
    "purchase_order_title": "Purchase Order",
    "show_purchase_order": false,
    "quantity_header": "Quantity",
    "item_header": "Item",
    "unit_cost_header": "Rate",
    "amount_header": "Amount",
    "subtotal_title": "Subtotal",
    "notes_title": "Notes",
    "terms_title": "Terms",
    "header": "INVOICE",
    "payment_terms_title": "Payment Terms",
    "amount_paid_title": "Amount Paid",
    "balance_title": "Balance Due",
    "header_estimate": "ESTIMATE",
    "estimate_number_title": "Estimate Number",
    "total_title": "Total",
    "header_receipt": "RECEIPT",
    "amount_title": "Amount",
    "payment_method_title": "Payment Method",
    "check_no_title": "Check #",
    "receipt_footer": "Thank you!",
    "custom_appearance": false,
    "estimate_css": null,
    "estimate_html": null,
    "invoice_css": null,
    "invoice_html": null,
    "receipt_css": null,
    "receipt_html": null
  },
  {...}
]
```

### Creating a Theme

  POST /themes

#### Input

```json
{
    "name": "My Theme",
    "from_title": "From",
    "to_title": "Client",
    "tax_id_title": null,
    "customer_number_title": "Customer Number",
    "show_customer_no": false,
    "invoice_number_title": "Invoice Number",
    "date_title": "Date",
    "due_date_title": "Due Date",
    "date_format": null,
    "purchase_order_title": "Purchase Order",
    "show_purchase_order": false,
    "quantity_header": "Quantity",
    "item_header": "Item",
    "unit_cost_header": "Rate",
    "amount_header": "Amount",
    "subtotal_title": "Subtotal",
    "notes_title": "Notes",
    "terms_title": "Terms",
    "header": "INVOICE",
    "payment_terms_title": "Payment Terms",
    "amount_paid_title": "Amount Paid",
    "balance_title": "Balance Due",
    "header_estimate": "ESTIMATE",
    "estimate_number_title": "Estimate Number",
    "total_title": "Total",
    "header_receipt": "RECEIPT",
    "amount_title": "Amount",
    "payment_method_title": "Payment Method",
    "check_no_title": "Check #",
    "receipt_footer": "Thank you!",
    "custom_appearance": false,
    "estimate_css": null,
    "estimate_html": null,
    "invoice_css": null,
    "invoice_html": null,
    "receipt_css": null,
    "receipt_html": null
}
```

#### Response

  Status: 201 Created

```json
{
  "theme": {
    "created_at": 1415228628,
    "updated_at": 1422902098,
    "id": 6,
    "name": "My Theme",
    "from_title": "From",
    "to_title": "Client",
    "tax_id_title": null,
    "customer_number_title": "Customer Number",
    "show_customer_no": false,
    "invoice_number_title": "Invoice Number",
    "date_title": "Date",
    "due_date_title": "Due Date",
    "date_format": null,
    "purchase_order_title": "Purchase Order",
    "show_purchase_order": false,
    "quantity_header": "Quantity",
    "item_header": "Item",
    "unit_cost_header": "Rate",
    "amount_header": "Amount",
    "subtotal_title": "Subtotal",
    "notes_title": "Notes",
    "terms_title": "Terms",
    "header": "INVOICE",
    "payment_terms_title": "Payment Terms",
    "amount_paid_title": "Amount Paid",
    "balance_title": "Balance Due",
    "header_estimate": "ESTIMATE",
    "estimate_number_title": "Estimate Number",
    "total_title": "Total",
    "header_receipt": "RECEIPT",
    "amount_title": "Amount",
    "payment_method_title": "Payment Method",
    "check_no_title": "Check #",
    "receipt_footer": "Thank you!",
    "custom_appearance": false,
    "estimate_css": null,
    "estimate_html": null,
    "invoice_css": null,
    "invoice_html": null,
    "receipt_css": null,
    "receipt_html": null
  },
}
```

### Fetch a Theme

  GET /themes/:id

#### Response

  Status: 200 OK

```json
{
  "theme": {
    "created_at": 1415228628,
    "updated_at": 1422902098,
    "id": 6,
    "name": "My Theme",
    "from_title": "From",
    "to_title": "Client",
    "tax_id_title": null,
    "customer_number_title": "Customer Number",
    "show_customer_no": false,
    "invoice_number_title": "Invoice Number",
    "date_title": "Date",
    "due_date_title": "Due Date",
    "date_format": null,
    "purchase_order_title": "Purchase Order",
    "show_purchase_order": false,
    "quantity_header": "Quantity",
    "item_header": "Item",
    "unit_cost_header": "Rate",
    "amount_header": "Amount",
    "subtotal_title": "Subtotal",
    "notes_title": "Notes",
    "terms_title": "Terms",
    "header": "INVOICE",
    "payment_terms_title": "Payment Terms",
    "amount_paid_title": "Amount Paid",
    "balance_title": "Balance Due",
    "header_estimate": "ESTIMATE",
    "estimate_number_title": "Estimate Number",
    "total_title": "Total",
    "header_receipt": "RECEIPT",
    "amount_title": "Amount",
    "payment_method_title": "Payment Method",
    "check_no_title": "Check #",
    "receipt_footer": "Thank you!",
    "custom_appearance": false,
    "estimate_css": null,
    "estimate_html": null,
    "invoice_css": null,
    "invoice_html": null,
    "receipt_css": null,
    "receipt_html": null
  },
}
```

### Editing a Theme

  PATCH /themes/:id

#### Input

```json
{
  "archived": true
}
```

#### Response

  Status: 200 OK

```json
{
  "success": true
}
```

### Deleting a Theme

  DELETE /themes/:id

#### Response

  Status: 204 No Content