---
title: "Understanding the menu reporting data"
id: apiAnalyticsMenuReportingDataUnderstandingData
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiAnalyticsMenuReportingDataOmitChunkFromSearchIndex.md
parentSectionTitle: "Menu reporting data"
previousSectionFile: apiDevGuide-apiAnalyticsMenuReportingDataAggregation.md
previousSectionTitle: "Aggregating the menu reporting data"
nextSectionFile: apiDevGuide-apiAnalyticsPayoutReportingDataOmitChunkFromSearchIndex.md
nextSectionTitle: "Payout reporting data"
excerpt: "Menu reporting data contains objects that correspond to each available restaurant and business date combination. Optionally, you can choose to aggregate the data by menu, menu group, menu item, or..."
keywords: ["understanding", "menu", "reporting", "data", "restaurantIds", "excludedRestaurantIds", "restaurantGuid", "restaurantName", "restaurantLocationName", "restaurantLocationCode"]
procedures: 0
codeExamples: 0
---

Menu reporting data contains objects that correspond to each available restaurant and business date combination. Optionally, you can choose to aggregate the data by menu, menu group, menu item, or modifier. For more information, see [Aggregating the menu reporting data](apiAnalyticsMenuReportingDataAggregation.html). You can also choose to retrieve data for currently inactive restaurants. For more information, see [Viewing inactive restaurant data](apiAnalyticsInactiveRestaurantData.html).

The restaurants included in the menu reporting data can be limited using either the `restaurantIds` or `excludedRestaurantIds` value in the message body. Any restaurants listed with the `restaurantIds` value are included in the menu reporting data, with any restaurants not listed excluded. Any restaurants listed with the `excludedRestaurantIds` value are excluded from the menu reporting data, with any restaurants not listed included. When left blank, all restaurants are included automatically. You can include restaurant GUIDs for only one of these values. For an example that chooses to include specific restaurants, see [Creating a request for menu reporting data](apiAnalyticsMenuReportingDataCreateRequest.html).

The following table specifies the returned set of values in the menu reporting data. The values are listed in the order they appear.

| Value name | Definition | 
| --- | --- |
| `restaurantGuid` | The unique identifier assigned to the restaurant by the Toast platform. | 
| `restaurantName` | The restaurant’s name. | 
| `restaurantLocationName` | The restaurant’s location name. | 
| `restaurantLocationCode` | The restaurant’s location code. | 
| `businessDate` | The calendar date of the associated order data, in `YYYYMMDD` format. | 
| `netSalesAmount` | The total sales, excluding tax, gratuity, tips, discounts, refunds, and deferred amounts. When grouping by `MENU`, `MENU_GROUP`, or `MENU_ITEM`, this is the net sales for the associated menu item or items, including any modifiers. When grouping by `MODIFIER`, this is the net sales for the modifier.  | 
| `grossSalesAmount` | The total sales, including discounts and refunds. When grouping by `MENU`, `MENU_GROUP`, or `MENU_ITEM`, this is the gross sales for the associated menu item or items, including any modifiers. When grouping by `MODIFIER`, this is the gross sales for the modifier.  | 
| `discountAmount` | The total amount of discounts. When grouping by `MENU`, `MENU_GROUP`, or `MENU_ITEM`, this is the discount amount for the associated menu item or items, including any modifiers. When grouping by `MODIFIER`, this is the discount amount for the modifier.  | 
| `refundAmount` | The total amount of refunded sales. When grouping by `MENU`, `MENU_GROUP`, or `MENU_ITEM`, this is the refund amount for the associated menu item or items, including any modifiers. When grouping by `MODIFIER`, this is the refund amount for the modifier.  | 
| `voidAmount` | The total amount of voided sales. When grouping by `MENU`, `MENU_GROUP`, or `MENU_ITEM`, this is the void amount for the associated menu item or items, including any modifiers. When grouping by `MODIFIER`, this is the void amount for the modifier.  | 
| `quantitySold` | The number of menu entities sold. This number includes items that were made but later refunded. When grouping by `MENU`, `MENU_GROUP`, or `MENU_ITEM`, this is the count of the associated menu item or items and does not count modifiers separately. When grouping by `MODIFIER`, this is the count of the modifier. | 
| `averagePrice` | The average price of the menu entity. When grouping by `MENU`, `MENU_GROUP`, or `MENU_ITEM`, this is the average price for the associated menu item or items, including any modifiers. When grouping by `MODIFIER`, this is the average price for the modifier.  | 
| `wasteCount` | The number of menu entities tracked as food waste. When grouping by `MENU`, `MENU_GROUP`, or `MENU_ITEM`, this is the count of the associated menu item or items and does not count modifiers separately. When grouping by `MODIFIER`, this is the count of the modifier. | 
| `wasteAmount` | The total amount tracked as food waste. When grouping by `MENU`, `MENU_GROUP`, or `MENU_ITEM`, this is the total price for the menu item or items, including any modifiers. When grouping by `MODIFIER`, this is the total price for the modifier.  | 
| `menuGuid` | The identifier for the menu, assigned by the Toast platform. This property appears when the request for menu data includes the `groupBy` property with value `MENU`. | 
| `menuName` | The name of the menu. This property appears when the request for menu data includes the `groupBy`property with value `MENU`. | 
| `menuGroupGuid` | The identifier for the menu group, assigned by the Toast platform. This property appears when the request for menu data includes the `groupBy` property with value `MENU_GROUP`. | 
| `menuGroupName` | The name of the menu group. This property appears when the request for menu data includes the `groupBy` property with value `MENU_GROUP`. | 
| `menuItemGuid` | The identifier for the menu item, assigned by the Toast platform. This property appears when the request for menu data includes the `groupBy` property with value `MENU_ITEM`. | 
| `menuItemName` | The name of the menu item. This property appears when the request for menu data includes the `groupBy` property with value `MENU_ITEM`. | 
| `modifierGuid` | The identifier for the modifier, assigned by the Toast platform. This property appears when the request for menu data includes the `groupBy` property with value `MODIFIER`. | 
| `modifierName` | The name of the modifier. This property appears when the request for menu data includes the `groupBy` property with value `MODIFIER`. | 

