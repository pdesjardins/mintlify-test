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


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className=""><div className=""><p className="text-base leading-relaxed">Report type</p></div></th>
      <th className=""><div className=""><p className="text-base leading-relaxed">Object</p></div></th>
      <th className=""><div className=""><p className="text-base leading-relaxed">Values</p></div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Order data</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Orders</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Consider displaying the following reporting information for orders:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">Dining option name</p></li><li className=""><p className="text-base leading-relaxed">Dining option behavior</p></li><li className=""><p className="text-base leading-relaxed">Revenue center name</p></li><li className=""><p className="text-base leading-relaxed">Server name</p></li><li className=""><p className="text-base leading-relaxed">Service area name</p></li><li className=""><p className="text-base leading-relaxed">Table name</p></li><li className=""><p className="text-base leading-relaxed">Numbers of guests</p></li><li className=""><p className="text-base leading-relaxed">Order source</p></li><li className=""><p className="text-base leading-relaxed">Restaurant service name</p></li><li className=""><p className="text-base leading-relaxed">Opened date</p></li><li className=""><p className="text-base leading-relaxed">Modified date</p></li><li className=""><p className="text-base leading-relaxed">Paid date</p></li><li className=""><p className="text-base leading-relaxed">Closed date</p></li><li className=""><p className="text-base leading-relaxed">Voided status</p></li></ul></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Checks</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Consider displaying the following reporting information for checks:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">Display number</p></li><li className=""><p className="text-base leading-relaxed">Tab name</p></li><li className=""><p className="text-base leading-relaxed">Total amount</p></li><li className=""><p className="text-base leading-relaxed">Tax amount</p></li><li className=""><p className="text-base leading-relaxed">Refunded amount</p></li><li className=""><p className="text-base leading-relaxed">Applied discount names</p></li><li className=""><p className="text-base leading-relaxed">Applied discount amounts</p></li><li className=""><p className="text-base leading-relaxed">Applied service charge names</p></li><li className=""><p className="text-base leading-relaxed">Applied service charge amounts</p></li></ul></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Menu item selections</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Consider displaying the following reporting information for menu item selections:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">Menu item name - Use the <code className="font-mono text-sm">displayName</code> value on <code className="font-mono text-sm">Selection</code> object</p></li><li className=""><p className="text-base leading-relaxed">Applied modifier names - Modifiers may be nested arbitrarily deep on a menu item</p></li><li className=""><p className="text-base leading-relaxed">Price</p></li><li className=""><p className="text-base leading-relaxed">Applied tax rate names</p></li><li className=""><p className="text-base leading-relaxed">Applied tax values</p></li><li className=""><p className="text-base leading-relaxed">Applied discount names</p></li><li className=""><p className="text-base leading-relaxed">Applied discount amounts</p></li><li className=""><p className="text-base leading-relaxed">Sales category name</p></li><li className=""><p className="text-base leading-relaxed">Item tags - Retrieve from the menus API and cache this data</p></li></ul></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Payments</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Consider displaying the following reporting information for payments:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">Amount</p></li><li className=""><p className="text-base leading-relaxed">Tip amount</p></li><li className=""><p className="text-base leading-relaxed">Refund information</p></li><li className=""><p className="text-base leading-relaxed">Type</p></li><li className=""><p className="text-base leading-relaxed">Card entry mode</p></li><li className=""><p className="text-base leading-relaxed">Payment status</p></li></ul></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Cash transactions</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Cash entries</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Consider displaying the following reporting information for cash entries:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">Cash entry type</p></li><li className=""><p className="text-base leading-relaxed">Cash entry date</p></li><li className=""><p className="text-base leading-relaxed">Amount</p></li><li className=""><p className="text-base leading-relaxed">Reason</p></li><li className=""><p className="text-base leading-relaxed">Cash drawer name</p></li><li className=""><p className="text-base leading-relaxed">Payout reason name</p></li><li className=""><p className="text-base leading-relaxed">No sale reason name</p></li><li className=""><p className="text-base leading-relaxed">Employee 1 name</p></li><li className=""><p className="text-base leading-relaxed">Employee 2 name</p></li><li className=""><p className="text-base leading-relaxed">Reversed cash transaction</p></li></ul></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Deposits</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Consider displaying the following reporting information for cash deposits:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">Cash entry date</p></li><li className=""><p className="text-base leading-relaxed">Amount</p></li><li className=""><p className="text-base leading-relaxed">Employee name</p></li><li className=""><p className="text-base leading-relaxed">Reversed cash transaction</p></li></ul></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Labor data</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Time entries</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Consider displaying the following reporting information for time entries:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">Employee name</p></li><li className=""><p className="text-base leading-relaxed">Job name</p></li><li className=""><p className="text-base leading-relaxed">In date</p></li><li className=""><p className="text-base leading-relaxed">Out date</p></li><li className=""><p className="text-base leading-relaxed">Regular hours</p></li><li className=""><p className="text-base leading-relaxed">Overtime hours</p></li><li className=""><p className="text-base leading-relaxed">Declared cash tips</p></li><li className=""><p className="text-base leading-relaxed">Non-cash tips</p></li><li className=""><p className="text-base leading-relaxed">Break information: break type name, paid, in time, out time, missed</p></li><li className=""><p className="text-base leading-relaxed">Cash gratuity service charges</p></li><li className=""><p className="text-base leading-relaxed">Tips withheld</p></li><li className=""><p className="text-base leading-relaxed">Hourly wage</p></li><li className=""><p className="text-base leading-relaxed">Deleted</p></li></ul></div></td>
    </tr>
  </tbody>
