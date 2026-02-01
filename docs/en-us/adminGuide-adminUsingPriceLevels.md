---
title: "Using price levels"
id: adminUsingPriceLevels
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminMenuPricingOmitChunkFromSearchIndex.md
parentSectionTitle: "Menu pricing"
previousSectionFile: adminGuide-adminUsingThePriceEditor.md
previousSectionTitle: "Using the price editor"
nextSectionFile: adminGuide-adminDiscountsAndPricing.md
nextSectionTitle: "Discounts and pricing"
excerpt: "Price levels..."
keywords: [price,levels]
procedures: 0
codeExamples: 0
---

### Using price levels

Price levels allow you to quickly price menu items or groups that all share the same price. You create a price level, and then assign it to the menu items and groups that will use it. For example, all bottled beers are $5 and all draft beers are $6. To change the price of the menu items and groups that use a price level, you only need to change the price level itself. This eliminates the need to edit the price for each individual menu group or item.

#### Creating and assigning price levels

To use a price level, you must first create it, and then you assign it to the menu items and groups that will use it.

**Procedure 8.118. To create a price level**

1. [Access Toast Web ](adminAccessToastAdminBackend.html).


2. Choose Menus > Settings > Price levels to open the Price levelspage.


3. In the price levels grid, click Add to create a new price level.


4. Enter a name and a price for the price level.


5. Repeat these steps to create additional price levels as needed.


6. Save and publish your changes.


7. [Assign your price levels to the menu items and groups that will use them.](adminUsingPriceLevels.html#adminToAssignAPriceLevelToAMenuItem)



**Procedure 8.119. To assign a price level to a menu item**

1. [Access Toast Web ](adminAccessToastAdminBackend.html).


2. Choose Menus > Bulk management > Advanced properties to open the Advanced properties page.


3. Expand the menus and menu groups on the Advanced Properties page to locate the menu item you want to edit.


4. Click the name of the menu item you want to edit to see its details page.


5. In the Pricing section, set Pricing Provider to Price level, and choose a price level.


6. Save your changes.


7. [If you are done editing prices for your menus, publish your changes.](adminNoteAboutPublishingPrices.html)



**Procedure 8.120. To assign a price level to a menu group**

1. [Access Toast Web ](adminAccessToastAdminBackend.html).


2. Choose Menus > Bulk management > Advanced properties to open the Advanced properties page.


3. Expand the menus and menu groups on the Advanced properties page to locate the menu group you want to edit.


4. Click the name of the menu group you want to edit to see its details page.


5. In the Pricing section, set Menu group provides pricing to Yes.


6. Set Pricing Provider to Price level, and choose a price level.


7. Save your changes.


8. [If you are done editing prices for your menus, publish your changes.](adminNoteAboutPublishingPrices.html)



#### Using price levels with other pricing strategies

By default, price levels use the Base Price pricing strategy. Price levels can also be combined with other pricing strategies, such as size pricing, menu-specific pricing, or time-specific pricing. A common approach is to use price levels with time-specific pricing. For example, a bakery might offer muffins for $3, but from 4 to 6p.m. the muffins are $1 cheaper. In this scenario, you could apply time-specific pricing to the price level, so that between the hours of 4 to 6p.m., the price would drop from $3 to $2

**Procedure 8.121. To change the pricing strategy of a price level**

1. [Access Toast Web ](adminAccessToastAdminBackend.html).


2. Choose Menus > Settings > Price levels to open the Price levelspage.


3. Click the name of a price level to view its details page.


4. From Pricing Strategy settings, select your pricing strategy and configure its details. The pricing strategies include [Base Price](adminBasePrice.html), [Size Price](adminSizePrice.html#adminConfiguringSizePricingOnMenuGroupsAndMenuItems), [Menu Specific Price](adminMenuSpecificPrice.html), [Time Specific Price](adminTimeSpecificPrice.html), and [Open Price](adminOpenPrice.html).


5. Save your changes.


6. [If you are done editing prices for your menus, publish your changes.](adminNoteAboutPublishingPrices.html)



