Changelog
===

### March 16, 2015

- Removed the redundant `company` property on all API responses. Since API keys are owned by a single company, the key used implies which company is the owner.
- Removed the deprecated `date_format` property on estimates and invoices.

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