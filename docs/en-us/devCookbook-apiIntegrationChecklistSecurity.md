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

| Report type | Object | Values | 
| --- | --- | --- |
| Order data | Orders | Consider displaying the following reporting information for orders:- Dining option name
- Dining option behavior
- Server name
- Created and modified device
- Order source
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
| Menu item selections | Consider displaying the following reporting information for menu item selections:- Menu item name - Use the `displayName`value within the `Selection` object
- Applied modifier names - Modifiers may be nested arbitrarily deep on a menu item
- Price
- Applied tax rate names
- Applied tax values
- Applied discount names
- Applied discount amounts

 | 
| Payments | Consider displaying the following reporting information for payments:- Amount
- Tip amount
- Refund information
- Type

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



| Information type | Configuration | 
| --- | --- |
| Order configuration | These pieces of configuration are often associated with orders. They describe how the order was placed and how its price was calculated.- Alternate payment types from the configuration API. [More information](https://doc.toasttab.com/openapi/configuration/operation/alternatePaymentTypesGet/)
- Dining options from the configuration API. [More information](https://doc.toasttab.com/openapi/configuration/operation/diningOptionsGet/)
- Discounts from the configuration API. [More information](https://doc.toasttab.com/openapi/configuration/operation/discountsGet/)
- Service charges from the configuration API. [More information](https://doc.toasttab.com/openapi/configuration/operation/serviceChargesGet/)
- Tax rates from the configuration API. [More information](https://doc.toasttab.com/openapi/configuration/operation/taxRatesGet/)
- Void reasons from the configuration API. [More information](https://doc.toasttab.com/openapi/configuration/operation/voidReasonsGet/)

 | 
| Menu information | The menus API returns menu item names and other menu-related information you may want to display in your platform.- Menu information, such as menu group names, menu item names, and item tags from the menus API. [More information](https://doc.toasttab.com/doc/devguide/apiGettingMenuInformationFromTheMenusAPI.html)

 | 
| Cash configuration | Cash configuration allows you to display metadata about the cash transactions at a restaurant. For more information about working with cash entries, see [Cash management overview](apiDevGuide-apiWorkingWithCashEntriesAndDeposits). - Cash drawers from the configuration API. [More information](https://doc.toasttab.com/openapi/configuration/operation/cashDrawersGet/)
- No sale reasons from the configuration API. [More information](https://doc.toasttab.com/openapi/configuration/operation/noSaleReasonsGet/)
- Payout reasons from the configuration API. [More information](https://doc.toasttab.com/openapi/configuration/operation/payoutReasonsGet/)
- Void reasons from the configuration API. [More information](https://doc.toasttab.com/openapi/configuration/operation/voidReasonsGet/)

 | 
| Labor configuration | This labor information allows you to acquire information about restaurant employees and the jobs they do. - Employees from the labor API. [More information](https://doc.toasttab.com/doc/devguide/api_get_all_employees.html)
- Jobs from the labor API. [More information](https://doc.toasttab.com/doc/devguide/https://doc.toasttab.com/openapi/labor/operation/jobsGet/)

 | 

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

