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
      <th className=""><div className="">Report type</div></th>
      <th className=""><div className="">Object</div></th>
      <th className=""><div className="">Values</div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className=""><div className="">Order data</div></td>
      <td className=""><div className="">Orders</div></td>
      <td className=""><div className="">Consider displaying the following reporting information for orders:<ul className=""><li className="">Dining option name</li><li className="">Dining option behavior</li><li className="">Revenue center name</li><li className="">Server name</li><li className="">Service area name</li><li className="">Table name</li><li className="">Numbers of guests</li><li className="">Order source</li><li className="">Restaurant service name</li><li className="">Opened date</li><li className="">Modified date</li><li className="">Paid date</li><li className="">Closed date</li><li className="">Voided status</li></ul></div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Checks</div></td>
      <td className=""><div className="">Consider displaying the following reporting information for checks:<ul className=""><li className="">Display number</li><li className="">Tab name</li><li className="">Total amount</li><li className="">Tax amount</li><li className="">Refunded amount</li><li className="">Applied discount names</li><li className="">Applied discount amounts</li><li className="">Applied service charge names</li><li className="">Applied service charge amounts</li></ul></div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Menu item selections</div></td>
      <td className=""><div className="">Consider displaying the following reporting information for menu item selections:<ul className=""><li className="">Menu item name - Use the <code className="">displayName</code> value on <code className="">Selection</code> object</li><li className="">Applied modifier names - Modifiers may be nested arbitrarily deep on a menu item</li><li className="">Price</li><li className="">Applied tax rate names</li><li className="">Applied tax values</li><li className="">Applied discount names</li><li className="">Applied discount amounts</li><li className="">Sales category name</li><li className="">Item tags - Retrieve from the menus API and cache this data</li></ul></div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Payments</div></td>
      <td className=""><div className="">Consider displaying the following reporting information for payments:<ul className=""><li className="">Amount</li><li className="">Tip amount</li><li className="">Refund information</li><li className="">Type</li><li className="">Card entry mode</li><li className="">Payment status</li></ul></div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Cash transactions</div></td>
      <td className=""><div className="">Cash entries</div></td>
      <td className=""><div className="">Consider displaying the following reporting information for cash entries:<ul className=""><li className="">Cash entry type</li><li className="">Cash entry date</li><li className="">Amount</li><li className="">Reason</li><li className="">Cash drawer name</li><li className="">Payout reason name</li><li className="">No sale reason name</li><li className="">Employee 1 name</li><li className="">Employee 2 name</li><li className="">Reversed cash transaction</li></ul></div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Deposits</div></td>
      <td className=""><div className="">Consider displaying the following reporting information for cash deposits:<ul className=""><li className="">Cash entry date</li><li className="">Amount</li><li className="">Employee name</li><li className="">Reversed cash transaction</li></ul></div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Labor data</div></td>
      <td className=""><div className="">Time entries</div></td>
      <td className=""><div className="">Consider displaying the following reporting information for time entries:<ul className=""><li className="">Employee name</li><li className="">Job name</li><li className="">In date</li><li className="">Out date</li><li className="">Regular hours</li><li className="">Overtime hours</li><li className="">Declared cash tips</li><li className="">Non-cash tips</li><li className="">Break information: break type name, paid, in time, out time, missed</li><li className="">Cash gratuity service charges</li><li className="">Tips withheld</li><li className="">Hourly wage</li><li className="">Deleted</li></ul></div></td>
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
      <th className=""><div className="">Information type</div></th>
      <th className=""><div className="">Transactional information</div></th>
      <th className=""><div className="">Additional information</div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className=""><div className="">Orders</div></td>
      <td className=""><div className="">Retrieve all orders from the previous day using the <code className="">/ordersBulk</code> endpoint of the orders API. <br/> <a href="apiDevGuide-apiOrdersGetDetailedInfoAboutMultipleOrders" className="">More information</a> <blockquote><strong>Note</strong> Toast support recommends using the <a href="apiDevGuide-devOrdersWebhookRef#apiOrdersWebhookOrderUpdated" className="">orders updated webhook</a> to receive order updates as they occur instead of pulling order updates with the <code className="">/ordersBulk</code> endpoint. </blockquote> </div></td>
      <td className=""><div className="">Use the <code className="">startDate</code> and <code className="">endDate</code> query parameters of the <code className="">/ordersBulk</code> endpoint to retrieve orders by their <code className="">modifiedDate</code> timestamp.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Payments</div></td>
      <td className=""><div className="">Retrieve all payments from the previous day using the <code className="">/payments</code> endpoint of the orders API. <br/> <a href="apiDevGuide-apiAllPaymentsInRestaurants" className="">More information</a></div></td>
      <td className=""><div className="">Use the <code className="">paidBusinessDate</code>, <code className="">voidBusinessDate</code>, and <code className="">refundBusinessDate</code> query parameters to retrieve all payment transactions from the previous business date. <br/> Retrieve payments at least six hours after the restaurant's <code className="">closeoutHour</code> in order to retrieve all credit card payments and fees from the previous day.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Time entries</div></td>
      <td className=""><div className="">Retrieve all time entries from the previous day using the <code className="">/timeEntries</code> endpoint of the labor API. <br/> <a href="apiDevGuide-apiGettingTimeEntriesForEmployees" className="">More information</a></div></td>
      <td className=""><div className="">Use the <code className="">modifiedStartDate</code> and <code className="">modifiedEndDate</code> query parameters of the <code className="">/timeEntries</code> endpoint to retrieve all time entries created or updated during the previous business day.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Cash transactions</div></td>
      <td className=""><div className="">Retrieve all cash transactions from the previous business day using the <code className="">/deposits</code> and <code className="">/entries</code> endpoints of the cash management API. <br/> <a href="apiDevGuide-apiWorkingWithCashEntriesAndDeposits" className="">More information</a></div></td>
      <td className=""><div className="">Use the cash management API to retrieve all cash transactions from the previous business day, such as when employees open the cash drawer, add cash to the cash drawer, and retrieve their day's tips in cash.</div></td>
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
      <th className=""><div className="">Information type</div></th>
      <th className=""><div className="">Configuration</div></th>
      <th className=""><div className="">Additional information</div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className=""><div className="">Reporting categories</div></td>
      <td className=""><div className="">Revenue centers from the configuration API. <a href="https://doc.toasttab.com/openapi/configuration/operation/revenueCentersGet/" className="">More information</a> <br/> Sales categories from the configuration API. <a href="https://doc.toasttab.com/openapi/configuration/operation/salesCategoriesGet/" className="">More information</a></div></td>
      <td className=""><div className="">See Toast Central for more information about <a href="https://central.toasttab.com/s/article/Creating-and-Assigning-Revenue-Centers" className="">revenue centers</a> and <a href="https://central.toasttab.com/s/article/Sales-Categories-1492812477858" className="">sales categories</a>.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Order configuration</div></td>
      <td className=""><div className="">Alternative payment types from the configuration API. <a href="https://doc.toasttab.com/openapi/configuration/operation/alternatePaymentTypesGet/" className="">More information</a> <br/> Dining options from the configuration API. <a href="https://doc.toasttab.com/openapi/configuration/operation/diningOptionsGet/" className="">More information</a> <br/> Discounts from the configuration API. <a href="https://doc.toasttab.com/openapi/configuration/operation/discountsGet/" className="">More information</a> <br/> Service charges from the configuration API. <a href="https://doc.toasttab.com/openapi/configuration/operation/serviceChargesGet/" className="">More information</a> <br/> Tax rates from the configuration API. <a href="https://doc.toasttab.com/openapi/configuration/operation/taxRatesGet/" className="">More information</a></div></td>
      <td className=""><div className="">These pieces of configuration are often associated with orders. <br/> They describe how the order was placed and how its price was calculated.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Menu information</div></td>
      <td className=""><div className="">Menu information, such as menu group names, menu item names, and item tags from the menus API.  <br/> <a href="apiDevGuide-apiGettingMenuInformationFromTheMenusAPI" className="">More information</a></div></td>
      <td className=""><div className="">The menus API returns menu item names and other menu-related information you may want to display in your reporting platform.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Restaurant information</div></td>
      <td className=""><div className="">Restaurant services from the configuration API. <a href="https://doc.toasttab.com/openapi/configuration/operation/restaurantServicesGet/" className="">More information</a> <br/> Service areas from the configuration API. <a href="https://doc.toasttab.com/openapi/configuration/operation/serviceAreasGet/" className="">More information</a> <br/> Tables from the configuration API. <a href="https://doc.toasttab.com/openapi/configuration/operation/tablesGet/" className="">More information</a></div></td>
      <td className=""><div className="">This restaurant information allows your integration to report on when and where orders were placed in your restaurant. <br/> See Toast Central for more information about <a href="https://central.toasttab.com/s/article/Setup-Restaurant-Hours-and-Services" className="">hours and services</a> and <a href="https://central.toasttab.com/s/article/Creating-Service-Areas-and-Table-Setup-1493049150430" className="">service areas and tables</a>.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Cash configuration</div></td>
      <td className=""><div className="">Cash drawers from the configuration API. <a href="https://doc.toasttab.com/openapi/configuration/operation/cashDrawersGet/" className="">More information</a> <br/> No sale reasons from the configuration API. <a href="https://doc.toasttab.com/openapi/configuration/operation/noSaleReasonsGet/" className="">More information</a> <br/> Payout reasons from the configuration API. <a href="https://doc.toasttab.com/openapi/configuration/operation/payoutReasonsGet/" className="">More information</a> <br/> Void reasons from the configuration API. <a href="https://doc.toasttab.com/openapi/configuration/operation/voidReasonsGet/" className="">More information</a></div></td>
      <td className=""><div className="">Cash configuration allows you to display metadata about the cash transactions at a restaurant. <br/> For more information about working with cash entries, see <a href="apiDevGuide-apiWorkingWithCashEntriesAndDeposits" className="">Cash management overview</a>.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Labor configuration</div></td>
      <td className=""><div className="">Break types from the configuration API. <a href="https://doc.toasttab.com/openapi/configuration/operation/breakTypesGet/" className="">More information</a> <br/> Employees from the labor API. <a href="apiDevGuide-api_get_all_employees" className="">More information</a> <br/> Jobs from the labor API. <a href="https://doc.toasttab.com/openapi/labor/operation/jobsGet/" className="">More information</a></div></td>
      <td className=""><div className="">This labor information allows you to display information about restaurant employees, the jobs they do, and the breaks they take.</div></td>
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







