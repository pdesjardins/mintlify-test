---
title: "Building an inventory tracking integration"
id: apiIntegrationChecklistInventory
type: section
documentId: devCookbook
parentSectionFile: devCookbook-cookbookAnalyticsOmitChunkFromSearchIndex.md
parentSectionTitle: "Reports"
previousSectionFile: devCookbook-apiHowToReporting.md
previousSectionTitle: "Building a data warehouse integration"
nextSectionFile: devCookbook-apiHowToBuildACrmGuestEngagementIntegration.md
nextSectionTitle: "Building a CRM & Guest Engagement integration"
externalReferences: [https://doc.toasttab.com/openapi/configuration/overview/, https://doc.toasttab.com/openapi/configuration/operation/salesCategoriesGet/, https://central.toasttab.com/s/article/Sales-Categories-1492812477858, https://doc.toasttab.com/openapi/configuration/operation/alternatePaymentTypesGet/, https://doc.toasttab.com/openapi/configuration/operation/discountsGet/, https://doc.toasttab.com/openapi/configuration/operation/taxRatesGet/, https://doc.toasttab.com/openapi/configuration/operation/restaurantServicesGet/, https://central.toasttab.com/s/article/Setup-Restaurant-Hours-and-Services]
excerpt: "Follow the steps below to build an inventory tracking integration with the Toast platform, which allows restaurants to stay aware of their ingredient usage and potential cost savings."
procedures: 0
codeExamples: 0
---

Follow the steps below to build an inventory tracking integration with the Toast platform, which allows restaurants to stay aware of their ingredient usage and potential cost savings.

## Required scopes

To follow these instructions, you must have the following [scopes](apiDevGuide-apiScopes):

- `config:read`


- `menus:read`


- `restaurants:read`


- `orders:read`



## Setup

### Complete initial integration setup

Review and implement the instructions in [How to build a Toast integration](devCookbook-apiIntegrationChecklistGeneral).

### Review menu hierarchy

Inventory tracking depends on usage of menu items. To understand Toast menu concepts before you begin development, review [menu hierarchy information](adminGuide-adminMenuHierarchy).

## Ingredient management

### Build purchase tracking functionality

Restaurants may want to compare ingredient purchases with ingredient usage to understand how much of each ingredient they discard.

Your integration should have a place in which restaurants can enter the date they purchased an ingredient and the volume they purchased.

It should also allow restaurants to record when they discarded the remainder of an ingredient.

### Retrieve menu items

Use the Toast [menus API](apiDevGuide-apiGettingMenuInformationFromTheMenusAPI)to retrieve all menu items that the restaurant sells.

Your inventory functionality should allow restaurant administrators to map recipes to menu items using the recipe management functionality that you build.

### Build recipe management functionality

Restaurants may want to report on specific ingredient volumes and sales.

For example, your integration's functionality should allow restaurant administrators to record that a ham and cheese sandwich requires bread, ham, and cheese.

Then when a guest orders a ham and cheese sandwich, your reports can reflect the amount of bread, ham, and cheese that the restaurant used in this sale.

### Build close-out inventory entry

Restaurants often want to record the total volume of each ingredient that remains at the end of the day. Your integration should have close-out inventory entry functionality that allows restaurants to record this information.

This functionality should also evaluate how much of each ingredient was wasted. For example, if a restaurant has 50 burger patties at the beginning of the day, sells 30 hamburgers, and has 18 patties at close-out, your integration should record that two patties were lost.

## Sales reporting

### Determine closeout hour

The `closeoutHour` value in the `General`object returned by the [restaurants API](apiDevGuide-apiRestaurantInformation) contains the restaurant's closeout hour.

The default closeout hour is 4:00 a.m. local time unless a Toast employee changes this setting. The `businessDate` value on API data changes after the `closeoutHour`.

Consider [daylight savings time](apiDevGuide-api_dates_and_timestamps#apiDaylightSavingsTime) when interacting with the closeout hour.

### Plan your display

The following table provides suggested information that you can display in different types of inventory reports. For more information about the difference between orders, checks, menu item selections, and payments, see [Orders API overview](apiDevGuide-portalOrdersApiOverview).


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className=""><div className=""><p className="text-base leading-relaxed">Object</p></div></th>
      <th className=""><div className=""><p className="text-base leading-relaxed"> Values</p></div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Orders</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Consider displaying the following reporting information for orders:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">Order source</p></li><li className=""><p className="text-base leading-relaxed">Opened date</p></li><li className=""><p className="text-base leading-relaxed">Paid date</p></li><li className=""><p className="text-base leading-relaxed">Closed date</p></li><li className=""><p className="text-base leading-relaxed">Voided status</p></li></ul></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Checks</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Consider displaying the following reporting information for checks:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">Display number</p></li><li className=""><p className="text-base leading-relaxed">Tab name</p></li><li className=""><p className="text-base leading-relaxed">Total amount</p></li><li className=""><p className="text-base leading-relaxed">Refunded amount</p></li><li className=""><p className="text-base leading-relaxed">Applied discount names</p></li><li className=""><p className="text-base leading-relaxed">Applied discount amounts</p></li></ul></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Menu item selections</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Consider displaying the following reporting information for item selections:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">Menu item name - Use <code className="font-mono text-sm">displayName</code> value on <code className="font-mono text-sm">Selection</code> object</p></li><li className=""><p className="text-base leading-relaxed">Applied modifier names - Modifiers may be nested arbitrarily deep on a menu item</p></li><li className=""><p className="text-base leading-relaxed">Price</p></li><li className=""><p className="text-base leading-relaxed">Applied discount names</p></li><li className=""><p className="text-base leading-relaxed">Applied discount amounts</p></li><li className=""><p className="text-base leading-relaxed">Sales category name</p></li><li className=""><p className="text-base leading-relaxed">Menu item tags</p></li><li className=""><p className="text-base leading-relaxed">Menu item SKU</p></li></ul></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Payments</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">By reporting on payments, you help restaurant administrators understand their profit margins on ingredients and menu items.</p> <p className="text-base leading-relaxed">Consider displaying the following reporting information for payments:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">Amount</p></li><li className=""><p className="text-base leading-relaxed">Refund information</p></li><li className=""><p className="text-base leading-relaxed">Type</p></li><li className=""><p className="text-base leading-relaxed">Payment status</p></li></ul></div></td>
    </tr>
  </tbody>
</table>
</div>

### Set up a recurring order retrieval

Retrieve all orders from the previous day using the `/ordersBulk` endpoint of the orders API. See [Getting detailed information about multiple orders](apiDevGuide-apiOrdersGetDetailedInfoAboutMultipleOrders) for more information.



> **Note**
> 
> Toast support recommends using the [orders updated webhook](apiDevGuide-devOrdersWebhookRef#apiOrdersWebhookOrderUpdated) to receive order updates as they occur instead of pulling order updates with the `/ordersBulk` endpoint. 


Use the `startDate` and `endDate` query parameters to retrieve orders by their `modifiedDate`timestamp.

### Consider a one-time historical order backfill per location

Consider loading historical order information for each restaurant location one time when that location starts using your integration.

Toast support recommends retrieving twelve weeks of historical data.

### Retrieve restaurant configuration information

Consider including the configuration information shown in the table below in your inventory integration.

After you decide which configuration information you want to display, set up a daily poll to the [configuration API](https://doc.toasttab.com/openapi/configuration/overview/) and [menus API](apiDevGuide-apiGettingMenuInformationFromTheMenusAPI)to retrieve it.

To reduce the amount of data that you receive when you poll the configuration API:

- Use the `lastModified` query parameter so that you only retrieve entities modified after the specified timestamp.


- Only retrieve a new menu when you determine that your existing menu is outdated. For more information about when to retrieve a new menu, see [Determining if a restaurant's menu data has gone stale](apiDevGuide-apiDeterminingIfYourMenuJsonIsOutdated_V2).




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
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Sales categories from the configuration API.</p> <p className="text-base leading-relaxed"><a href="https://doc.toasttab.com/openapi/configuration/operation/salesCategoriesGet/" className="">More information</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">See Toast Central for more information about <a href="https://central.toasttab.com/s/article/Sales-Categories-1492812477858" className="">sales categories</a>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Order configuration</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Alternative payment types from the configuration API. <a href="https://doc.toasttab.com/openapi/configuration/operation/alternatePaymentTypesGet/" className="">More information</a></p> <p className="text-base leading-relaxed">Discounts from the configuration API. <a href="https://doc.toasttab.com/openapi/configuration/operation/discountsGet/" className="">More information</a></p> <p className="text-base leading-relaxed">Tax rates from the configuration API. <a href="https://doc.toasttab.com/openapi/configuration/operation/taxRatesGet/" className="">More information</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">These pieces of configuration are often associated with orders.</p> <p className="text-base leading-relaxed">They describe how the order was placed and how its price was calculated. </p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Menu information</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Menu information from the menus API.</p> <p className="text-base leading-relaxed">In particular, consider saving the names of menu groups and the names, item tags, and SKUs of menu items.</p> <p className="text-base leading-relaxed"><a href="apiDevGuide-apiGettingMenuInformationFromTheMenusAPI" className="">More information</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The menus API returns menu item names and other menu-related information you may want to display in your inventory platform. </p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Restaurant information</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Restaurant services from the configuration API.</p> <p className="text-base leading-relaxed"><a href="https://doc.toasttab.com/openapi/configuration/operation/restaurantServicesGet/" className="">More information</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">This restaurant information allows your integration to report on when orders were placed in your restaurant.</p> <p className="text-base leading-relaxed">For more information, see this <a href="https://central.toasttab.com/s/article/Setup-Restaurant-Hours-and-Services" className="">Toast Central article about hours and services</a>.</p></div></td>
    </tr>
  </tbody>
</table>
</div>

### Add additional business logic

Consider suppressing voided orders from your reports by default and allowing users to actively choose to display these transactions.

Use the `voided` value on an `Order` object to determine whether an order was voided.

### Track sales across enterprise groups

Many restaurant groups use the [enterprise module](apiDevGuide-apiToastApisAndTheEnterpriseModule)of the Toast platform to share entities across many locations.

To track sales of the same item across multiple restaurant locations, use the `multilocationId` value in the menus API to tie sales together across locations.

For more information, see [multiLocationId values](apiDevGuide-apiUnderstandingGuidsEntityIdentifiersAndMultilocationIds_V2#apiMultilocationIdValues_V2).

### Build your inventory report display and summaries

After you build a basic data warehouse display of transactional data, consider summarizing inventory and sales in any of the following ways:



****Inventory data****
: - Total sales per ingredient in dollars or currency value


- Profit margin per ingredient


- Total volume of each ingredient used


- Wastage per ingredient





****Sales data****
: - Overall sales value in dollars or currency value


- Total number of orders


- Total sales per sales category


- Total sales per item tag







## Predictive capabilities

### Evaluate future purchase decisions

Your integration will be particularly helpful for restaurants if you use the data you mine to produce advice about the inventory purchases they should make in the future.

For example, is the restaurant about to run out of flour? Should they stock up on burgers on Fridays if burgers tend to sell well on Saturdays? Should they remove a certain item from their menu if it has not sold well in months? Are they undercharging for avocados?

Consider how you can help restaurants make smart purchase decisions in the future and make optimal use of their current inventory today.

