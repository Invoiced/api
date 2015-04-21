Changelog
===

### April 21, 2015

- Added `number` property to stored items.
- Added `item_number_title` and `show_item_number` properties to themes.

### April 17, 2015

- Added `next_chase_on` property to invoices.

### April 15, 2015

- Added `email` property to customers.
- Added `attempt_count`, `next_payment_attempt`, and `stripe_invoice` properties to invoices.

### April 6, 2015

- Added Templates endpoints for managing pre-filled shortcuts for estimates and invoices.
- Added Themes endpoints for managing the appearance of estimates, invoices, and receipts.
- Added `theme` properties to Estimates and Invoices.

### March 29, 2015

- Added `discounts`, `taxes`, and `shipping` properties to Stored Items.

### March 28, 2015

- Renamed `Payments` to `Transactions`. Transactions can represent a `charge`, `payment`, `refund`, or `adjustment` with the `transaction_type` property.
- Added Stored Items endpoints for frequently invoiced items, such as services or products.

### March 26, 2015

- Added Payment Methods endpoints for managing how your clients pay.

### March 25, 2015

- Estimates, Invoices, and Line Items now have `discounts`, `taxes`, and `shipping` properties. Each of these properties are a list of Applied Rates matching the Rate's type. For example, discounts can be added to an Invoice by adding `"discounts":[{"rate": rate_id}]`.
- Added Rates endpoints for managing discounts, taxes, and shipping.

### March 20, 2015

- Estimates now have a `closed` property. When an estimate is closed it cannot be modified. An estimate is closed automatically upon approval.

### March 18, 2015

- Payments are moving to a more diverse transaction model. New `transaction_type`, `method`, `status`, `gateway`, `gateway_id`, and `parent_transaction` properties have been added. The `type`, `check_no`, `paypal_transaction_id`, and `stripe_charge` properties have been deprecated.

### March 16, 2015

- Removed the redundant `company` property on all API responses. Since API keys are owned by a single company, the key used implies which company is the owner.
- Removed the deprecated `date_format` property on estimates and invoices.
- All `currency` properties are now lowercase.
- Support for multiple templates are being deprecated due to a lack of interest. Removed the `template` property on estimates and invoices. In the near future companies will only have a single template.
- Added `draft` property to invoices and estimates. Invoices and estimates are not published to the client's account until `draft` is `false`. If you are creating drafts then you must set `draft=true` when the model is first created because it will default to `false`.
- Invoice line items now have a `plan` property that associates with line items generated from a recurring plan.

### March 13, 2015

- The `client_view_url` property of estimate and invoices has been renamed to `url`.

### February 18, 2015

- The `id` property of estimate and invoice line items have been renamed to `item`. When set, they reference a stored item. The `id` property is now the identifier for the line item.

### January 28, 2015

- Added `disabled_payment_methods` property to invoices to turn off various payment methods for a specific invoice.

### January 26, 2015

- Added `sent` property to payments to track if a receipt has been sent

### December 31, 2014

- Removed option to set `date_format` for individual invoices and estimates

### December 26, 2014

- Added `attach_pdf` parameter when sending emails.
- Emails can now be sent to multiple recipients. The `to` parameter has changed, however, the old way of passing in a single address still works.
- Added Contacts API for customers
- Added support for estimate and invoice names