</table>
</div>

## Set up a recurring retrieval of transactional information

After you decide what to display in your reports, build a retrieval of transactional information. Below are recommendations for how to retrieve transactional data.


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className=""><div className=""><p className="text-base leading-relaxed">Information type</p></div></th>
      <th className=""><div className=""><p className="text-base leading-relaxed">Transactional information</p></div></th>
      <th className=""><div className=""><p className="text-base leading-relaxed">Additional information</p></div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Orders</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed italic">[Complex content with notes omitted - see <a href="https://doc.toasttab.com/platformguide/" className="underline">current documentation</a>]</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Use the <code className="font-mono text-sm">startDate</code> and <code className="font-mono text-sm">endDate</code> query parameters of the <code className="font-mono text-sm">/ordersBulk</code> endpoint to retrieve orders by their <code className="font-mono text-sm">modifiedDate</code> timestamp.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Payments</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Retrieve all payments from the previous day using the <code className="font-mono text-sm">/payments</code> endpoint of the orders API.</p> <p className="text-base leading-relaxed"><a href="apiDevGuide-apiAllPaymentsInRestaurants" className="">More information</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Use the <code className="font-mono text-sm">paidBusinessDate</code>, <code className="font-mono text-sm">voidBusinessDate</code>, and <code className="font-mono text-sm">refundBusinessDate</code> query parameters to retrieve all payment transactions from the previous business date.</p> <p className="text-base leading-relaxed">Retrieve payments at least six hours after the restaurant's <code className="font-mono text-sm">closeoutHour</code> in order to retrieve all credit card payments and fees from the previous day.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Time entries</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Retrieve all time entries from the previous day using the <code className="font-mono text-sm">/timeEntries</code> endpoint of the labor API.</p> <p className="text-base leading-relaxed"><a href="apiDevGuide-apiGettingTimeEntriesForEmployees" className="">More information</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Use the <code className="font-mono text-sm">modifiedStartDate</code> and <code className="font-mono text-sm">modifiedEndDate</code> query parameters of the <code className="font-mono text-sm">/timeEntries</code> endpoint to retrieve all time entries created or updated during the previous business day.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Cash transactions</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Retrieve all cash transactions from the previous business day using the <code className="font-mono text-sm">/deposits</code> and <code className="font-mono text-sm">/entries</code> endpoints of the cash management API.</p> <p className="text-base leading-relaxed"><a href="apiDevGuide-apiWorkingWithCashEntriesAndDeposits" className="">More information</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Use the cash management API to retrieve all cash transactions from the previous business day, such as when employees open the cash drawer, add cash to the cash drawer, and retrieve their day's tips in cash.</p></div></td>
    </tr>
  </tbody>
</table>
</div>

## Consider a one-time historical information backfill per location

Consider loading historical order information for each restaurant location one time when that location begins to use your integration.

Toast support recommends retrieving twelve weeks of historical data.

## Retrieve restaurant configuration information

