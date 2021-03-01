Changelog
=========
### March 1, 2021
- Added `invoice` property to Note object.

### February 22, 2021
- Credit note, estimate, invoice, and receipt PDFs can be downloaded by setting the `Accept` header to `application/pdf`.

### February 2, 2021
- Credit notes, estimates, and invoices have a `purchase_order` property.

### December 15, 2020
- Added `applied_credit` payment application type for applying credit balances.

### December 9, 2020
- Added Credit Balance Adjustment object.

### December 7, 2020
- Added Payment, Charge, and Refund objects. Payment objects replace Transactions with some added features to handle more complex cash application scenarios.

### December 2, 2020
- Added `currency` property to customers.

### November 17, 2020
- Added `payment.*` webhook events.
- Changed the structure of the perform charge endpoint.

### October 20, 2020
- The perform charge endpoint now supports processing payments for estimate deposits and advance payments.

### September 21, 2020
- The create file upload endpoint now supports multipart/form-data uploads.

### June 16, 2020
- Added a `currency` query parameter to the get current balance endpoint.

### June 5, 2020
- Setting the `invoice` property on credit notes is no longer required.

### April 21, 2020
- Added the Payment object.

### April 14, 2020
- Added `avalara_location_code` property to the Item object.
- The Catalog Item object has been renamed to Item.

### January 6, 2020
- A `template` parameter has been added when sending emails to use a custom email template.

### December 30, 2019
- The Go library has been updated to support all of the latest API capabilities and the documentation now includes Go code examples.

### December 27, 2019
- The .NET library has been updated to support all of the latest API capabilities and the documentation now includes .NET code examples.

### December 10, 2019
- Added create, retrieve, delete and list endpoints for payment sources.

### December 3, 2019
- Add the `bill_in_advance_days` property to subscriptions for advance billing.

### November 20, 2019
- The invoice, estimate, and subscription objects now have a `ship_to` property.

### October 25, 2019
- The create and update endpoints for documents (invoices, estimates, credit notes) now have a `calculate_taxes` parameter.

### October 21, 2019
- Added endpoint to perform a charge.
- Added endpoint to preview a new subscription without committing the transaction.
- New endpoints for voiding invoices, credit notes, and estimates.
- Added invoice consolidation endpoint.
- Added notes object and endpoints
- Added task object and endpoints.

### October 20, 2019
- Added create, retrieve, update, delete, and list endpoints for catalog items, plans, tax rates, and coupons.

### October 11, 2019
- Added `avalara_tax_code` and `gl_account` properties to the catalog item object.
- Added `department`, `phone`, `sms_enabled` and `title` properties to the contact object.
- Added `exclusive`, `expiration_date`, and `max_redemptions` properties to the coupon object.
- Added `autopay_delay_days`, `avalara_entity_use_code`, `avalara_exemption_number`, `chase`, `chasing_cadence`, `next_chase_step`, `credit_hold`, `credit_limit`, `owner`, `parent_customer`, and `taxable` properties to the customer object.
- Added `approved` and `expiration_date` properties to the estimate object.
- Added `payment_plan` property to the invoice object.
- Added `pricing_mode`, `quantity_type` and `tiers` property to the plan object.
- Added `bill_in`, `contract_period_end`, `contract_period_start`, `contract_renewal_cycles`, `contract_renewal_mode`, and `paused` properties to the subscription object.
- Added `inclusive` property to the tax rate object.

### June 17, 2019
- Added contact event types.

### May 8, 2019
- Added payment source event types.

### May 1, 2019
- Added new event types.

### March 15, 2019
- Added a `language` property to the customer object.

