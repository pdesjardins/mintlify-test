---
title: "Using advanced pricing strategies for menu items"
id: adminUsingAdvancedPricingStrategiesForMenuItemsMenuBuilder
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminCreatingYourMenuUsingTheBasicMenuBuilderOmitChunkFromSearchIndex.md
parentSectionTitle: "Menu builder"
previousSectionFile: adminGuide-adminSpecifyingOrderingChannelVisibility.md
previousSectionTitle: "Specifying ordering channel visibility"
nextSectionFile: adminGuide-platformMenuBuilderForMultiLocationOmitChunkFromSearchIndex.md
nextSectionTitle: "Menu builder for multi-location restaurants"
externalReferences: [https://central.toasttab.com/s/article/Shallow-and-Deep-Copying-Menu-Items-and-Modifiers, https://central.toasttab.com/s/article/Quick-Edit-Mode-1492794309057#:~:text=Since%20Toast%20is%20a%20cloud,Quick%20Edit%20Mode%2C%20select%20OK.]
excerpt: "Currently, the menu builder supports setting base prices, size prices, and open prices. You can use the classic menu..."
keywords: ["advanced", "pricing", "strategies", "menu", "items"]
procedures: 3
codeExamples: 0
---

Currently, the menu builder supports setting base prices, size prices, and open prices. You can use the classic menu item detail pages to configure other advanced pricing strategies for your menu items, including time prices, and price levels. You can also use the classic pages to specify that a menu item inherits its price from a menu group. If you set an advanced pricing strategy on a menu item's classic details page, the menu builder will display the pricing strategy's name and the price range for the price (for example, $8.00 - $10.00). If you configure a menu item to inherit its price from a menu group, the menu builder displays a message informing you that you must use the classic page to update the menu item's price, along with a link to the classic page.

It is important to note that not all pricing strategies are supported on all Toast ordering channels. For example, Toast Online Ordering does not support time or open prices so you should not use those pricing strategies for menu items that will be displayed on your Toast Online Ordering website. Before using an advanced pricing strategy, check the table below to ensure that the strategy you want to use is supported by the Toast ordering channels where those menu items will be visible. This table also includes a description of each pricing strategy and the location where you configure it (in the menu builder or in the classic menu item details page). The sections that follow the table describe how to configure each of these pricing strategies.


<table>
  <thead>
    <tr>
      <th>Pricing Strategy</th>
      <th>Description</th>
      <th>Can be used with...</th>
      <th>Configure in...</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Size price</td>
      <td>With size pricing, the price of a menu item changes based on the size chosen for the menu item. For example, a small pizza costs $6 and a large pizza costs $8.</td>
      <td><ul><li>Toast POS app</li><li>Toast Online Ordering</li><li>Toast Takeout (Local by Toast) app</li><li>Toast Kiosk</li><li>Toast Order and Pay</li><li>Online ordering partners (Support can vary by online ordering partner, contact the partner to confirm.)</li></ul></td>
      <td>Menu builder</td>
    </tr>
    <tr>
      <td>Open price</td>
      <td>With open pricing, you manually specify a price for a menu item when that menu item is ordered on the Toast POS app. For example, you may want to set the price of a menu item differently depending on the market price of that menu item on the day that it is ordered.</td>
      <td><ul><li>Toast POS app</li><li>Online ordering partners (Support can vary by online ordering partner, contact the partner to confirm.)</li></ul></td>
      <td>Menu builder</td>
    </tr>
    <tr>
      <td>Menu-specific price</td>
      <td>With menu-specific pricing, the price of a menu item changes based on the menu it was ordered from, for example, a menu item that costs $5 when it is ordered from the Lunch menu and $7 when it is ordered from the Dinner menu.<br/>Menu-specific prices require that the same menu item has been added to multiple menus. Currently, that type of configuration can only be created in the classic menu details pages in Toast Web. For instructions on how to add the same menu item to multiple menus, see this [Adding/Copying Menu Items and Modifiers](https://central.toasttab.com/s/article/Shallow-and-Deep-Copying-Menu-Items-and-Modifiers) in Toast Central.</td>
      <td><ul><li>Toast POS app</li><li>Toast Online Ordering</li><li>Toast Takeout (Local by Toast) app</li><li>Toast Kiosk</li><li>Toast Order and Pay</li><li>Online ordering partners (Support can vary by online ordering partner, contact the partner to confirm.)</li></ul></td>
      <td>Classic menu item details page</td>
    </tr>
    <tr>
      <td>Time price</td>
      <td>With time pricing, you define the price of a menu group or item during specific times of the day. For example, a menu item that costs $10 between noon and 2pm and $12 during the rest of the day. With time pricing, you also specify a base price that functions as a default price for times of day when a time price has not been defined.</td>
      <td><ul><li>Toast POS app</li><li>Toast Online Ordering</li><li>Toast Takeout (Local by Toast) app</li><li>Toast Kiosk</li><li>Toast Order and Pay</li><li>Online ordering partners (Support can vary by online ordering partner, contact the partner to confirm.)</li></ul></td>
      <td>Classic menu item details page</td>
    </tr>
    <tr>
      <td>Price levels</td>
      <td>Price levels allow you to quickly price menu items that all share the same price. You create a price level, and then assign it to the menu items that will use it. For example, all bottled beers are $5 and all draft beers are $6. To change the price of the menu items that use a price level, you only need to change the price level itself. This eliminates the need to edit the price for each individual menu group or item.</td>
      <td><ul><li>Toast POS app</li><li>Toast Kiosk</li><li>Online ordering partners (Support can vary by online ordering partner, contact the partner to confirm.)</li></ul></td>
      <td>Classic menu item details page</td>
    </tr>
  </tbody>
</table>

**Procedure 8.35. To set a size price in the menu builder**

1. On the details page for the [menu group](adminGuide-adminCreatingYourMenuHierarchy#adminToEditAMenuGroup) or [subgroup](adminGuide-adminCreatingYourMenuHierarchy#adminToEditASubgroup) that contains the menu item you want to set size prices for, select Items.


2. Select the edit icon (pencil) for the menu item you want to edit.


3. In the Pricing section, select the Size price strategy. You see a set of rows for defining the size prices. By default, rows are added for Small, Medium, and Large sizes.


4. Optionally, do any of the following to customize the menu item's sizes:

- To change the name of a size, select the name and type a new one.


- To add another size, select Add size price. A new row is added where you can specify the size's name and price.


- To delete a size, select the trash icon next to the size.




5. Enter a price for each size you have defined.


6. Delete any empty size price rows.


7. When you are finished editing the menu item, select Save.


8. Select the X icon in the upper-left corner to return to the menu builder home page.


9. If you are ready for guests and employees to see these menu changes, select Publish all changes, then select Publish again in the Confirm Publish dialog. For more information, see [Understanding when to publish your menu](adminGuide-adminUnderstandingWhenToPublishYourMenu).



**Procedure 8.36. To set an open price in the menu builder**



> **Note**
> 
> For items that have a daily market price, Toast support recommends configuring the item with an open price and then using [Quick Edit](https://central.toasttab.com/s/article/Quick-Edit-Mode-1492794309057#:~:text=Since%20Toast%20is%20a%20cloud,Quick%20Edit%20Mode%2C%20select%20OK.) mode on a Toast POS device to set a price for the item each day. This ensures that the price is accurate and employees don't have to enter a price every time the item is ordered.


1. On the details page for the [menu group](adminGuide-adminCreatingYourMenuHierarchy#adminToEditAMenuGroup) or [subgroup](adminGuide-adminCreatingYourMenuHierarchy#adminToEditASubgroup) that contains the menu item you want to set an open price for, select Items.


2. Select the edit icon (pencil) for the menu item you want to edit.


3. In the Pricing section, select the Open price strategy.


4. Select Save.


5. Select the X icon in the upper-left corner to return to the menu builder home page.


6. If you are ready for guests and employees to see these menu changes, select Publish all changes, then select Publish again in the Confirm Publish dialog. For more information, see [Understanding when to publish your menu](adminGuide-adminUnderstandingWhenToPublishYourMenu).



**Procedure 8.37. To set an advanced price using the classic menu item details page**

1. On the details page for the [menu group](adminGuide-adminCreatingYourMenuHierarchy#adminToEditAMenuGroup) or [subgroup](adminGuide-adminCreatingYourMenuHierarchy#adminToEditASubgroup) that contains the menu item you want to set an advanced price for, select Items.


2. Select the edit icon (pencil) for the menu item you want to edit.


3. Select More item settings to go to the More item settings section, then select More item settings again to view the menu item's classic details page.


4. If you want to use the Menu Specific Priceor Time Specific Price pricing strategy, do the following:

- Leave the Pricing Provider section set to Specify pricing on this item.


- In the Pricing Strategy section, choose the advanced pricing strategy and fill out its configuration details. Click a link below for specific instructions for each strategy type:

- [Menu Specific Price](adminGuide-adminMenuSpecificPrice#adminToCreateMenuSpecificPricesForAMenuItem)


- [Time Specific Price](adminGuide-adminTimeSpecificPrice#adminToCreateTimeSpecificPricesForAMenuGroupOrMenuItem)






5. If you want to use price levels, set the Pricing Provider section to Price level and then choose a price level from the Price Leveldropdown list.



> **Note**
> 
> Price levels must be created before you can assign them to your menu items. Currently, price level creation must be done in the classic menu details pages in Toast Web. For instructions on how to create price levels, see [Using price levels](adminGuide-adminUsingPriceLevels).



6. At the top of the page, select Save.


7. If you are ready for your guests to see these menu changes, select Publish Now in the green banner that appears (see [Understanding when to publish your menu](adminGuide-adminUnderstandingWhenToPublishYourMenu) for more information). If not, skip to the next step.


8. To return to the menu builder, select your browser's back button twice.





> **Note**
> 
> The menu builder does not support pricing at the menu group level yet. You can still assign prices to your menu groups using the classic menu details pages but the group prices you create *will not be shown* in the menu builder. For information on pricing menu groups, see [Setting prices at the menu group level](adminGuide-adminPricingMenuItems#adminSettingPricesAtTheMenuGroupLevel).


