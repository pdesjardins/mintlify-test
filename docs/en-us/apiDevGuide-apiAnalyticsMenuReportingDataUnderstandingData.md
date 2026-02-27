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


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className=""><div className=""><p className="text-base leading-relaxed">Value name</p></div></th>
      <th className=""><div className=""><p className="text-base leading-relaxed">Definition</p></div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">restaurantGuid</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The unique identifier assigned to the restaurant by the Toast platform.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">restaurantName</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The restaurant’s name.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">restaurantLocationName</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The restaurant’s location name.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">restaurantLocationCode</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The restaurant’s location code.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">businessDate</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The calendar date of the associated order data, in <code className="font-mono text-sm">YYYYMMDD</code> format.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">netSalesAmount</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The total sales, excluding tax, gratuity, tips, discounts, refunds, and deferred amounts. When grouping by <code className="font-mono text-sm">MENU</code>, <code className="font-mono text-sm">MENU_GROUP</code>, or <code className="font-mono text-sm">MENU_ITEM</code>, this is the net sales for the associated menu item or items, including any modifiers. When grouping by <code className="font-mono text-sm">MODIFIER</code>, this is the net sales for the modifier. </p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">grossSalesAmount</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The total sales, including discounts and refunds. When grouping by <code className="font-mono text-sm">MENU</code>, <code className="font-mono text-sm">MENU_GROUP</code>, or <code className="font-mono text-sm">MENU_ITEM</code>, this is the gross sales for the associated menu item or items, including any modifiers. When grouping by <code className="font-mono text-sm">MODIFIER</code>, this is the gross sales for the modifier. </p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">discountAmount</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The total amount of discounts. When grouping by <code className="font-mono text-sm">MENU</code>, <code className="font-mono text-sm">MENU_GROUP</code>, or <code className="font-mono text-sm">MENU_ITEM</code>, this is the discount amount for the associated menu item or items, including any modifiers. When grouping by <code className="font-mono text-sm">MODIFIER</code>, this is the discount amount for the modifier. </p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">refundAmount</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The total amount of refunded sales. When grouping by <code className="font-mono text-sm">MENU</code>, <code className="font-mono text-sm">MENU_GROUP</code>, or <code className="font-mono text-sm">MENU_ITEM</code>, this is the refund amount for the associated menu item or items, including any modifiers. When grouping by <code className="font-mono text-sm">MODIFIER</code>, this is the refund amount for the modifier. </p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">voidAmount</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The total amount of voided sales. When grouping by <code className="font-mono text-sm">MENU</code>, <code className="font-mono text-sm">MENU_GROUP</code>, or <code className="font-mono text-sm">MENU_ITEM</code>, this is the void amount for the associated menu item or items, including any modifiers. When grouping by <code className="font-mono text-sm">MODIFIER</code>, this is the void amount for the modifier. </p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">quantitySold</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The number of menu entities sold. This number includes items that were made but later refunded. When grouping by <code className="font-mono text-sm">MENU</code>, <code className="font-mono text-sm">MENU_GROUP</code>, or <code className="font-mono text-sm">MENU_ITEM</code>, this is the count of the associated menu item or items and does not count modifiers separately. When grouping by <code className="font-mono text-sm">MODIFIER</code>, this is the count of the modifier.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">averagePrice</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The average price of the menu entity. When grouping by <code className="font-mono text-sm">MENU</code>, <code className="font-mono text-sm">MENU_GROUP</code>, or <code className="font-mono text-sm">MENU_ITEM</code>, this is the average price for the associated menu item or items, including any modifiers. When grouping by <code className="font-mono text-sm">MODIFIER</code>, this is the average price for the modifier. </p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">wasteCount</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The number of menu entities tracked as food waste. When grouping by <code className="font-mono text-sm">MENU</code>, <code className="font-mono text-sm">MENU_GROUP</code>, or <code className="font-mono text-sm">MENU_ITEM</code>, this is the count of the associated menu item or items and does not count modifiers separately. When grouping by <code className="font-mono text-sm">MODIFIER</code>, this is the count of the modifier.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">wasteAmount</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The total amount tracked as food waste. When grouping by <code className="font-mono text-sm">MENU</code>, <code className="font-mono text-sm">MENU_GROUP</code>, or <code className="font-mono text-sm">MENU_ITEM</code>, this is the total price for the menu item or items, including any modifiers. When grouping by <code className="font-mono text-sm">MODIFIER</code>, this is the total price for the modifier. </p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">menuGuid</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The identifier for the menu, assigned by the Toast platform. This property appears when the request for menu data includes the <code className="font-mono text-sm">groupBy</code> property with value <code className="font-mono text-sm">MENU</code>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">menuName</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The name of the menu. This property appears when the request for menu data includes the <code className="font-mono text-sm">groupBy</code> property with value <code className="font-mono text-sm">MENU</code>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">menuGroupGuid</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The identifier for the menu group, assigned by the Toast platform. This property appears when the request for menu data includes the <code className="font-mono text-sm">groupBy</code> property with value <code className="font-mono text-sm">MENU_GROUP</code>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">menuGroupName</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The name of the menu group. This property appears when the request for menu data includes the <code className="font-mono text-sm">groupBy</code> property with value <code className="font-mono text-sm">MENU_GROUP</code>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">menuItemGuid</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The identifier for the menu item, assigned by the Toast platform. This property appears when the request for menu data includes the <code className="font-mono text-sm">groupBy</code> property with value <code className="font-mono text-sm">MENU_ITEM</code>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">menuItemName</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The name of the menu item. This property appears when the request for menu data includes the <code className="font-mono text-sm">groupBy</code> property with value <code className="font-mono text-sm">MENU_ITEM</code>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">modifierGuid</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The identifier for the modifier, assigned by the Toast platform. This property appears when the request for menu data includes the <code className="font-mono text-sm">groupBy</code> property with value <code className="font-mono text-sm">MODIFIER</code>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">modifierName</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The name of the modifier. This property appears when the request for menu data includes the <code className="font-mono text-sm">groupBy</code> property with value <code className="font-mono text-sm">MODIFIER</code>.</p></div></td>
    </tr>
  </tbody>
</table>
</div>