Consider including the configuration information shown in the table below in your reporting integration. After deciding which configuration information you want to display, set up a daily poll to the [configuration API](https://doc.toasttab.com/openapi/configuration/overview/) and [menus API](https://doc.toasttab.com/openapi/menus/overview/) to retrieve it.

To reduce the amount of data that you receive when you poll the configuration API:

- Use the `lastModified` query parameter so that you only retrieve entities modified after the specified timestamp.


- Only retrieve a new menu when you determine that your existing menu is outdated. For more information about when to retrieve a new menu, see [Determining if a restaurant's menu data has gone stale](apiDevGuide-apiDeterminingIfYourMenuJsonIsOutdated_V2).



Consider including the following configuration in your analytics integration.


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className=""><div className=""><p className="text-base leading-relaxed">Information type</p></div></th>
      <th className=""><div className=""><p className="text-base leading-relaxed">Configuration</p></div></th>
      <th className=""><div className=""><p className="text-base leading-relaxed">Additional information</p></div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Reporting categories</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Revenue centers from the configuration API. <a href="https://doc.toasttab.com/openapi/configuration/operation/revenueCentersGet/" className="">More information</a></p> <p className="text-base leading-relaxed">Sales categories from the configuration API. <a href="https://doc.toasttab.com/openapi/configuration/operation/salesCategoriesGet/" className="">More information</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">See Toast Central for more information about <a href="https://central.toasttab.com/s/article/Creating-and-Assigning-Revenue-Centers" className="">revenue centers</a> and <a href="https://central.toasttab.com/s/article/Sales-Categories-1492812477858" className="">sales categories</a>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Order configuration</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Alternative payment types from the configuration API. <a href="https://doc.toasttab.com/openapi/configuration/operation/alternatePaymentTypesGet/" className="">More information</a></p> <p className="text-base leading-relaxed">Dining options from the configuration API. <a href="https://doc.toasttab.com/openapi/configuration/operation/diningOptionsGet/" className="">More information</a></p> <p className="text-base leading-relaxed">Discounts from the configuration API. <a href="https://doc.toasttab.com/openapi/configuration/operation/discountsGet/" className="">More information</a></p> <p className="text-base leading-relaxed">Service charges from the configuration API. <a href="https://doc.toasttab.com/openapi/configuration/operation/serviceChargesGet/" className="">More information</a></p> <p className="text-base leading-relaxed">Tax rates from the configuration API. <a href="https://doc.toasttab.com/openapi/configuration/operation/taxRatesGet/" className="">More information</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">These pieces of configuration are often associated with orders.</p> <p className="text-base leading-relaxed">They describe how the order was placed and how its price was calculated.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Menu information</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Menu information, such as menu group names, menu item names, and item tags from the menus API. </p> <p className="text-base leading-relaxed"><a href="apiDevGuide-apiGettingMenuInformationFromTheMenusAPI" className="">More information</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The menus API returns menu item names and other menu-related information you may want to display in your reporting platform.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Restaurant information</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Restaurant services from the configuration API. <a href="https://doc.toasttab.com/openapi/configuration/operation/restaurantServicesGet/" className="">More information</a></p> <p className="text-base leading-relaxed">Service areas from the configuration API. <a href="https://doc.toasttab.com/openapi/configuration/operation/serviceAreasGet/" className="">More information</a></p> <p className="text-base leading-relaxed">Tables from the configuration API. <a href="https://doc.toasttab.com/openapi/configuration/operation/tablesGet/" className="">More information</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">This restaurant information allows your integration to report on when and where orders were placed in your restaurant.</p> <p className="text-base leading-relaxed">See Toast Central for more information about <a href="https://central.toasttab.com/s/article/Setup-Restaurant-Hours-and-Services" className="">hours and services</a> and <a href="https://central.toasttab.com/s/article/Creating-Service-Areas-and-Table-Setup-1493049150430" className="">service areas and tables</a>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Cash configuration</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Cash drawers from the configuration API. <a href="https://doc.toasttab.com/openapi/configuration/operation/cashDrawersGet/" className="">More information</a></p> <p className="text-base leading-relaxed">No sale reasons from the configuration API. <a href="https://doc.toasttab.com/openapi/configuration/operation/noSaleReasonsGet/" className="">More information</a></p> <p className="text-base leading-relaxed">Payout reasons from the configuration API. <a href="https://doc.toasttab.com/openapi/configuration/operation/payoutReasonsGet/" className="">More information</a></p> <p className="text-base leading-relaxed">Void reasons from the configuration API. <a href="https://doc.toasttab.com/openapi/configuration/operation/voidReasonsGet/" className="">More information</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Cash configuration allows you to display metadata about the cash transactions at a restaurant.</p> <p className="text-base leading-relaxed">For more information about working with cash entries, see <a href="apiDevGuide-apiWorkingWithCashEntriesAndDeposits" className="">Cash management overview</a>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Labor configuration</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Break types from the configuration API. <a href="https://doc.toasttab.com/openapi/configuration/operation/breakTypesGet/" className="">More information</a></p> <p className="text-base leading-relaxed">Employees from the labor API. <a href="apiDevGuide-api_get_all_employees" className="">More information</a></p> <p className="text-base leading-relaxed">Jobs from the labor API. <a href="https://doc.toasttab.com/openapi/labor/operation/jobsGet/" className="">More information</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">This labor information allows you to display information about restaurant employees, the jobs they do, and the breaks they take.</p></div></td>
    </tr>
  </tbody>
</table>
</div>

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







