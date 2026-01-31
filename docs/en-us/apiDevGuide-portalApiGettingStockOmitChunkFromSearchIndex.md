---
title: "Chapter 5. Stock"
id: portalApiGettingStockOmitChunkFromSearchIndex
type: chapter
documentId: apiDevGuide
parentSectionFile: apiDevGuide-index.md
parentSectionTitle: "Developer guide"
previousSectionFile: apiDevGuide-menu_information_config_api.md
previousSectionTitle: "Getting menu information from the configuration API"
nextSectionFile: apiDevGuide-apiGettingStockInformationOmitChunkFromSearchIndex.md
nextSectionTitle: "Getting stock information"
externalReferences: [https://status-dev.toasttab.com/]
procedures: 0
codeExamples: 0
---

# Chapter 5. Stock

## Stock overview

The stock webhook and stock API provide inventory information for menu items and modifiers. This inventory information includes the stock status of the menu item or modifier (in stock, out of stock, or low quantity). Depending on the stock status, the webhook payload or API response may also include the quantity of the menu item or modifier.

With the [stock webhook](apiGettingStockInformationOmitChunkFromSearchIndex.html#apiUsingTheStockWebhook), the Toast platform pushes updates to your system when the stock status of a menu item or modifier changes. This is the preferred method for getting information about changes to a menu item or modifier's inventory.

With the [stock API](apiUsingTheStockApi.html), you can retrieve a list of menu items that are out of stock, in limited supply, or both. You can also submit a list of menu items or modifiers to the stock API and it returns their current stock status and quantities.

In addition, the stock API gives you the ability to update inventory information for menu items and modifiers.



> **Note**
> 
> If the stock API is temporarily unavailable, Toast Support recommends that your integration assumes the items or modifiers are in stock and places the order anyway. The orders API will accept the order when it is placed even if it contains out of stock items or modifiers.
> If the stock API is unavailable, it returns 5xx HTTP responses to your requests. You can also check the [Toast API Status](https://status-dev.toasttab.com/)site for information on the health of Toast APIs.


To use the stock API, your API account must have one of the following [scopes](apiScopes.html):

- To retrieve inventory information, your API account must have the `stock:read` scope.


- To update inventory information, your account must have the `stock:write` scope.



Stock updates do not represent changes to the menu itself. Updating the menu and consuming stock updates should occur in separate processes. Only retrieve a new menu when the menus webhook has sent a message that the menu is outdated, or a request to the `/metadata` endpoint of the menus API indicates that the menu JSON is outdated. For more information about when to retrieve a new menu, see [Determining if a restaurant's menu data has gone stale](apiGettingMenuInformationOmitChunkFromSearchIndex.html#apiDeterminingIfYourMenuJsonIsOutdated_V2).



> **Note**
> 
> Modifiers are supported by an underlying menu item, called the modifier's item reference. Therefore, in this section, the term *menu item* is used to generically refer to both standalone menu items and modifier item references, because the same data is returned for both entities. For detailed information on modifier item references, see [Understanding a modifier item reference](adminPricingModifierOptions.html#adminUnderstandingAModifierOptionsItemReference).




> **Note**
> 
> Scheduled future orders from Toast product ordering channels, such as those placed through the Toast POS or Toast Online Ordering, decrement quantity-based stock immediately at the time of order creation. For example, if a restaurant has ten cookies in stock on Monday and a guest places a catering order on Monday for fulfillment on Friday that includes a cookie, the stock count will drop to nine on Monday (not Friday).
> Scheduled future orders from the orders API do not decrement stock when the order is created. Stock is only decremented when the order is fired to the kitchen. For more information about scheduling future orders, see [Scheduling future orders](orders_api_future_orders.html).


