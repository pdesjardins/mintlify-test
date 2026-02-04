---
title: "Building a digital menu signage integration"
id: apiBuildingDigitalSignage
type: section
documentId: devCookbook
parentSectionFile: devCookbook-cookbookOrderingOmitChunkFromSearchIndex.md
parentSectionTitle: "Ordering"
previousSectionFile: devCookbook-apiIntegrationChecklistOrdering.md
previousSectionTitle: "Building an online ordering integration"
nextSectionFile: devCookbook-apiIntegrationChecklistDelivery.md
nextSectionTitle: "Building a delivery dispatch integration"
externalReferences: [https://central.toasttab.com/s/article/86-an-Item]
excerpt: "Follow the steps below to build a digital menu signage integration with the Toast platform."
procedures: 0
codeExamples: 0
---

Follow the steps below to build a digital menu signage integration with the Toast platform.

This integration allows you to retrieve menu and restaurant information to display on a digital menu signage board.

## Required scopes

To follow these instructions, you must have the following [scopes](apiScopes.html):

- `menus:read`


- `restaurants:read`


- `stock:read`



You can retrieve a list of your current scopes through your [Toast developer portal](apiDeveloperPortal.html#apiDeveloperPortalScopes) account. If you lack the required scopes, refer to the [Integration partnership process](integrationDevProcess.html)guide for instructions on requesting access.

## Setup and planning

### Complete initial integration setup

Review and implement the instructions in [How to build a Toast integration](apiIntegrationChecklistGeneral.html).

### Learn menu structure and hierarchy

Building a digital menu signage integration requires understanding of the Toast menu hierarchy, menu groups, items, modifiers, and sub-menu groups.

To understand Toast menu concepts before you begin development, please review the [menu hierarchy documentation](adminMenuHierarchy.html).

## Handle menu data

### Build your menu

Your digital signage might display different information depending on the exact experience you’re targeting. At least top level menu item names will be required, and other information may be displayed depending on the target experience.

Entities that might be displayed on digital signage:

- Menu entity names, at all levels of the menu hierarchy


- Item descriptions


- Item images


- Prices


- Item tags. Common item tags include “gluten free” and “vegetarian”.



Only display a menu while it is configured in Toast Web to be available. Restaurants can configure specific menus to only be available at certain times of day, such as a brunch or happy hour menu. Your integration should only display menus when their corresponding `Availability` object in the `/menus` endpoint of the menus API says that they should be visible.



> **Note**
> 
> Consider time changes (like daylight savings time) when building menu display times.


Your menu display should also accommodate [pricing strategies and rules](apiUsingPricingRulesAndPricingStrategyToCalculatePrices_V2.html) the restaurant may have set up. These allow the restaurant to specify menu item or modifier pricing at a very granular level. Your integration should consume this work.

Your menu display configuration interface should allow a restaurant to refine exactly which menu items will be displayed and how. In other words, even if a menu or menu item is available for your integration, the person configuring the digital signage using your integration may want to further customize what appears and how in your administration interface.

Update menus on a near-real-time basis. The [menus webhook](apiMenusWebhook.html) is the most effective way to do this. The webhook and other methods are described in the [Determining if a restaurant's menu data has gone stale](apiDeterminingIfYourMenuJsonIsOutdated_V2.html)documentation.

Avoid infinite loops when parsing menus. There is a rare but possible menu configuration that can send your integration into an infinite loop when parsing a restaurant menu. To avoid this problem, see [Detecting and avoiding infinite loops in the menus API JSON](apiDetectingAndAvoidingInfiniteLoopsInTheMenusApiJson.html).

Finally, your menu display integration should be able to handle [multiLocationId values](apiUnderstandingGuidsEntityIdentifiersAndMultilocationIds_V2.html). These values represent versions of the same menu item across multiple locations in a restaurant group. Handling these values will be important for many of your larger customers.

### Handle out of stock items

Understand item stock information utilizing our [Stock API](apiUsingTheStockApi.html) endpoint and webhooks. Your menu display should prevent guests from seeing (ordering) items that are out of stock. Initialize the stock status of menu items by polling the stock API. Then your integration can use the [stock webhook](apiUsingTheStockWebhook.html) to receive real-time notifications about item stock updates. Fall back to the stock API if you miss a webhook update or if your webhook subscription is paused.

See [this Toast Central article](https://central.toasttab.com/s/article/86-an-Item) for information about how to test out of stock items.