### February 28, 2019
- Our [.NET client library](https://github.com/Invoiced/invoiced-csharp) is now available!

### December 16, 2018
- Added `mrr` and `recurring_total` properties to subscriptions.

### December 15, 2018
- Removed `chase` and `next_chase_on` property on invoices. The new chasing system chases balances at the customer level.

### August 16, 2018
- Added `updated_after` request parameter when listing customers, estimates, credit notes, invoices, subscriptions, and transactions to only return results updated after a given timestamp.

### April 28, 2018
- Removed `description` property on plans. It is recommended to use the subscription addon description for information specific to a subscription. Otherwise the catalog item description will be used on line items.

### April 16, 2018
- Added `catalog_item` property to plans. Plans can now be attributed to a parent catalog item, which represents a product or service you sell.

### April 15, 2018
- Added `plan` property to subscription addons. Using plans for addons are now recommended over catalog items.

### January 26, 2018

- Added `start_date` and `end_date` parameters when listing transactions.

### September 15, 2017
- Added estimate deposits.
- Can specify `proration_date` when updating subscriptions for changing proration calculations.

### August 9, 2017
- Added `disabled_payment_methods` parameter when creating or updating customers, invoices, and estimates

### August 2, 2017
- Added retrieve event endpoint.

### June 2, 2017
- Added a `description` property to subscription addons

### May 8, 2017
- Added `sign_up_page` and `sign_up_url` properties to customers

### April 24, 2017
- Pending line items now have a `customer` property
- Added pending line item events

### April 20, 2017
- On customer and invoice objects the `collection_mode` property has been replaced with the `autopay` property

### April 11, 2017
- Added estimate webhook events

### January 24, 2017
- Support for calendar billing with subscriptions

### January 21, 2017
- All objects now include their object type

### January 12, 2017
- Added estimates
- Added credit notes

### December 15, 2016
- Removed `tags` property on invoices. Please use `metadata` instead.

### November 26, 2016
- Added payment plan endpoints

### November 10, 2016
- Added pricing objects: Catalog Items, Plans, Tax Rates, and Coupons

### October 19, 2016
- Added `invoiced-java` documentation

### September 23, 2016
- Removed the `fee` property from transactions

### September 12, 2016
- Added endpoint to retrieve events
- Added `timestamp` property to events

### August 20, 2016
- Subscriptions can now have a `canceled` status
- Canceling a subscription returns the updated object instead of a 204
- Canceled or finished subscriptions can now be retrieved in the list subscriptions endpoint

### August 10, 2016
- Added `invoice.paid` event

### July 16, 2016
- Added `payment_source` to transactions

### July 12, 2016
- Added metadata filtering

### June 6, 2016
- Subscriptions now have `cancel_at_period_end` and `canceled_at` properties

### June 1, 2016
- Added endpoints for creating and managing file attachments

### May 27, 2016
- Removed customer subscriptions endpoint. Recommend using list subscriptions instead with a filter for the customer.
- Added endpoints for managing customer contacts
- Removed `sent` property on transactions
- Removed `sent` property on invoices

### May 26, 2016
- Can filter customers with/without a payment source and credit balance
- Added `history` to customer balance endpoint

### May 2, 2016
- Objects now support a key-value metadata store for sending additional information into Invoiced

### March 30, 2016
- Added `discountable` and `taxable` properties to line items

### March 29, 2016

- Removed `other_phone` property on customers
- Removed `terms` property on invoices
- Removed `theme` property on invoices and transactions
- Renamed `renewed_last` and `renews_next` properties on subscriptions to `period_start` and `period_end` respectively
- Revert `external_id` property on customers back to `number`

### March 8, 2016

- Added metered billing section

### February 26, 2016

- Added `taxes` property to customers

### February 24, 2016

- Added bank account object
- The `number` property on customers has been renamed to `external_id`
- Invoices can no longer have `overpaid` status

### February 8, 2016

- Added `tags` property to invoices
- Added `tags` parameter to list all invoices endpoint for filtering invoices by tag

### February 5, 2016

- Added `payment_url` property to invoices

### January 29, 2016

- Custom line item types supported

### January 26, 2016

- Added `failure_reason` Transaction Object Attributes and removed it from the Json Response Examples
- Added instructions for accessing sandbox API

### December 30, 2015

- Added webhooks that are now in beta

### December 12, 2015

- Added `expires` property to discounts

### December 5, 2015

- Added `shipping` line item type

### December 4, 2015

- Add Subscription endpoints

### December 3, 2015

- Added official Python client library.
- Removed `website` property from customers
- Added `object` property to payment sources
- Added Card object

### November 3, 2015

- The new `catalog_item` parameter can be used to fill in Line Items with pricing from your Invoiced catalog

### October 22, 2015

- Added `start_date` and `end_date` parameters when listing invoices.

### September 8, 2015

- Invoices can have `pending` status when there is a pending payment.

### August 20, 2015

- Added official PHP client library.

### July 30, 2015

- The API documentation has been redesigned. It's now viewable at [invoiced.com/docs/api](https://invoiced.com/resources/docs/api).