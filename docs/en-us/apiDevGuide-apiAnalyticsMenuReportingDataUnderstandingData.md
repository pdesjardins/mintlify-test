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
      <td><code>restaurantGuid</code></td>
      <td>The unique identifier assigned to the restaurant by the Toast platform.</td>
    </tr>
    <tr>
      <td><code>restaurantName</code></td>
      <td>The restaurant’s name.</td>
    </tr>
    <tr>
      <td><code>restaurantLocationName</code></td>
      <td>The restaurant’s location name.</td>
    </tr>
    <tr>
      <td><code>restaurantLocationCode</code></td>
      <td>The restaurant’s location code.</td>
    </tr>
    <tr>
      <td><code>businessDate</code></td>
      <td>The calendar date of the associated order data, in <code>YYYYMMDD</code> format.</td>
    </tr>
    <tr>
      <td><code>netSalesAmount</code></td>
      <td>The total sales, excluding tax, gratuity, tips, discounts, refunds, and deferred amounts. When grouping by <code>MENU</code>, <code>MENU_GROUP</code>, or <code>MENU_ITEM</code>, this is the net sales for the associated menu item or items, including any modifiers. When grouping by <code>MODIFIER</code>, this is the net sales for the modifier. </td>
    </tr>
    <tr>
      <td><code>grossSalesAmount</code></td>
      <td>The total sales, including discounts and refunds. When grouping by <code>MENU</code>, <code>MENU_GROUP</code>, or <code>MENU_ITEM</code>, this is the gross sales for the associated menu item or items, including any modifiers. When grouping by <code>MODIFIER</code>, this is the gross sales for the modifier. </td>
    </tr>
    <tr>
      <td><code>discountAmount</code></td>
      <td>The total amount of discounts. When grouping by <code>MENU</code>, <code>MENU_GROUP</code>, or <code>MENU_ITEM</code>, this is the discount amount for the associated menu item or items, including any modifiers. When grouping by <code>MODIFIER</code>, this is the discount amount for the modifier. </td>
    </tr>
    <tr>
      <td><code>refundAmount</code></td>
      <td>The total amount of refunded sales. When grouping by <code>MENU</code>, <code>MENU_GROUP</code>, or <code>MENU_ITEM</code>, this is the refund amount for the associated menu item or items, including any modifiers. When grouping by <code>MODIFIER</code>, this is the refund amount for the modifier. </td>
    </tr>
    <tr>
      <td><code>voidAmount</code></td>
      <td>The total amount of voided sales. When grouping by <code>MENU</code>, <code>MENU_GROUP</code>, or <code>MENU_ITEM</code>, this is the void amount for the associated menu item or items, including any modifiers. When grouping by <code>MODIFIER</code>, this is the void amount for the modifier. </td>
    </tr>
    <tr>
      <td><code>quantitySold</code></td>
      <td>The number of menu entities sold. This number includes items that were made but later refunded. When grouping by <code>MENU</code>, <code>MENU_GROUP</code>, or <code>MENU_ITEM</code>, this is the count of the associated menu item or items and does not count modifiers separately. When grouping by <code>MODIFIER</code>, this is the count of the modifier.</td>
    </tr>
    <tr>
      <td><code>averagePrice</code></td>
      <td>The average price of the menu entity. When grouping by <code>MENU</code>, <code>MENU_GROUP</code>, or <code>MENU_ITEM</code>, this is the average price for the associated menu item or items, including any modifiers. When grouping by <code>MODIFIER</code>, this is the average price for the modifier. </td>
    </tr>
    <tr>
      <td><code>wasteCount</code></td>
      <td>The number of menu entities tracked as food waste. When grouping by <code>MENU</code>, <code>MENU_GROUP</code>, or <code>MENU_ITEM</code>, this is the count of the associated menu item or items and does not count modifiers separately. When grouping by <code>MODIFIER</code>, this is the count of the modifier.</td>
    </tr>
    <tr>
      <td><code>wasteAmount</code></td>
      <td>The total amount tracked as food waste. When grouping by <code>MENU</code>, <code>MENU_GROUP</code>, or <code>MENU_ITEM</code>, this is the total price for the menu item or items, including any modifiers. When grouping by <code>MODIFIER</code>, this is the total price for the modifier. </td>
    </tr>
    <tr>
      <td><code>menuGuid</code></td>
      <td>The identifier for the menu, assigned by the Toast platform. This property appears when the request for menu data includes the <code>groupBy</code> property with value <code>MENU</code>.</td>
    </tr>
    <tr>
      <td><code>menuName</code></td>
      <td>The name of the menu. This property appears when the request for menu data includes the <code>groupBy</code> property with value <code>MENU</code>.</td>
    </tr>
    <tr>
      <td><code>menuGroupGuid</code></td>
      <td>The identifier for the menu group, assigned by the Toast platform. This property appears when the request for menu data includes the <code>groupBy</code> property with value <code>MENU_GROUP</code>.</td>
    </tr>
    <tr>
      <td><code>menuGroupName</code></td>
      <td>The name of the menu group. This property appears when the request for menu data includes the <code>groupBy</code> property with value <code>MENU_GROUP</code>.</td>
    </tr>
    <tr>
      <td><code>menuItemGuid</code></td>
      <td>The identifier for the menu item, assigned by the Toast platform. This property appears when the request for menu data includes the <code>groupBy</code> property with value <code>MENU_ITEM</code>.</td>
    </tr>
    <tr>
      <td><code>menuItemName</code></td>
      <td>The name of the menu item. This property appears when the request for menu data includes the <code>groupBy</code> property with value <code>MENU_ITEM</code>.</td>
    </tr>
    <tr>
      <td><code>modifierGuid</code></td>
      <td>The identifier for the modifier, assigned by the Toast platform. This property appears when the request for menu data includes the <code>groupBy</code> property with value <code>MODIFIER</code>.</td>
    </tr>
    <tr>
      <td><code>modifierName</code></td>
      <td>The name of the modifier. This property appears when the request for menu data includes the <code>groupBy</code> property with value <code>MODIFIER</code>.</td>
    </tr>
  </tbody>
</table>

