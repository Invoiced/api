Changelog
=========
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

- The API documentation has been redesigned. It's now viewable at [invoiced.com/docs/api](https://invoiced.com/docs/api).