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

This document describes how to build a general data warehouse. For more detailed information about how to report on specific types of data, see [Building a sales report](devCookbook-apiIntegrationChecklistAccounting) and [Building labor reports](devCookbook-apiIntegrationChecklistPayroll).

## Required scopes

To follow these instructions, you must have the following [scopes](apiDevGuide-apiScopes):

- `cashmgmt:read`


- `config:read`


- `labor.employees:read`


- `labor:read`


- `menus:read`


- `restaurants:read`


- `orders:read`



## Complete initial integration setup

Review and implement the instructions in [How to build a Toast integration](devCookbook-apiIntegrationChecklistGeneral).

## Determine closeout hour

The `closeoutHour` value in the `General`object returned by the [restaurants API](apiDevGuide-apiRestaurantInformation) contains the restaurant's closeout hour.

The default closeout hour is 4:00 a.m. local time unless a Toast employee changes this setting. The `businessDate` value on API data changes after the `closeoutHour`.

Consider [daylight savings time](apiDevGuide-api_dates_and_timestamps#apiDaylightSavingsTime) when interacting with the closeout hour.

## Review menu and order structure

Reporting on sales depends on restaurants' usage of menu items and the overall structure of orders.

To understand Toast menu concepts before you begin development, review [menu hierarchy information](adminGuide-adminMenuHierarchy).

To review order structure, see [Orders API overview](apiDevGuide-portalOrdersApiOverview).

## Plan your display

The following table provides suggested information that you can display in different types of reports. For more information about the difference between orders, checks, menu item selections, and payments, see [Orders API overview](apiDevGuide-portalOrdersApiOverview).


<table>
  <thead>
    <tr>
      <th>Report type</th>
      <th>Object</th>
      <th>Values</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Order data</td>
      <td>Orders</td>
      <td>Consider displaying the following reporting information for orders:<ul><li>Dining option name</li><li>Dining option behavior</li><li>Revenue center name</li><li>Server name</li><li>Service area name</li><li>Table name</li><li>Numbers of guests</li><li>Order source</li><li>Restaurant service name</li><li>Opened date</li><li>Modified date</li><li>Paid date</li><li>Closed date</li><li>Voided status</li></ul></td>
    </tr>
    <tr>
      <td>Checks</td>
      <td>Consider displaying the following reporting information for checks:<ul><li>Display number</li><li>Tab name</li><li>Total amount</li><li>Tax amount</li><li>Refunded amount</li><li>Applied discount names</li><li>Applied discount amounts</li><li>Applied service charge names</li><li>Applied service charge amounts</li></ul></td>
    </tr>
    <tr>
      <td>Menu item selections</td>
      <td>Consider displaying the following reporting information for menu item selections:<ul><li>Menu item name - Use the <code>displayName</code> value on <code>Selection</code> object</li><li>Applied modifier names - Modifiers may be nested arbitrarily deep on a menu item</li><li>Price</li><li>Applied tax rate names</li><li>Applied tax values</li><li>Applied discount names</li><li>Applied discount amounts</li><li>Sales category name</li><li>Item tags - Retrieve from the menus API and cache this data</li></ul></td>
    </tr>
    <tr>
      <td>Payments</td>
      <td>Consider displaying the following reporting information for payments:<ul><li>Amount</li><li>Tip amount</li><li>Refund information</li><li>Type</li><li>Card entry mode</li><li>Payment status</li></ul></td>
    </tr>
    <tr>
      <td>Cash transactions</td>
      <td>Cash entries</td>
      <td>Consider displaying the following reporting information for cash entries:<ul><li>Cash entry type</li><li>Cash entry date</li><li>Amount</li><li>Reason</li><li>Cash drawer name</li><li>Payout reason name</li><li>No sale reason name</li><li>Employee 1 name</li><li>Employee 2 name</li><li>Reversed cash transaction</li></ul></td>
    </tr>
    <tr>
      <td>Deposits</td>
      <td>Consider displaying the following reporting information for cash deposits:<ul><li>Cash entry date</li><li>Amount</li><li>Employee name</li><li>Reversed cash transaction</li></ul></td>
    </tr>
    <tr>
      <td>Labor data</td>
      <td>Time entries</td>
      <td>Consider displaying the following reporting information for time entries:<ul><li>Employee name</li><li>Job name</li><li>In date</li><li>Out date</li><li>Regular hours</li><li>Overtime hours</li><li>Declared cash tips</li><li>Non-cash tips</li><li>Break information: break type name, paid, in time, out time, missed</li><li>Cash gratuity service charges</li><li>Tips withheld</li><li>Hourly wage</li><li>Deleted</li></ul></td>
    </tr>
  </tbody>
</table>

## Set up a recurring retrieval of transactional information

After you decide what to display in your reports, build a retrieval of transactional information. Below are recommendations for how to retrieve transactional data.


<table>
  <thead>
    <tr>
      <th>Information type</th>
      <th>Transactional information</th>
      <th>Additional information</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Orders</td>
      <td>Retrieve all orders from the previous day using the <code>/ordersBulk</code> endpoint of the orders API. <br/> <a href="apiDevGuide-apiOrdersGetDetailedInfoAboutMultipleOrders">More information</a> <blockquote><strong>Note</strong> Toast support recommends using the <a href="apiDevGuide-devOrdersWebhookRef#apiOrdersWebhookOrderUpdated">orders updated webhook</a> to receive order updates as they occur instead of pulling order updates with the <code>/ordersBulk</code> endpoint. </blockquote> </td>
      <td>Use the <code>startDate</code> and <code>endDate</code> query parameters of the <code>/ordersBulk</code> endpoint to retrieve orders by their <code>modifiedDate</code> timestamp.</td>
    </tr>
    <tr>
      <td>Payments</td>
      <td>Retrieve all payments from the previous day using the <code>/payments</code> endpoint of the orders API. <br/> <a href="apiDevGuide-apiAllPaymentsInRestaurants">More information</a></td>
      <td>Use the <code>paidBusinessDate</code>, <code>voidBusinessDate</code>, and <code>refundBusinessDate</code> query parameters to retrieve all payment transactions from the previous business date. <br/> Retrieve payments at least six hours after the restaurant's <code>closeoutHour</code> in order to retrieve all credit card payments and fees from the previous day.</td>
    </tr>
    <tr>
      <td>Time entries</td>
      <td>Retrieve all time entries from the previous day using the <code>/timeEntries</code> endpoint of the labor API. <br/> <a href="apiDevGuide-apiGettingTimeEntriesForEmployees">More information</a></td>
      <td>Use the <code>modifiedStartDate</code> and <code>modifiedEndDate</code> query parameters of the <code>/timeEntries</code> endpoint to retrieve all time entries created or updated during the previous business day.</td>
    </tr>
    <tr>
      <td>Cash transactions</td>
      <td>Retrieve all cash transactions from the previous business day using the <code>/deposits</code> and <code>/entries</code> endpoints of the cash management API. <br/> <a href="apiDevGuide-apiWorkingWithCashEntriesAndDeposits">More information</a></td>
      <td>Use the cash management API to retrieve all cash transactions from the previous business day, such as when employees open the cash drawer, add cash to the cash drawer, and retrieve their day's tips in cash.</td>
    </tr>
  </tbody>
</table>

## Consider a one-time historical information backfill per location

Consider loading historical order information for each restaurant location one time when that location begins to use your integration.

Toast support recommends retrieving twelve weeks of historical data.

## Retrieve restaurant configuration information

Consider including the configuration information shown in the table below in your reporting integration. After deciding which configuration information you want to display, set up a daily poll to the [configuration API](https://doc.toasttab.com/openapi/configuration/overview/) and [menus API](https://doc.toasttab.com/openapi/menus/overview/) to retrieve it.

To reduce the amount of data that you receive when you poll the configuration API:

- Use the `lastModified` query parameter so that you only retrieve entities modified after the specified timestamp.


- Only retrieve a new menu when you determine that your existing menu is outdated. For more information about when to retrieve a new menu, see [Determining if a restaurant's menu data has gone stale](apiDevGuide-apiDeterminingIfYourMenuJsonIsOutdated_V2).



Consider including the following configuration in your analytics integration.


<table>
  <thead>
    <tr>
      <th>Information type</th>
      <th>Configuration</th>
      <th>Additional information</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Reporting categories</td>
      <td>Revenue centers from the configuration API. <a href="https://doc.toasttab.com/openapi/configuration/operation/revenueCentersGet/">More information</a> <br/> Sales categories from the configuration API. <a href="https://doc.toasttab.com/openapi/configuration/operation/salesCategoriesGet/">More information</a></td>
      <td>See Toast Central for more information about <a href="https://central.toasttab.com/s/article/Creating-and-Assigning-Revenue-Centers">revenue centers</a> and <a href="https://central.toasttab.com/s/article/Sales-Categories-1492812477858">sales categories</a>.</td>
    </tr>
    <tr>
      <td>Order configuration</td>
      <td>Alternative payment types from the configuration API. <a href="https://doc.toasttab.com/openapi/configuration/operation/alternatePaymentTypesGet/">More information</a> <br/> Dining options from the configuration API. <a href="https://doc.toasttab.com/openapi/configuration/operation/diningOptionsGet/">More information</a> <br/> Discounts from the configuration API. <a href="https://doc.toasttab.com/openapi/configuration/operation/discountsGet/">More information</a> <br/> Service charges from the configuration API. <a href="https://doc.toasttab.com/openapi/configuration/operation/serviceChargesGet/">More information</a> <br/> Tax rates from the configuration API. <a href="https://doc.toasttab.com/openapi/configuration/operation/taxRatesGet/">More information</a></td>
      <td>These pieces of configuration are often associated with orders. <br/> They describe how the order was placed and how its price was calculated.</td>
    </tr>
    <tr>
      <td>Menu information</td>
      <td>Menu information, such as menu group names, menu item names, and item tags from the menus API.  <br/> <a href="apiDevGuide-apiGettingMenuInformationFromTheMenusAPI">More information</a></td>
      <td>The menus API returns menu item names and other menu-related information you may want to display in your reporting platform.</td>
    </tr>
    <tr>
      <td>Restaurant information</td>
      <td>Restaurant services from the configuration API. <a href="https://doc.toasttab.com/openapi/configuration/operation/restaurantServicesGet/">More information</a> <br/> Service areas from the configuration API. <a href="https://doc.toasttab.com/openapi/configuration/operation/serviceAreasGet/">More information</a> <br/> Tables from the configuration API. <a href="https://doc.toasttab.com/openapi/configuration/operation/tablesGet/">More information</a></td>
      <td>This restaurant information allows your integration to report on when and where orders were placed in your restaurant. <br/> See Toast Central for more information about <a href="https://central.toasttab.com/s/article/Setup-Restaurant-Hours-and-Services">hours and services</a> and <a href="https://central.toasttab.com/s/article/Creating-Service-Areas-and-Table-Setup-1493049150430">service areas and tables</a>.</td>
    </tr>
    <tr>
      <td>Cash configuration</td>
      <td>Cash drawers from the configuration API. <a href="https://doc.toasttab.com/openapi/configuration/operation/cashDrawersGet/">More information</a> <br/> No sale reasons from the configuration API. <a href="https://doc.toasttab.com/openapi/configuration/operation/noSaleReasonsGet/">More information</a> <br/> Payout reasons from the configuration API. <a href="https://doc.toasttab.com/openapi/configuration/operation/payoutReasonsGet/">More information</a> <br/> Void reasons from the configuration API. <a href="https://doc.toasttab.com/openapi/configuration/operation/voidReasonsGet/">More information</a></td>
      <td>Cash configuration allows you to display metadata about the cash transactions at a restaurant. <br/> For more information about working with cash entries, see <a href="apiDevGuide-apiWorkingWithCashEntriesAndDeposits">Cash management overview</a>.</td>
    </tr>
    <tr>
      <td>Labor configuration</td>
      <td>Break types from the configuration API. <a href="https://doc.toasttab.com/openapi/configuration/operation/breakTypesGet/">More information</a> <br/> Employees from the labor API. <a href="apiDevGuide-api_get_all_employees">More information</a> <br/> Jobs from the labor API. <a href="https://doc.toasttab.com/openapi/labor/operation/jobsGet/">More information</a></td>
      <td>This labor information allows you to display information about restaurant employees, the jobs they do, and the breaks they take.</td>
    </tr>
  </tbody>
</table>

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







