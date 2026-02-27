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
      <th className=""><div className="">Value name</div></th>
      <th className=""><div className="">Definition</div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className=""><div className=""><code className="">restaurantGuid</code></div></td>
      <td className=""><div className="">The unique identifier assigned to the restaurant by the Toast platform.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><code className="">restaurantName</code></div></td>
      <td className=""><div className="">The restaurant’s name.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><code className="">restaurantLocationName</code></div></td>
      <td className=""><div className="">The restaurant’s location name.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><code className="">restaurantLocationCode</code></div></td>
      <td className=""><div className="">The restaurant’s location code.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><code className="">businessDate</code></div></td>
      <td className=""><div className="">The calendar date of the associated order data, in <code className="">YYYYMMDD</code> format.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><code className="">netSalesAmount</code></div></td>
      <td className=""><div className="">The total sales, excluding tax, gratuity, tips, discounts, refunds, and deferred amounts. When grouping by <code className="">MENU</code>, <code className="">MENU_GROUP</code>, or <code className="">MENU_ITEM</code>, this is the net sales for the associated menu item or items, including any modifiers. When grouping by <code className="">MODIFIER</code>, this is the net sales for the modifier. </div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><code className="">grossSalesAmount</code></div></td>
      <td className=""><div className="">The total sales, including discounts and refunds. When grouping by <code className="">MENU</code>, <code className="">MENU_GROUP</code>, or <code className="">MENU_ITEM</code>, this is the gross sales for the associated menu item or items, including any modifiers. When grouping by <code className="">MODIFIER</code>, this is the gross sales for the modifier. </div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><code className="">discountAmount</code></div></td>
      <td className=""><div className="">The total amount of discounts. When grouping by <code className="">MENU</code>, <code className="">MENU_GROUP</code>, or <code className="">MENU_ITEM</code>, this is the discount amount for the associated menu item or items, including any modifiers. When grouping by <code className="">MODIFIER</code>, this is the discount amount for the modifier. </div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><code className="">refundAmount</code></div></td>
      <td className=""><div className="">The total amount of refunded sales. When grouping by <code className="">MENU</code>, <code className="">MENU_GROUP</code>, or <code className="">MENU_ITEM</code>, this is the refund amount for the associated menu item or items, including any modifiers. When grouping by <code className="">MODIFIER</code>, this is the refund amount for the modifier. </div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><code className="">voidAmount</code></div></td>
      <td className=""><div className="">The total amount of voided sales. When grouping by <code className="">MENU</code>, <code className="">MENU_GROUP</code>, or <code className="">MENU_ITEM</code>, this is the void amount for the associated menu item or items, including any modifiers. When grouping by <code className="">MODIFIER</code>, this is the void amount for the modifier. </div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><code className="">quantitySold</code></div></td>
      <td className=""><div className="">The number of menu entities sold. This number includes items that were made but later refunded. When grouping by <code className="">MENU</code>, <code className="">MENU_GROUP</code>, or <code className="">MENU_ITEM</code>, this is the count of the associated menu item or items and does not count modifiers separately. When grouping by <code className="">MODIFIER</code>, this is the count of the modifier.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><code className="">averagePrice</code></div></td>
      <td className=""><div className="">The average price of the menu entity. When grouping by <code className="">MENU</code>, <code className="">MENU_GROUP</code>, or <code className="">MENU_ITEM</code>, this is the average price for the associated menu item or items, including any modifiers. When grouping by <code className="">MODIFIER</code>, this is the average price for the modifier. </div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><code className="">wasteCount</code></div></td>
      <td className=""><div className="">The number of menu entities tracked as food waste. When grouping by <code className="">MENU</code>, <code className="">MENU_GROUP</code>, or <code className="">MENU_ITEM</code>, this is the count of the associated menu item or items and does not count modifiers separately. When grouping by <code className="">MODIFIER</code>, this is the count of the modifier.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><code className="">wasteAmount</code></div></td>
      <td className=""><div className="">The total amount tracked as food waste. When grouping by <code className="">MENU</code>, <code className="">MENU_GROUP</code>, or <code className="">MENU_ITEM</code>, this is the total price for the menu item or items, including any modifiers. When grouping by <code className="">MODIFIER</code>, this is the total price for the modifier. </div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><code className="">menuGuid</code></div></td>
      <td className=""><div className="">The identifier for the menu, assigned by the Toast platform. This property appears when the request for menu data includes the <code className="">groupBy</code> property with value <code className="">MENU</code>.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><code className="">menuName</code></div></td>
      <td className=""><div className="">The name of the menu. This property appears when the request for menu data includes the <code className="">groupBy</code> property with value <code className="">MENU</code>.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><code className="">menuGroupGuid</code></div></td>
      <td className=""><div className="">The identifier for the menu group, assigned by the Toast platform. This property appears when the request for menu data includes the <code className="">groupBy</code> property with value <code className="">MENU_GROUP</code>.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><code className="">menuGroupName</code></div></td>
      <td className=""><div className="">The name of the menu group. This property appears when the request for menu data includes the <code className="">groupBy</code> property with value <code className="">MENU_GROUP</code>.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><code className="">menuItemGuid</code></div></td>
      <td className=""><div className="">The identifier for the menu item, assigned by the Toast platform. This property appears when the request for menu data includes the <code className="">groupBy</code> property with value <code className="">MENU_ITEM</code>.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><code className="">menuItemName</code></div></td>
      <td className=""><div className="">The name of the menu item. This property appears when the request for menu data includes the <code className="">groupBy</code> property with value <code className="">MENU_ITEM</code>.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><code className="">modifierGuid</code></div></td>
      <td className=""><div className="">The identifier for the modifier, assigned by the Toast platform. This property appears when the request for menu data includes the <code className="">groupBy</code> property with value <code className="">MODIFIER</code>.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><code className="">modifierName</code></div></td>
      <td className=""><div className="">The name of the modifier. This property appears when the request for menu data includes the <code className="">groupBy</code> property with value <code className="">MODIFIER</code>.</div></td>
    </tr>
  </tbody>
</table>
</div>

