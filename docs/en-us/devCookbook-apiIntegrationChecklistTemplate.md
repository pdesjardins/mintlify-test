---
title: "Building an Analytics integration"
id: apiIntegrationChecklistTemplate
type: section
documentId: devCookbook
parentSectionFile: devCookbook-cookbookAnalyticsOmitChunkFromSearchIndex.md
parentSectionTitle: "Reports"
previousSectionFile: devCookbook-cookbookAnalyticsOmitChunkFromSearchIndex.md
previousSectionTitle: "Reports"
nextSectionFile: devCookbook-apiIntegrationChecklistPayroll.md
nextSectionTitle: "Building labor reports"
externalReferences: [https://doc.toasttab.com/openapi/configuration/overview/, https://doc.toasttab.com/openapi/restaurants/overview/, https://doc.toasttab.com/doc/platformguide/adminMenuHierarchy.html, https://doc.toasttab.com/doc/devguide/portalOrdersApiOverview.html, https://doc.toasttab.com/doc/devguide/apiOrdersOrderObjectSummary.html, https://doc.toasttab.com/openapi/orders/overview/, https://doc.toasttab.com/openapi/cashmanagement/operation/entriesGet/, https://doc.toasttab.com/openapi/cashmanagement/operation/depositsGet/, https://doc.toasttab.com/doc/devguide/api_get_all_employees.html, https://doc.toasttab.com/doc/apiordersdraftdoc/devOrdersWebhookRef.html#apiOrdersWebhookOrderUpdated, https://doc.toasttab.com/openapi/orders/operation/ordersBulkGet/, https://doc.toasttab.com/doc/devguide/apiMenusWebhook.html, https://doc.toasttab.com/doc/devguide/apiDeterminingIfYourMenuJsonIsOutdated_V2.html, https://doc.toasttab.com/doc/devguide/apiRateLimiting.html, https://doc.toasttab.com/doc/devguide/api_dates_and_timestamps.html#apiDaylightSavingsTime, https://doc.toasttab.com/openapi/restaurants/operation/restaurantsRestaurantGuidGet/]
excerpt: "Follow the steps below to build an analytics integration with the Toast platform."
procedures: 0
codeExamples: 0
---

Follow the steps below to build an analytics integration with the Toast platform.

This integration allows you to provide restaurants with detailed information about sales, labor, inventory, and more. 

## Required scopes

To follow these instructions, you must have the following [scopes](apiScopes.html):

- `config:read`


- restaurants:read


- menus:read


- orders:read


- labor.employees:read


- labor:read


- cashmgmt:read



You can retrieve a list of your current scopes through your [Toast developer portal](apiDeveloperPortal.html#apiDeveloperPortalScopes) account. If you lack the required scopes, refer to the [Integration partnership process](integrationDevProcess.html)guide for instructions on requesting access.

## Setup and planning

### Complete initial integration setup

Review and implement the instructions in [How to build a Toast integration](apiIntegrationChecklistGeneral.html).

### Retrieve configuration information

Use the [configuration API](https://doc.toasttab.com/openapi/configuration/overview/) to retrieve necessary configuration information you need to build your analytics capabilities. For example, retrieving a list of the dining options for a restaurant so that you can provide human-readable dining option names when presenting information from the orders API.

Use the [restaurants API](https://doc.toasttab.com/openapi/restaurants/overview/) to retrieve general information about the configuration of a restaurant. 

To ensure you have the latest restaurant configuration, poll the configuration API and the restaurants API once per restaurant location per day, and update configuration information in your system based on anything that was added, updated, or deleted. 

### Learn menu and order structure concepts

Integrations consuming order information will rely on the restaurants’ usage of menu items and the overall structure of orders. 

To understand Toast menu concepts before you begin development, review [menu hierarchy information](https://doc.toasttab.com/doc/platformguide/adminMenuHierarchy.html). 

To successfully retrieve information relevant to orders, familiarize yourself with the structure of an order by reading the [Orders API overview](https://doc.toasttab.com/doc/devguide/portalOrdersApiOverview.html) and [Order object summary](https://doc.toasttab.com/doc/devguide/apiOrdersOrderObjectSummary.html). For more information about the orders API, see the [reference documentation](https://doc.toasttab.com/openapi/orders/overview/). 

### Decide if your integration will include cash transaction information

To report on cash transactions, you need to retrieve cash entries and deposits once per day. 

- For [cash entries](https://doc.toasttab.com/openapi/cashmanagement/operation/entriesGet/), use the `businessDate` parameter of the `/entries` endpoint of the cash management API. 


- For [deposits](https://doc.toasttab.com/openapi/cashmanagement/operation/depositsGet/), use the `businessDate` parameter of the `/deposits` endpoint of the cash management API. 



To display additional information associated with cash transactions, query the following configuration API endpoints at least once per day: 

- `/cashDrawers`


- `/noSaleReasons`


- `/payoutReasons`



In addition, query the `/employees`[endpoint](https://doc.toasttab.com/doc/devguide/api_get_all_employees.html)of the labor API at least once per day to retrieve information about the employees associated with cash transactions.

### Decide if your integration will include order information

To report on order information, use the [orders updated webhook](https://doc.toasttab.com/doc/apiordersdraftdoc/devOrdersWebhookRef.html#apiOrdersWebhookOrderUpdated) to receive order updates as they occur.



> **Note**
> 
> You can also use the `/ordersBulk`[endpoint](https://doc.toasttab.com/openapi/orders/operation/ordersBulkGet/)to retrieve orders using the `startDate` and `endDate` parameters. 


To ensure you have the latest menu information, use the menus webhook or query the `/metadata` endpoint of the menus API throughout the day. For more information about understanding menu updates, see [Menus webhook](https://doc.toasttab.com/doc/devguide/apiMenusWebhook.html).

Retrieve a new menu when you determine that [your existing menu is outdated](https://doc.toasttab.com/doc/devguide/apiDeterminingIfYourMenuJsonIsOutdated_V2.html). 

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



### Consider historical backfill for integrations consuming order information 

When a restaurant first connects to your integration, they may expect to see some historical information already displayed in your system. Define how many days of historical orders and cash transactions you retrieve when a restaurant first connects to your integration. 

To retrieve the orders for these days, use either the `businessDate` or `startDate` and `endDate`parameters of the `/ordersBulk` endpoint of the orders API. 

Toast support recommends retrieving twelve weeks of historical and orders when a restaurant first connects to your integration.

Ensure your integration adheres to the endpoint specific rate-limit for the `/ordersBulk` endpoint when retrieving order data. For more information about Toast rate limits, see [Rate limiting](https://doc.toasttab.com/doc/devguide/apiRateLimiting.html).

### Determine closeout hour

When retrieving cash transaction or order information, you need to determine the closeout hour of the restaurant. 

The `closeoutHour` value in the `General`object returned by the restaurants API contains the restaurant’s closeout hour. 

The default closeout hour is 4:00am local time unless a Toast employee changes this setting. The `businessDate` value on order entities changes after the `closeoutHour`. 

Consider [daylight savings time](https://doc.toasttab.com/doc/devguide/api_dates_and_timestamps.html#apiDaylightSavingsTime) when interacting with the closeout hour. 

For more information, see the [API reference](https://doc.toasttab.com/openapi/restaurants/operation/restaurantsRestaurantGuidGet/). 

