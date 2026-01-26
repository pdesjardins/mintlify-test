---
title: "Using menus API data to submit properly formed orders"
id: apiUsingMenusApiDataToSubmitProperlyFormedOrders_V2
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiGettingMenuInformationOmitChunkFromSearchIndex.md
parentSectionTitle: "Getting menu information"
previousSectionFile: apiDevGuide-apiUsingTaxInfoAndModifierOptionTaxInfoToCalculateTaxesForMenuItemsAndModOptions.md
previousSectionTitle: "Using taxInfo and modifierOptionTaxInfo to calculate taxes for menu items and modifier options"
nextSectionFile: apiDevGuide-apiDeterminingIfMenuItemsOrModifiersContainAlcohol.md
nextSectionTitle: "Determining if a menu item or modifier contains alcohol"
externalReferences: [https://doc.toasttab.com/openapi/menusv3/tag/Data-definitions/schema/Menu/, https://doc.toasttab.com/openapi/menusv3/tag/Data-definitions/schema/ModifierGroup/, https://doc.toasttab.com/openapi/menusv3/tag/Data-definitions/schema/ModifierOption/, https://doc.toasttab.com/openapi/menusv3/tag/Data-definitions/schema/MenuItem/, https://doc.toasttab.com/openapi/orders/tag/Data-definitions/schema/Selection/]
excerpt: "If you are using the menus API data to construct an ordering application, those orders will ultimately be..."
keywords: [menus,data,submit,properly,formed,orders,minSelections,maxSelections,requiredMode,isMultiSelect]
procedures: 0
codeExamples: 0
---

### Using menus API data to submit properly formed orders

If you are using the menus API data to construct an ordering application, those orders will ultimately be injected into the Toast platform using the orders API. It is important that orders injected into the orders API are properly formed and valid. You can inspect certain values in the menus API data to make sure that the orders you submit to the orders API will pass validation. For example, if a modifier group has a minimum number of selections required, the orders API will fail an order that contains too few selections from that modifier group. You can inspect the `minSelections`values on the modifier groups returned by the menus API to make sure you account for the minimum selections requirement and your orders will pass validation.

Use the following values returned by the menus API to ensure that you submit orders correctly to the orders API:

- The `availability`value of the [Menu](https://doc.toasttab.com/openapi/menusv3/tag/Data-definitions/schema/Menu/)object. The orders API *does not validate*against the availability settings of a menu, meaning it is possible to submit an order for an item on a menu that is not currently available (see [Orders API limitations](apiOrdersOmitChunkFromSearchIndex.html#ordersAPILimitations)for more information). For this reason, it is particularly important that you use the menus API to confirm the availability of a menu before you place an order from it.


- The `minSelections`and `maxSelections`values of the [ModifierGroup](https://doc.toasttab.com/openapi/menusv3/tag/Data-definitions/schema/ModifierGroup/)object. The orders API rejects an order if at least one menu item selection has a modifier group with minimum or maximum selection requirements and those requirements have not been met for that menu item.


- The `requiredMode`value of the [ModifierGroup](https://doc.toasttab.com/openapi/menusv3/tag/Data-definitions/schema/ModifierGroup/)object. The orders API rejects an order if at least one menu item selection has a required modifier group and there is no modifier option from that group specified for the menu item.


- The `isMultiSelect`value of the [ModifierGroup](https://doc.toasttab.com/openapi/menusv3/tag/Data-definitions/schema/ModifierGroup/)object. The orders API rejects an order if at least one menu item selection has a modifier group whose `isMultiSelect`value is FALSE, meaning only one modifier option may be chosen from the group, and more than one modifier option has been specified from that modifier group for the menu item.


- The `isDefault`value of the [ModifierOption](https://doc.toasttab.com/openapi/menusv3/tag/Data-definitions/schema/ModifierOption/)object. The orders API *does not validate*against the `isDefault`value, meaning it is possible to submit an order for a menu item that has a default modifier and that default modifier has been omitted. To avoid issues with default modifiers, your integration should inspect each modifier option's `isDefault`value and, if `isDefault`is set to `True`, include that modifier option by default for the parent menu item on the online ordering site. You should also provide guests with the ability to remove a default modifier from its parent menu item. For example, if a burger includes lettuce and tomato as default modifiers then, by default, your online ordering site should show lettuce and tomato as modifier options on the burger and guests should have the ability to exclude these options from their burger.


- The `isDiscountable`value of the [MenuItem](https://doc.toasttab.com/openapi/menusv3/tag/Data-definitions/schema/MenuItem/)object. The orders API *does not validate*against the `isDiscountable`value. If you submit an order that applies a discount to a menu item whose `isDiscountable`value is FALSE, the orders API will not fail the order but it will set the discount amount on the menu item to $0.00. If you are using the menus API to build an ordering application, be sure to inspect the `isDiscountable`value of the menu items to ensure that your ordering application does not allow an item to be discounted if its `isDiscountable`value is FALSE.


- The `pricingStrategy`value of the [MenuItem](https://doc.toasttab.com/openapi/menusv3/tag/Data-definitions/schema/MenuItem/)object. For menu items that use the Open Price pricing strategy, the expectation is that the price is provided to the Toast platform at the time the item is ordered. If you are injecting orders into the Toast platform using the orders API, you must include the price for an Open Price menu item in the [openPriceAmount value of the Selection object](https://doc.toasttab.com/openapi/orders/tag/Data-definitions/schema/Selection/). You can inspect the `pricingStrategy`value of your menu items to determine if any of them use the OPEN_PRICE pricing strategy. If so, be sure to include pricing information for those items in the injected order.



You should also be aware that the orders API and the menus API use slightly different names for the values that make up an order, as shown in the table below.

| Value name in orders API | Value name in menus API | 
| --- | --- |
| itemGroup | menuGroups | 
| item | menuItem | 
| optionGroup | modifierGroup | 
| item | modifierOption | 

