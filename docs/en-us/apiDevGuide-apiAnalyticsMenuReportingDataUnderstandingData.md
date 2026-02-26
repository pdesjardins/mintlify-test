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

Menu reporting data contains objects that correspond to each available restaurant and business date combination. Optionally, you can choose to aggregate the data by menu, menu group, menu item, or modifier. For more information, see [Aggregating the menu reporting data](apiDevGuide-apiAnalyticsMenuReportingDataAggregation). You can also choose to retrieve data for currently inactive restaurants. For more information, see [Viewing inactive restaurant data](apiDevGuide-apiAnalyticsInactiveRestaurantData).

The restaurants included in the menu reporting data can be limited using either the `restaurantIds` or `excludedRestaurantIds` value in the message body. Any restaurants listed with the `restaurantIds` value are included in the menu reporting data, with any restaurants not listed excluded. Any restaurants listed with the `excludedRestaurantIds` value are excluded from the menu reporting data, with any restaurants not listed included. When left blank, all restaurants are included automatically. You can include restaurant GUIDs for only one of these values. For an example that chooses to include specific restaurants, see [Creating a request for menu reporting data](apiDevGuide-apiAnalyticsMenuReportingDataCreateRequest).

The following table specifies the returned set of values in the menu reporting data. The values are listed in the order they appear.


<table>
  <thead>
    <tr>
      <th>Value name</th>
      <th>Definition</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>`restaurantGuid`</td>
      <td>The unique identifier assigned to the restaurant by the Toast platform.</td>
    </tr>
    <tr>
      <td>`restaurantName`</td>
      <td>The restaurant’s name.</td>
    </tr>
    <tr>
      <td>`restaurantLocationName`</td>
      <td>The restaurant’s location name.</td>
    </tr>
    <tr>
      <td>`restaurantLocationCode`</td>
      <td>The restaurant’s location code.</td>
    </tr>
    <tr>
      <td>`businessDate`</td>
      <td>The calendar date of the associated order data, in `YYYYMMDD` format.</td>
    </tr>
    <tr>
      <td>`netSalesAmount`</td>
      <td>The total sales, excluding tax, gratuity, tips, discounts, refunds, and deferred amounts. When grouping by `MENU`, `MENU_GROUP`, or `MENU_ITEM`, this is the net sales for the associated menu item or items, including any modifiers. When grouping by `MODIFIER`, this is the net sales for the modifier. </td>
    </tr>
    <tr>
      <td>`grossSalesAmount`</td>
      <td>The total sales, including discounts and refunds. When grouping by `MENU`, `MENU_GROUP`, or `MENU_ITEM`, this is the gross sales for the associated menu item or items, including any modifiers. When grouping by `MODIFIER`, this is the gross sales for the modifier. </td>
    </tr>
    <tr>
      <td>`discountAmount`</td>
      <td>The total amount of discounts. When grouping by `MENU`, `MENU_GROUP`, or `MENU_ITEM`, this is the discount amount for the associated menu item or items, including any modifiers. When grouping by `MODIFIER`, this is the discount amount for the modifier. </td>
    </tr>
    <tr>
      <td>`refundAmount`</td>
      <td>The total amount of refunded sales. When grouping by `MENU`, `MENU_GROUP`, or `MENU_ITEM`, this is the refund amount for the associated menu item or items, including any modifiers. When grouping by `MODIFIER`, this is the refund amount for the modifier. </td>
    </tr>
    <tr>
      <td>`voidAmount`</td>
      <td>The total amount of voided sales. When grouping by `MENU`, `MENU_GROUP`, or `MENU_ITEM`, this is the void amount for the associated menu item or items, including any modifiers. When grouping by `MODIFIER`, this is the void amount for the modifier. </td>
    </tr>
    <tr>
      <td>`quantitySold`</td>
      <td>The number of menu entities sold. This number includes items that were made but later refunded. When grouping by `MENU`, `MENU_GROUP`, or `MENU_ITEM`, this is the count of the associated menu item or items and does not count modifiers separately. When grouping by `MODIFIER`, this is the count of the modifier.</td>
    </tr>
    <tr>
      <td>`averagePrice`</td>
      <td>The average price of the menu entity. When grouping by `MENU`, `MENU_GROUP`, or `MENU_ITEM`, this is the average price for the associated menu item or items, including any modifiers. When grouping by `MODIFIER`, this is the average price for the modifier. </td>
    </tr>
    <tr>
      <td>`wasteCount`</td>
      <td>The number of menu entities tracked as food waste. When grouping by `MENU`, `MENU_GROUP`, or `MENU_ITEM`, this is the count of the associated menu item or items and does not count modifiers separately. When grouping by `MODIFIER`, this is the count of the modifier.</td>
    </tr>
    <tr>
      <td>`wasteAmount`</td>
      <td>The total amount tracked as food waste. When grouping by `MENU`, `MENU_GROUP`, or `MENU_ITEM`, this is the total price for the menu item or items, including any modifiers. When grouping by `MODIFIER`, this is the total price for the modifier. </td>
    </tr>
    <tr>
      <td>`menuGuid`</td>
      <td>The identifier for the menu, assigned by the Toast platform. This property appears when the request for menu data includes the `groupBy` property with value `MENU`.</td>
    </tr>
    <tr>
      <td>`menuName`</td>
      <td>The name of the menu. This property appears when the request for menu data includes the `groupBy` property with value `MENU`.</td>
    </tr>
    <tr>
      <td>`menuGroupGuid`</td>
      <td>The identifier for the menu group, assigned by the Toast platform. This property appears when the request for menu data includes the `groupBy` property with value `MENU_GROUP`.</td>
    </tr>
    <tr>
      <td>`menuGroupName`</td>
      <td>The name of the menu group. This property appears when the request for menu data includes the `groupBy` property with value `MENU_GROUP`.</td>
    </tr>
    <tr>
      <td>`menuItemGuid`</td>
      <td>The identifier for the menu item, assigned by the Toast platform. This property appears when the request for menu data includes the `groupBy` property with value `MENU_ITEM`.</td>
    </tr>
    <tr>
      <td>`menuItemName`</td>
      <td>The name of the menu item. This property appears when the request for menu data includes the `groupBy` property with value `MENU_ITEM`.</td>
    </tr>
    <tr>
      <td>`modifierGuid`</td>
      <td>The identifier for the modifier, assigned by the Toast platform. This property appears when the request for menu data includes the `groupBy` property with value `MODIFIER`.</td>
    </tr>
    <tr>
      <td>`modifierName`</td>
      <td>The name of the modifier. This property appears when the request for menu data includes the `groupBy` property with value `MODIFIER`.</td>
    </tr>
  </tbody>
</table>

