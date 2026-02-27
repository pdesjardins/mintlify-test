---
title: "Building a security integration"
id: apiIntegrationChecklistSecurity
type: section
documentId: devCookbook
parentSectionFile: devCookbook-cookbookSecurityOmitChunkFromSearchIndex.md
parentSectionTitle: "Security"
previousSectionFile: devCookbook-cookbookSecurityOmitChunkFromSearchIndex.md
previousSectionTitle: "Security"
nextSectionFile: devCookbook-cookbookWebhooksOmitChunkFromSearchIndex.md
nextSectionTitle: "Webhooks"
externalReferences: [https://doc.toasttab.com/openapi/orders/overview/, https://doc.toasttab.com/openapi/configuration/overview/, https://doc.toasttab.com/openapi/menus/overview/, https://doc.toasttab.com/openapi/configuration/operation/alternatePaymentTypesGet/, https://doc.toasttab.com/openapi/configuration/operation/diningOptionsGet/, https://doc.toasttab.com/openapi/configuration/operation/discountsGet/, https://doc.toasttab.com/openapi/configuration/operation/noSaleReasonsGet/, https://doc.toasttab.com/openapi/configuration/operation/payoutReasonsGet/, https://doc.toasttab.com/openapi/configuration/operation/serviceChargesGet/, https://doc.toasttab.com/openapi/configuration/operation/taxRatesGet/, https://doc.toasttab.com/openapi/configuration/operation/tipWithholdingGet/, https://doc.toasttab.com/openapi/configuration/operation/voidReasonsGet/, https://doc.toasttab.com/openapi/menusv3/operation/metadataGet/, https://doc.toasttab.com/doc/devguide/apiGettingMenuInformationFromTheMenusAPI.html, https://doc.toasttab.com/openapi/configuration/operation/cashDrawersGet/, https://doc.toasttab.com/doc/devguide/api_get_all_employees.html, https://doc.toasttab.com/doc/devguide/https://doc.toasttab.com/openapi/labor/operation/jobsGet/, https://doc.toasttab.com/openapi/orders/operation/ordersBulkGet/, https://doc.toasttab.com/doc/devguide/apiRestaurantInformation.html, https://doc.toasttab.com/openapi/orders/tag/Data-definitions/schema/Order/, https://doc.toasttab.com/openapi/orders/tag/Data-definitions/schema/Check/, https://central.toasttab.com/s/article/Voiding-Items-Payments-and-Checks]
excerpt: "Follow the steps below to build a..."
procedures: 0
codeExamples: 0
---

Follow the steps below to build a security integration with the Toast platform. This guide outlines how your integration can use Toast orders data in coordination with video footage from your security monitoring service to develop a security business solution. Using time stamps, you can integrate video footage with order data, allowing restaurants to monitor operations and detect possible fraud or theft.

After you complete and test these steps, you can complete an end-to-end test of your integration functionality.

## Required scopes

To build a security integration, you must have the following [scopes](apiDevGuide-apiScopes):

- `cashmgmt:read`


- `config:read`


- `labor:read`


- `labor.employees:read`


- `menus:read`


- `orders:read`


- `restaurants:read`



You can retrieve a list of your current scopes through your [Toast developer portal](apiDevGuide-apiDeveloperPortal#apiDeveloperPortalScopes) account. If you lack the required scopes, refer to the [Integration partnership process](apiDevGuide-integrationDevProcess)guide for instructions on requesting access.

## Setup and planning

### Complete initial integration setup

Review and implement the instructions in [How to build a Toast integration](devCookbook-apiIntegrationChecklistGeneral).

### Review menu and order structure

Reporting on sales depends on a restaurant’s usage of menu items and the overall structure of orders.

To understand Toast menu concepts before you begin development, review [Menu hierarchy](adminGuide-adminMenuHierarchy).

To review order structure, see [Orders API overview](apiDevGuide-portalOrdersApiOverview) and [Order object summary](apiDevGuide-apiOrdersOrderObjectSummary). For more information about the orders API, see the [orders API reference documentation](https://doc.toasttab.com/openapi/orders/overview/).

### Decide what order information you will provide

Before beginning development, decide how you will report on the data retrieved. You should consider what information you will need to align transactions with video footage to detect possible fraud, theft, and so on. We specifically recommend you report on discounts, voids, and refunds. This guide will also describe how to determine the time a transaction began and ended, on which device, and by which employee, in order to sync this with video footage.

### Plan your display

The following table provides suggested information that you can use when displaying order data alongside video footage or in reports. 


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className="">Report type</th>
      <th className="">Object</th>
      <th className="">Values</th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="">Order data</td>
      <td className="">Orders</td>
      <td className="">Consider displaying the following reporting information for orders:<ul className=""><li className="">Dining option name</li><li className="">Dining option behavior</li><li className="">Server name</li><li className="">Created and modified device</li><li className="">Order source</li><li className="">Opened date</li><li className="">Modified date</li><li className="">Paid date</li><li className="">Closed date</li><li className="">Voided status</li></ul></td>
    </tr>
    <tr className="">
      <td className="">Checks</td>
      <td className="">Consider displaying the following reporting information for checks:<ul className=""><li className="">Display number</li><li className="">Tab name</li><li className="">Total amount</li><li className="">Tax amount</li><li className="">Refunded amount</li><li className="">Applied discount names</li><li className="">Applied discount amounts</li><li className="">Applied service charge names</li><li className="">Applied service charge amounts</li></ul></td>
    </tr>
    <tr className="">
      <td className="">Menu item selections</td>
      <td className="">Consider displaying the following reporting information for menu item selections:<ul className=""><li className="">Menu item name - Use the <code className="">displayName</code> value within the <code className="">Selection</code> object</li><li className="">Applied modifier names - Modifiers may be nested arbitrarily deep on a menu item</li><li className="">Price</li><li className="">Applied tax rate names</li><li className="">Applied tax values</li><li className="">Applied discount names</li><li className="">Applied discount amounts</li></ul></td>
    </tr>
    <tr className="">
      <td className="">Payments</td>
      <td className="">Consider displaying the following reporting information for payments:<ul className=""><li className="">Amount</li><li className="">Tip amount</li><li className="">Refund information</li><li className="">Type</li></ul></td>
    </tr>
    <tr className="">
      <td className="">Cash transactions</td>
      <td className="">Cash entries</td>
      <td className="">Consider displaying the following reporting information for cash entries:<ul className=""><li className="">Cash entry type</li><li className="">Cash entry date</li><li className="">Amount</li><li className="">Reason</li><li className="">Cash drawer name</li><li className="">Payout reason name</li><li className="">No sale reason name</li><li className="">Employee 1 name</li><li className="">Employee 2 name</li><li className="">Reversed cash transaction</li></ul></td>
    </tr>
    <tr className="">
      <td className="">Deposits</td>
      <td className="">Consider displaying the following reporting information for cash deposits:<ul className=""><li className="">Cash entry date</li><li className="">Amount</li><li className="">Employee name</li><li className="">Reversed cash transaction</li></ul></td>
    </tr>
  </tbody>
</table>
</div>

## Retrieve restaurant configuration information

### Set up recurring retrieval of menu and configuration information

Consider including the following configuration information in your integration. After deciding which configuration information you want to retrieve, set up a daily poll to the [configuration API](https://doc.toasttab.com/openapi/configuration/overview/) and [menus API](https://doc.toasttab.com/openapi/menus/overview/) to retrieve it. 

In addition to the information in the table below, query the following configuration API endpoints at least once a day to ensure your integration captures any changes a restaurant makes to their configuration: 

- [/alternatePaymentTypes](https://doc.toasttab.com/openapi/configuration/operation/alternatePaymentTypesGet/)


- [/diningOptions](https://doc.toasttab.com/openapi/configuration/operation/diningOptionsGet/)


- [/discounts](https://doc.toasttab.com/openapi/configuration/operation/discountsGet/)


- [/noSalesReasons](https://doc.toasttab.com/openapi/configuration/operation/noSaleReasonsGet/)


- [/payoutReasons](https://doc.toasttab.com/openapi/configuration/operation/payoutReasonsGet/)


- [/serviceCharges](https://doc.toasttab.com/openapi/configuration/operation/serviceChargesGet/)


- [/taxRates](https://doc.toasttab.com/openapi/configuration/operation/taxRatesGet/)


- [/tipWithholding](https://doc.toasttab.com/openapi/configuration/operation/tipWithholdingGet/)


- [/voidReasons](https://doc.toasttab.com/openapi/configuration/operation/voidReasonsGet/)



To reduce the amount of data that you receive when you poll the configuration API and menus API: Use the menus webhook or query the /metadata endpoint of menus API throughout the day.



> **Note**
> 
> Only retrieve a new menu when you determine that your existing menu is outdated.


- Use the `lastModified` query parameter to only retrieve entities modified after the specified timestamp.


- Use the [menus webhook](apiDevGuide-apiMenusWebhook) or query the [/metadata](https://doc.toasttab.com/openapi/menusv3/operation/metadataGet/)endpoint of menus API throughout the day. Only retrieve a new menu when you determine that your [existing menu is outdated](apiDevGuide-apiDeterminingIfYourMenuJsonIsOutdated_V2).




<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className="">Information type</th>
      <th className="">Configuration</th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="">Order configuration</td>
      <td className="">These pieces of configuration are often associated with orders. They describe how the order was placed and how its price was calculated.<ul className=""><li className="">Alternate payment types from the configuration API. <a href="https://doc.toasttab.com/openapi/configuration/operation/alternatePaymentTypesGet/" className="">More information</a></li><li className="">Dining options from the configuration API. <a href="https://doc.toasttab.com/openapi/configuration/operation/diningOptionsGet/" className="">More information</a></li><li className="">Discounts from the configuration API. <a href="https://doc.toasttab.com/openapi/configuration/operation/discountsGet/" className="">More information</a></li><li className="">Service charges from the configuration API. <a href="https://doc.toasttab.com/openapi/configuration/operation/serviceChargesGet/" className="">More information</a></li><li className="">Tax rates from the configuration API. <a href="https://doc.toasttab.com/openapi/configuration/operation/taxRatesGet/" className="">More information</a></li><li className="">Void reasons from the configuration API. <a href="https://doc.toasttab.com/openapi/configuration/operation/voidReasonsGet/" className="">More information</a></li></ul></td>
    </tr>
    <tr className="">
      <td className="">Menu information</td>
      <td className="">The menus API returns menu item names and other menu-related information you may want to display in your platform.<ul className=""><li className="">Menu information, such as menu group names, menu item names, and item tags from the menus API. <a href="https://doc.toasttab.com/doc/devguide/apiGettingMenuInformationFromTheMenusAPI.html" className="">More information</a></li></ul></td>
    </tr>
    <tr className="">
      <td className="">Cash configuration</td>
      <td className="">Cash configuration allows you to display metadata about the cash transactions at a restaurant. For more information about working with cash entries, see <a href="apiDevGuide-apiWorkingWithCashEntriesAndDeposits" className="">Cash management overview</a>. <ul className=""><li className="">Cash drawers from the configuration API. <a href="https://doc.toasttab.com/openapi/configuration/operation/cashDrawersGet/" className="">More information</a></li><li className="">No sale reasons from the configuration API. <a href="https://doc.toasttab.com/openapi/configuration/operation/noSaleReasonsGet/" className="">More information</a></li><li className="">Payout reasons from the configuration API. <a href="https://doc.toasttab.com/openapi/configuration/operation/payoutReasonsGet/" className="">More information</a></li><li className="">Void reasons from the configuration API. <a href="https://doc.toasttab.com/openapi/configuration/operation/voidReasonsGet/" className="">More information</a></li></ul></td>
    </tr>
    <tr className="">
      <td className="">Labor configuration</td>
      <td className="">This labor information allows you to acquire information about restaurant employees and the jobs they do. <ul className=""><li className="">Employees from the labor API. <a href="https://doc.toasttab.com/doc/devguide/api_get_all_employees.html" className="">More information</a></li><li className="">Jobs from the labor API. <a href="https://doc.toasttab.com/doc/devguide/https://doc.toasttab.com/openapi/labor/operation/jobsGet/" className="">More information</a></li></ul></td>
    </tr>
  </tbody>
</table>
</div>

### Set up recurring order retrieval of transactional information

To report on completed orders, you need to retrieve orders at least once per day using the `startDate` and `endDate` parameters of the [/ordersBulk](https://doc.toasttab.com/openapi/orders/operation/ordersBulkGet/)endpoint of the orders API. See [Getting detailed information about multiple orders](apiDevGuide-apiOrdersGetDetailedInfoAboutMultipleOrders) for more information.

For real-time order information, Toast support recommends using the [Orders webhook](apiDevGuide-devOrdersWebhookRef) to receive order updates as they occur instead of pulling order updates with the [/ordersBulk](https://doc.toasttab.com/openapi/orders/operation/ordersBulkGet/)endpoint.

### Determine closeout hour

The `closeoutHour` value in the `General`object returned by the [restaurants API](https://doc.toasttab.com/doc/devguide/apiRestaurantInformation.html) contains the restaurant’s closeout hour. The default closeout hour is 4:00 a.m. local time unless a Toast employee changes this setting. The `businessDate` value on order entities changes after the `closeoutHour`.

Consider [daylight savings time](apiDevGuide-api_dates_and_timestamps#apiDaylightSavingsTime) when interacting with the closeout hour.

## Building report functionality

### Determine dining option and source of an order

Based on the response from the [/diningOptions](https://doc.toasttab.com/openapi/configuration/operation/diningOptionsGet/)endpoint, determine which dining options your security integration needs to sync with video footage and/or report on. Each dining option has a corresponding behavior such as "`DINE_IN`", "`TAKE_OUT`", or "`DELIVERY`". Special consideration should be taken for dining options indicating an off-premise order and payment experience (such as orders placed through the orders API or online orders) as these orders will not have an on-premise payment transaction to sync to video footage. Optionally, you can use timestamps on these orders to sync with preparation video footage.

While off-premise orders will have limited relation to video footage, these orders may need to be included in any reports provided - such as reporting on discounts, voids, and so on. In this case, the order source should be considered. Possible order sources include in-store, online, API, kiosk, and so on. All order sources are documented on the [order object API reference](https://doc.toasttab.com/openapi/orders/tag/Data-definitions/schema/Order/).

### Analyze order timestamps

There are many timestamps included in the [order](https://doc.toasttab.com/openapi/orders/tag/Data-definitions/schema/Order/)object and [check](https://doc.toasttab.com/openapi/orders/tag/Data-definitions/schema/Check/)object that will be helpful to consider when syncing in-store transactions with video footage. Review the [order object API reference](https://doc.toasttab.com/openapi/orders/tag/Data-definitions/schema/Order/) with consideration to the `createdDate`, `openedDate`, `paidDate`, `closedDate`, and `modifiedDate`. For void reporting, the `voidDate`and `voidBusinessDate` will also be useful.

### Determine voided entities

Servers can void orders, checks, item selections, and payments. If the `voided` value on an order, check, selection, or payment is `true`, your integration should include this data in the applicable void report. Consider displaying selection and payment void reasons by mapping the `voidReason` value on the selection or payment to the information in the [/voidReasons](https://doc.toasttab.com/openapi/configuration/operation/voidReasonsGet/)endpoint of the configuration API. 

See this [Toast Central article](https://central.toasttab.com/s/article/Voiding-Items-Payments-and-Checks) for more information about how to test void functionality.

### Determine discounts applied

Discounts can be applied to checks and item selections. Parse the checks and selections objects for the `appliedDiscounts`array in order to appropriately report on discounts. 

### Determine refunds

If the payment object of a [check](https://doc.toasttab.com/openapi/orders/tag/Data-definitions/schema/Check/)includes a `refundStatus` value of `PARTIAL` or `FULL`, details of the refund can be found on the refund object.

