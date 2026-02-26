---
title: "Building a sales report"
id: apiIntegrationChecklistAccounting
type: section
documentId: devCookbook
parentSectionFile: devCookbook-cookbookAnalyticsOmitChunkFromSearchIndex.md
parentSectionTitle: "Reports"
previousSectionFile: devCookbook-apiIntegrationChecklistPayroll.md
previousSectionTitle: "Building labor reports"
nextSectionFile: devCookbook-apiHowToCashReports.md
nextSectionTitle: "Building a cash transactions report"
externalReferences: [https://central.toasttab.com/s/article/Voiding-Items-Payments-and-Checks, https://doc.toasttab.com/openapi/menus/tag/Data-definitions/schema/MenuItem/, https://central.toasttab.com/s/article/Tip-Withholding, https://central.toasttab.com/s/article/Creating-and-Assigning-Revenue-Centers, https://central.toasttab.com/s/article/Sales-Categories-1492812477858, https://central.toasttab.com/s/article/Use-Menu-Item-Tags-to-Maximize-Reporting-1492918026171, https://central.toasttab.com/s/article/Dining-Options-1492794310377, https://central.toasttab.com/s/article/Setup-Restaurant-Hours-and-Services]
excerpt: "Use the instructions below to build sales reports using information from the Toast platform. This information will help when reporting on total sales and payments, reviewing tax information,..."
procedures: 0
codeExamples: 0
---

Use the instructions below to build sales reports using information from the Toast platform. This information will help when reporting on total sales and payments, reviewing tax information, identifying top-selling items, and more.

This integration provides restaurants with useful information to run their business.

## Required scopes

To follow these instructions, you must have the following [scopes](docs/en-us/apiDevGuide-apiScopes):

- `config:read`


- `menus:read`


- `orders:read`


- `restaurants:read`



## Setup and planning

### Complete initial integration setup

Review and implement the instructions in [How to build a Toast integration](docs/en-us/devCookbook-apiIntegrationChecklistGeneral).

### Decide what information your reports will provide

Before beginning development, decide what reports you will build.

This guide describes how to report on the following sales information:



****Total sales****
: - Number of orders


- Order amount charged


- Tax amount charged



> **Note**
> 
> You can also report on marketplace facilitator tax payments. For more information see, [Marketplace facilitator tax payments](docs/en-us/adminGuide-adminMarketplaceFacilitatorTaxPayments).



- Amount discounted


- Amount charged in service charges





****Payment information****
: - Value of payments taken


- Amount paid by payment type


- Value of tips collected


- Value of refunds given


- Value of payments voided





****Order trending per category****
: - Sales per revenue center


- Sales per sales category


- Sales per item tag


- Sales per dining option behavior


- Sales per order source


- Sales per service period





****Summarization****
: - Average value per order


- Percentage of orders with discounts


- Average discount value


- Percentage of payments with refunds







### Review menu and order structure

Reporting on sales depends on restaurants' usage of menu items and the overall structure of orders.

To understand Toast menu concepts before you begin development, review [menu hierarchy information](docs/en-us/adminGuide-adminMenuHierarchy).

To review order structure, see [Orders API overview](docs/en-us/apiDevGuide-portalOrdersApiOverview).

## Retrieving restaurant information

### Set up recurring retrieval of menu and configuration information

Use the [menus webhook](docs/en-us/apiDevGuide-apiMenusWebhook) or query the `/metadata` endpoint of the menus API throughout the day.

Retrieve a new menu when you determine that [your existing menu is outdated](docs/en-us/apiDevGuide-apiDeterminingIfYourMenuJsonIsOutdated_V2).

In addition, query the following configuration API endpoints at least once a day:

- `/alternativePaymentTypes`


- `/diningOptions`


- `/discounts`


- `/restaurantServices`


- `/revenueCenters`


- `/salesCategories`


- `/serviceCharges`


- `/taxRates`


- `/tipWithholding`


- `/voidReasons`



### Set up recurring order retrieval of transactional information

To report on order information, you need to retrieve orders at least once per day using the `startDate` and `endDate` parameters of the `/ordersBulk` endpoint of the orders API.



> **Note**
> 
> Toast support recommends using the [orders updated webhook](docs/en-us/apiDevGuide-devOrdersWebhookRef#apiOrdersWebhookOrderUpdated) to receive order updates as they occur instead of pulling order updates with the `/ordersBulk`endpoint.


See [Getting detailed information about multiple orders](docs/en-us/apiDevGuide-apiOrdersGetDetailedInfoAboutMultipleOrders) for more information.

### Consider historical backfill

When a restaurant first connects to your integration, they may expect to see some historical information already displayed in your system. Define how many days of historical orders you retrieve when a restaurant first connects to your integration.

To retrieve the orders for these days, use either the `businessDate` or `startDate`/`endDate`parameters of the `/ordersBulk` endpoint of the orders API.

Toast support recommends retrieving twelve weeks of historical orders when a restaurant first connects to your integration.

### Determine closeout hour

The `closeoutHour` value in the `General`object returned by the [restaurants API](docs/en-us/apiDevGuide-apiRestaurantInformation) contains the restaurant's closeout hour.

The default closeout hour is 4:00 a.m. local time unless a Toast employee changes this setting. The `businessDate` value on order entities changes after the `closeoutHour`.

Consider [daylight savings time](docs/en-us/apiDevGuide-api_dates_and_timestamps#apiDaylightSavingsTime) when interacting with the closeout hour.

## Building report functionality

### Separate future orders from past orders

Guests may place orders for future fulfillment. For example, a guest may place a catering order on a Monday to be fulfilled on a Friday.

An order is a future order if its `promisedDate` is in the future. In all order sales summaries, consider separating future orders from past orders so that restaurants have an accurate picture of how many orders they *fulfilled* on each day in the past.

For more information about how integration partners submit future orders, see [Scheduling future orders](docs/en-us/apiDevGuide-orders_api_future_orders).

### Suppress voided entities by default

Servers can void erroneous orders, checks, item selections, and payments. Restaurants may not want information about voided entities to appear in their sales summaries.

If the `voided` value on an order, check, selection, or payment is `true`, Toast support recommends ignoring this entity when calculating all sales information below. If you allow restaurants to display voided entities in their reports, consider displaying selections' and payments' void reasons by mapping the `voidReason` value on the entity to the information in the `/voidReasons` endpoint of the configuration API.

See [this Toast Central article](https://central.toasttab.com/s/article/Voiding-Items-Payments-and-Checks) for more information about how to test void functionality.

### Suppress deferred entities

Item selections can be marked as deferred. Deferred selections (usually Gift Cards or similar) see the value of the selection realized at the restaurant at a later date. The sales report for that later date will correctly capture that sales information. These selections should not appear in sales summaries.

If the `deferred` value on a selection is `true`, Toast support recommends ignoring this entity when calculating all sales information below.

### Filter fundraising contributions from sales reporting

Fundraising contributions appear as service charges in the orders API. When guests make donations through the Toast fundraising feature, the donation amount is added to the check as a service charge with a `serviceChargeCategory` value of `FUNDRAISING_CAMPAIGN`.

Since fundraising contributions are included in the `check.amount` value (which includes all non-gratuity service charges), you may want to exclude them when calculating net sales or order amounts for reporting purposes.

To filter fundraising contributions from your calculations:

- **For service charge totals:**Check the `serviceChargeCategory` value on each `AppliedServiceCharge` object. If the `serviceChargeCategory` value is `FUNDRAISING_CAMPAIGN`, exclude this service charge when calculating service charge totals for sales reporting.


- **For order amount calculations:** To calculate the net order amount (excluding fundraising contributions), you can either:

- Sum the `amount` values on each check, then subtract the sum of `chargeAmount` values from service charges where `serviceChargeCategory` is `FUNDRAISING_CAMPAIGN`.


- Use the net sales calculation method described in [Calculating net sales using the orders API](docs/en-us/apiDevGuide-apiOrdersNetSalesCalculation), which builds the net order amount from components and excludes fundraising contributions when adding service charges.





For more information about the `serviceChargeCategory`field and other service charge types, see [Service charges for checks](docs/en-us/apiDevGuide-apiOrderPrices#apiServiceCharges).

### Reporting on total sales

Below are suggestions for reporting on total sales within a given timeframe.

All ideas require polling the `/ordersBulk` endpoint of the orders API for the desired timeframe.



****Number of orders****
: Sum the total number of orders.



****Order amount charged****
: To calculate the gross order amount charged (including fundraising contributions), sum the `amount` values on each check.

To calculate the net order amount charged (excluding fundraising contributions), see [Filter fundraising contributions from sales reporting](docs/en-us/devCookbook-apiIntegrationChecklistAccounting#salesReportBuildFuncSuppressFundraising).



****Tax amount charged****
: Sum the `taxAmount` values on each check. To drill down:

- To allow users to drill down into the tax amount charged per tax rate, use the information you saved from the `/taxRates` endpoint of the configuration API to look up the name of the tax rate in the `taxRate`value, and then sum the `taxAmount` values within each tax rate.


- To allow users to see which orders were tax exempt, allow users to filter the report based on the `taxExempt` value on the `Check`object.





****Amount discounted****
: Sum the `discountAmount` values in the `AppliedDiscount` objects on each check and item selection. If the menu item is tax-inclusive, sum the `nonTaxDiscountAmount` values in the `AppliedDiscount` objects on each check and item selection. You can check if an item is tax-inclusive by checking the menu item's `taxInclusion` value in the [menus API](https://doc.toasttab.com/openapi/menus/tag/Data-definitions/schema/MenuItem/).

To allow users to drill down into the amount discounted with each discount:

1. Use the information you saved from the `/discounts` endpoint of the configuration API to look up the name of the discount in the `discount`value.


2. Sum the `discountAmount` values within each discount.





****Amount charged in service charges****
: Sum the `chargeAmount` values on the `AppliedServiceCharge` objects on each check. Exclude service charges where the `serviceChargeCategory` value is `FUNDRAISING_CAMPAIGN` from your service charge totals.

To allow users to drill down into the amount charged for each service charge:

1. Use the information you saved from the `/serviceCharges` endpoint of the configuration API to look up the name of the service charge in the `serviceCharge` value.


2. Sum the `chargeAmount` values within each service charge. Exclude service charges where `serviceChargeCategory` is `FUNDRAISING_CAMPAIGN`.







### Reporting on payments

Below are ideas for reporting on payment information for a given timeframe:



****Value of payments taken (excluding tips)****
: Poll the `/payments` endpoint of the orders API using the `paidBusinessDate` parameter.

Sum the `amount` values on each payment.



****Amount paid by payment type****
: Poll the `/payments` endpoint of the orders API using the `paidBusinessDate` parameter. Sum the `amount` value on each payment, separating the payment totals by the `type` value on the `Payment`object.

If the payment type is `OTHER`, use the information you saved from the `/alternativePaymentTypes` endpoint of the configuration API to look up the name of the payment type associated with the `otherPayment` value on the payment.



****Value of tips collected****
: Poll the `/payments` endpoint of the orders API using the `paidBusinessDate` parameter. Sum the `tipAmount` values on each payment.

If the restaurant uses [tip withholding](https://central.toasttab.com/s/article/Tip-Withholding) (exposed in the `/tipWithholding`endpoint of the configuration API), separate the amount of tip money distributed to staff from the amount withheld. To calculate the tips withheld, multiply the `percentage` value in the `/tipWithholding` endpoint by the total value of tips collected.



****Value of refunds given****
: Poll the `/payments` endpoint of the orders API using the `refundBusinessDate` parameter.

- To calculate sales refunds, sum the `refundAmount` values on the `Refund`object.


- To calculate tip refunds, sum the `tipRefundAmount` values on the `Refund`object.





****Value of payments voided****
: Poll the `/payments` endpoint of the orders API using the `voidBusinessDate` parameter.

Sum the `amount` values on each payment.





### Reporting on order trending per category

Below are ideas for reporting on sales per category within a given timeframe.

All ideas require polling the `/ordersBulk` endpoint of the orders API for the desired timeframe.



****Sales per [revenue center](https://central.toasttab.com/s/article/Creating-and-Assigning-Revenue-Centers)****
: Group orders based on the associated `revenueCenter`. Sum the `amount` values on all nested checks.

To retrieve the name of a revenue center, use the `/revenueCenters` endpoint of the configuration API.



****Sales per [sales category](https://central.toasttab.com/s/article/Sales-Categories-1492812477858)****
: Group orders based on the associated `salesCategory`. Sum the `amount` values on all nested checks.

To retrieve the name of a sales category, use the `/salesCategories` endpoint of the configuration API.



****Sales per [item tag](https://central.toasttab.com/s/article/Use-Menu-Item-Tags-to-Maximize-Reporting-1492918026171):****
: To report on sales per item tag:

- When you poll the `/menus` endpoint of the menus API, save a mapping of menu items and their associated `itemTag` values.


- Loop through each order and retrieve the `menuItem` on each selection on each nested check.


- Add the `amount` value on the check to the total sales for each item tag associated with each item.





****Sales per [dining option](https://central.toasttab.com/s/article/Dining-Options-1492794310377) behavior****
: To calculate sales per dining option behavior:

- When you poll the `/diningOptions` endpoint of the configuration API, save a mapping of dining options and their associated `behavior` values.


- Loop through each order and retrieve the `diningOption` on each selection on each nested check.


- Add the `amount` value on the check to the total sales for the behavior associated with this dining option.





****Sales per order source****
: Group orders based on the associated `source`. Sum the `amount` values on all nested checks.



****Sales per [service period](https://central.toasttab.com/s/article/Setup-Restaurant-Hours-and-Services)****
: Group orders based on the associated `service` . Sum the `amount` values on all nested checks.

To retrieve the name of a service period, use the `/restaurantServices` endpoint of the configuration API.





### Summarizing sales information

Below are ideas for calculating sales statistics within a given timeframe.

All ideas require polling the `/ordersBulk` endpoint of the orders API for the desired timeframe.



****Average value per order****
: Divide the total order amount charged by the number of orders in the timeframe.



****Percentage of orders with discounts****
: Count the number of orders whose nested `Check`and `Selection` objects contain information in their `appliedDiscount` values.

Divide this number by the total number of orders in the timeframe.



****Average discount value****
: Divide the total amount discounted by the number of discounted orders (calculated in the previous item).



****Percentage of payments with refunds****
: Using the `paidBusinessDate` parameter in the `/payments` endpoint of the orders API, count the total number of payments in a given business day.

Separately, calculate the number of payments with information in their nested `Refund` object.

Divide the number of payments with refund information by the total number of payments.





