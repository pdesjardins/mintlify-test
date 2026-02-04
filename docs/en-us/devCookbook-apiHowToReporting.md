---
title: "Building a data warehouse integration"
id: apiHowToReporting
type: section
documentId: devCookbook
parentSectionFile: devCookbook-cookbookAnalyticsOmitChunkFromSearchIndex.md
parentSectionTitle: "Reports"
previousSectionFile: devCookbook-apiHowToCashReports.md
previousSectionTitle: "Building a cash transactions report"
nextSectionFile: devCookbook-apiIntegrationChecklistInventory.md
nextSectionTitle: "Building an inventory tracking integration"
externalReferences: [https://doc.toasttab.com/openapi/configuration/overview/, https://doc.toasttab.com/openapi/menus/overview/, https://doc.toasttab.com/openapi/configuration/operation/revenueCentersGet/, https://doc.toasttab.com/openapi/configuration/operation/salesCategoriesGet/, https://central.toasttab.com/s/article/Creating-and-Assigning-Revenue-Centers, https://central.toasttab.com/s/article/Sales-Categories-1492812477858, https://doc.toasttab.com/openapi/configuration/operation/alternatePaymentTypesGet/, https://doc.toasttab.com/openapi/configuration/operation/diningOptionsGet/, https://doc.toasttab.com/openapi/configuration/operation/discountsGet/, https://doc.toasttab.com/openapi/configuration/operation/serviceChargesGet/, https://doc.toasttab.com/openapi/configuration/operation/taxRatesGet/, https://doc.toasttab.com/openapi/configuration/operation/restaurantServicesGet/, https://doc.toasttab.com/openapi/configuration/operation/serviceAreasGet/, https://doc.toasttab.com/openapi/configuration/operation/tablesGet/, https://central.toasttab.com/s/article/Setup-Restaurant-Hours-and-Services, https://central.toasttab.com/s/article/Creating-Service-Areas-and-Table-Setup-1493049150430, https://doc.toasttab.com/openapi/configuration/operation/cashDrawersGet/, https://doc.toasttab.com/openapi/configuration/operation/noSaleReasonsGet/, https://doc.toasttab.com/openapi/configuration/operation/payoutReasonsGet/, https://doc.toasttab.com/openapi/configuration/operation/voidReasonsGet/, https://doc.toasttab.com/openapi/configuration/operation/breakTypesGet/, https://doc.toasttab.com/openapi/labor/operation/jobsGet/]
excerpt: "Follow the steps below to build a data warehouse integration with Toast."
procedures: 0
codeExamples: 0
---

Follow the steps below to build a data warehouse integration with Toast.

This type of integration provides restaurants with greater visibility into key information that will help them run their business.

This document describes how to build a general data warehouse. For more detailed information about how to report on specific types of data, see [Building a sales report](apiIntegrationChecklistAccounting.html) and [Building labor reports](apiIntegrationChecklistPayroll.html).

## Required scopes

To follow these instructions, you must have the following [scopes](apiScopes.html):

- `cashmgmt:read`


- `config:read`


- `labor.employees:read`


- `labor:read`


- `menus:read`


- `restaurants:read`


- `orders:read`



## Complete initial integration setup

Review and implement the instructions in [How to build a Toast integration](apiIntegrationChecklistGeneral.html).

## Determine closeout hour

The `closeoutHour` value in the `General`object returned by the [restaurants API](apiRestaurantInformation.html) contains the restaurant's closeout hour.

The default closeout hour is 4:00 a.m. local time unless a Toast employee changes this setting. The `businessDate` value on API data changes after the `closeoutHour`.

Consider [daylight savings time](api_dates_and_timestamps.html#apiDaylightSavingsTime) when interacting with the closeout hour.

## Review menu and order structure

Reporting on sales depends on restaurants' usage of menu items and the overall structure of orders.

To understand Toast menu concepts before you begin development, review [menu hierarchy information](adminMenuHierarchy.html).

To review order structure, see [Orders API overview](portalOrdersApiOverview.html).

## Plan your display

The following table provides suggested information that you can display in different types of reports. For more information about the difference between orders, checks, menu item selections, and payments, see [Orders API overview](portalOrdersApiOverview.html).

| Report type | Object | Values | 
| --- | --- | --- |
| Order data | Orders | Consider displaying the following reporting information for orders:- Dining option name
- Dining option behavior
- Revenue center name
- Server name
- Service area name
- Table name
- Numbers of guests
- Order source
- Restaurant service name
- Opened date
- Modified date
- Paid date
- Closed date
- Voided status

 | 
| Checks | Consider displaying the following reporting information for checks:- Display number
- Tab name
- Total amount
- Tax amount
- Refunded amount
- Applied discount names
- Applied discount amounts
- Applied service charge names
- Applied service charge amounts

 | 
| Menu item selections | Consider displaying the following reporting information for menu item selections:- Menu item name - Use the `displayName`value on `Selection` object
- Applied modifier names - Modifiers may be nested arbitrarily deep on a menu item
- Price
- Applied tax rate names
- Applied tax values
- Applied discount names
- Applied discount amounts
- Sales category name
- Item tags - Retrieve from the menus API and cache this data

 | 
| Payments | Consider displaying the following reporting information for payments:- Amount
- Tip amount
- Refund information
- Type
- Card entry mode
- Payment status

 | 
| Cash transactions | Cash entries | Consider displaying the following reporting information for cash entries:- Cash entry type
- Cash entry date
- Amount
- Reason
- Cash drawer name
- Payout reason name
- No sale reason name
- Employee 1 name
- Employee 2 name
- Reversed cash transaction

 | 
| Deposits | Consider displaying the following reporting information for cash deposits:- Cash entry date
- Amount
- Employee name
- Reversed cash transaction

 | 
| Labor data | Time entries | Consider displaying the following reporting information for time entries:- Employee name
- Job name
- In date
- Out date
- Regular hours
- Overtime hours
- Declared cash tips
- Non-cash tips
- Break information: break type name, paid, in time, out time, missed
- Cash gratuity service charges
- Tips withheld
- Hourly wage
- Deleted

 | 

## Set up a recurring retrieval of transactional information

After you decide what to display in your reports, build a retrieval of transactional information. Below are recommendations for how to retrieve transactional data.

| Information type | Transactional information | Additional information | 
| --- | --- | --- |
| Orders | Retrieve all orders from the previous day using the `/ordersBulk` endpoint of the orders API.[More information](apiOrdersGetDetailedInfoAboutMultipleOrders.html)

> **Note**
> 
> Toast support recommends using the [orders updated webhook](devOrdersWebhookRef.html#apiOrdersWebhookOrderUpdated) to receive order updates as they occur instead of pulling order updates with the `/ordersBulk` endpoint. 


 | Use the `startDate` and `endDate` query parameters of the `/ordersBulk` endpoint to retrieve orders by their `modifiedDate` timestamp. | 
| Payments | Retrieve all payments from the previous day using the `/payments` endpoint of the orders API.[More information](apiAllPaymentsInRestaurants.html) | Use the `paidBusinessDate`, `voidBusinessDate`, and `refundBusinessDate`query parameters to retrieve all payment transactions from the previous business date.Retrieve payments at least six hours after the restaurant's `closeoutHour` in order to retrieve all credit card payments and fees from the previous day. | 
| Time entries | Retrieve all time entries from the previous day using the `/timeEntries` endpoint of the labor API.[More information](apiGettingTimeEntriesForEmployees.html) | Use the `modifiedStartDate` and `modifiedEndDate` query parameters of the `/timeEntries` endpoint to retrieve all time entries created or updated during the previous business day. | 
| Cash transactions | Retrieve all cash transactions from the previous business day using the `/deposits` and `/entries` endpoints of the cash management API.[More information](apiWorkingWithCashEntriesAndDeposits.html) | Use the cash management API to retrieve all cash transactions from the previous business day, such as when employees open the cash drawer, add cash to the cash drawer, and retrieve their day's tips in cash. | 

## Consider a one-time historical information backfill per location

Consider loading historical order information for each restaurant location one time when that location begins to use your integration.

Toast support recommends retrieving twelve weeks of historical data.

## Retrieve restaurant configuration information

Consider including the configuration information shown in the table below in your reporting integration. After deciding which configuration information you want to display, set up a daily poll to the [configuration API](https://doc.toasttab.com/openapi/configuration/overview/) and [menus API](https://doc.toasttab.com/openapi/menus/overview/) to retrieve it.

To reduce the amount of data that you receive when you poll the configuration API:

- Use the `lastModified` query parameter so that you only retrieve entities modified after the specified timestamp.


- Only retrieve a new menu when you determine that your existing menu is outdated. For more information about when to retrieve a new menu, see [Determining if a restaurant's menu data has gone stale](apiDeterminingIfYourMenuJsonIsOutdated_V2.html).



Consider including the following configuration in your analytics integration.

| Information type | Configuration | Additional information | 
| --- | --- | --- |
| Reporting categories | Revenue centers from the configuration API. [More information](https://doc.toasttab.com/openapi/configuration/operation/revenueCentersGet/)Sales categories from the configuration API. [More information](https://doc.toasttab.com/openapi/configuration/operation/salesCategoriesGet/) | See Toast Central for more information about [revenue centers](https://central.toasttab.com/s/article/Creating-and-Assigning-Revenue-Centers) and [sales categories](https://central.toasttab.com/s/article/Sales-Categories-1492812477858). | 
| Order configuration | Alternative payment types from the configuration API. [More information](https://doc.toasttab.com/openapi/configuration/operation/alternatePaymentTypesGet/)Dining options from the configuration API. [More information](https://doc.toasttab.com/openapi/configuration/operation/diningOptionsGet/)Discounts from the configuration API. [More information](https://doc.toasttab.com/openapi/configuration/operation/discountsGet/)Service charges from the configuration API. [More information](https://doc.toasttab.com/openapi/configuration/operation/serviceChargesGet/)Tax rates from the configuration API. [More information](https://doc.toasttab.com/openapi/configuration/operation/taxRatesGet/) | These pieces of configuration are often associated with orders.They describe how the order was placed and how its price was calculated. | 
| Menu information | Menu information, such as menu group names, menu item names, and item tags from the menus API. [More information](apiGettingMenuInformationFromTheMenusAPI.html) | The menus API returns menu item names and other menu-related information you may want to display in your reporting platform. | 
| Restaurant information | Restaurant services from the configuration API. [More information](https://doc.toasttab.com/openapi/configuration/operation/restaurantServicesGet/)Service areas from the configuration API. [More information](https://doc.toasttab.com/openapi/configuration/operation/serviceAreasGet/)Tables from the configuration API. [More information](https://doc.toasttab.com/openapi/configuration/operation/tablesGet/) | This restaurant information allows your integration to report on when and where orders were placed in your restaurant.See Toast Central for more information about [hours and services](https://central.toasttab.com/s/article/Setup-Restaurant-Hours-and-Services) and [service areas and tables](https://central.toasttab.com/s/article/Creating-Service-Areas-and-Table-Setup-1493049150430). | 
| Cash configuration | Cash drawers from the configuration API. [More information](https://doc.toasttab.com/openapi/configuration/operation/cashDrawersGet/)No sale reasons from the configuration API. [More information](https://doc.toasttab.com/openapi/configuration/operation/noSaleReasonsGet/)Payout reasons from the configuration API. [More information](https://doc.toasttab.com/openapi/configuration/operation/payoutReasonsGet/)Void reasons from the configuration API. [More information](https://doc.toasttab.com/openapi/configuration/operation/voidReasonsGet/) | Cash configuration allows you to display metadata about the cash transactions at a restaurant.For more information about working with cash entries, see [Cash management overview](apiWorkingWithCashEntriesAndDeposits.html). | 
| Labor configuration | Break types from the configuration API. [More information](https://doc.toasttab.com/openapi/configuration/operation/breakTypesGet/)Employees from the labor API. [More information](api_get_all_employees.html)Jobs from the labor API. [More information](https://doc.toasttab.com/openapi/labor/operation/jobsGet/) | This labor information allows you to display information about restaurant employees, the jobs they do, and the breaks they take. | 

## Add additional business logic

Consider suppressing voided orders and deleted time entries from your reports by default. Allow users to actively choose to display these transactions.

Use the `voided` value on an `Order` object to determine whether an order was voided.

Use the `deleted` value on `TimeEntry` objects to determine whether a time entry was deleted.

## Build your data warehouse display and summaries

After you build a basic data warehouse display of transactional data, consider summarizing Toast information in any of the following ways:



****Order data****
: - Total sales value


- Total number of orders


- Total sales per dining option behavior


- Total sales per revenue center


- Total sales per sales category


- Total sales per item tag


- Total sales per service period (such as lunch or dinner)


- Total amount discounted from all orders


- Total amount discounted as a percentage of total sales


- Number of voided orders


- Number of voided orders as a percentage of all orders





****Labor data****
: - Number of total labor hours


- Total spent on labor


- Missed breaks





****Cash data****
: - Cash transactions by type


- Cash drawer value







