---
title: "Pricing menu items"
id: adminPricingMenuItems
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminMenuPricingOmitChunkFromSearchIndex.md
parentSectionTitle: "Menu pricing"
previousSectionFile: adminGuide-adminNoteAboutPublishingPrices.md
previousSectionTitle: "Note about publishing prices"
nextSectionFile: adminGuide-adminPricingModifierOptions.md
nextSectionTitle: "Pricing modifiers"
excerpt: "When pricing the menu items in a menu group, you can choose to either:"
keywords: ["pricing", "menu", "items"]
procedures: 0
codeExamples: 0
---

When pricing the menu items in a menu group, you can choose to either:

- [Set a price on the menu group and then configure the group's menu items to inherit that price.](adminGuide-adminPricingMenuItems#adminSettingPricesAtTheMenuGroupLevel)


- [Price the menu items in the group individually.](adminGuide-adminPricingMenuItems#adminSettingPricesOnIndividualMenuItems)



If you choose the first approach, where menu items inherit their prices from their parent menu groups, you can also choose to override the menu group price and set a different price for specific menu items in the group. For example, you can have a Sandwiches menu group where all sandwiches are $7 with the exception of a Daily Specials Sandwich that is $6.

For both approaches, you can choose to use either a [pricing strategy](adminGuide-adminPricingStrategies), such as base price, menu-specific price or time-specific price, or you can use a [price level](adminGuide-adminUsingPriceLevels) to set your prices.

When pricing menu items that belong to multiple menu groups, there are some requirements to keep in mind:

- Menu items can belong to multiple menu groups. If you configure a menu item to inherit its price from its parent menu groups, then you must also make sure you have group-level prices for all of the item's parent menu groups.


- If you configure the menu item to have its own individual price, that price will override any group-level prices set for any of the item's parent menu groups.



## Setting prices at the menu group level

If all, or most, of the menu items in a menu group have the same price, as a best practice you should set a price at the menu group level. If necessary, you can override this price for specific menu items within the group.

The Items section on a menu group details page displays the menu items contained in the menu group. Menu items that inherit their price from the menu group display "inherited" in the Price column. A menu item that does not display "inherited" in the Price column is priced individually. Also, when the menu group has items that are priced individually, a message appears in the Pricingsection that says "Some of this group's items do not inherit pricing". You can click the Show button in that message to view a list of individually priced items.

![Example of the banner displayed for items that do not inherit their prices from a menu group.](https://doc.toasttab.com/doc/media/pricing-showing-price-inheritance.png)

**Procedure 8.111. To set a menu group-level price**

1. [Access Toast Web ](adminGuide-adminAccessToastAdminBackend).


2. Choose Menus &gt; Bulk management &gt; Advanced properties to open the Advanced properties page.


3. Expand the menus and menu groups on the Advanced properties page to locate the menu group you want to edit.


4. Click the menu group's name to view its details page.


5. In the Pricing section, set Menu group provides pricing to Yes.



> **Note**
> 
> Any menu items you create after setting this option to Yes automatically inherit their prices from the menu group. If most of a menu group's items will inherit their prices, it is most efficient to set this option to Yes before adding the menu items.



6. Set the pricing for the menu group. You can choose a pricing strategy ([Base Price](adminGuide-adminBasePrice), [Size Price](adminGuide-adminSizePrice), [Time Specific Price](adminGuide-adminTimeSpecificPrice), [Open Price](adminGuide-adminOpenPrice)) or use [price levels](adminGuide-adminUsingPriceLevels).


7. Save your changes.

Next, configure each of the group's menu items to either inherit their price from the menu group or specify their own price.


8. To configure a menu item to inherit its price from its parent menu group:

- In the Items section of the menu group details page, click a menu item name to view its details page.


- In the Pricing section, set Pricing Provider to Menu group provides pricing.



> **Note**
> 
> If the menu item belongs to any other menu groups and those menu groups do not have group-level pricing configured, the Toast platform displays a message that says "&lt;menu-group-name&gt; does not provide pricing information" to inform you of the issue.



- Save your changes.


- Repeat this procedure with any other menu items that need to inherit their prices.




9. To configure a menu item to override the menu group's price with its own individual price:

- In the Items section of the menu group details page, click a menu item name to view its details page.


- In the Pricing section, set Pricing Provider to Specify pricing on this item.


- Set the price for the menu item. You can choose a pricing strategy ([Base Price](adminGuide-adminBasePrice), [Size Price](adminGuide-adminSizePrice), [Menu Specific Price](adminGuide-adminMenuSpecificPrice), [Time Specific Price](adminGuide-adminTimeSpecificPrice), [Open Price](adminGuide-adminOpenPrice), [Location Specific Price](adminGuide-adminLocationSpecificPrice)) or use [price levels](adminGuide-adminUsingPriceLevels).



> **Note**
> 
> If the menu item belongs to any menu groups that use group-level pricing, the Toast platform displays the message "This overrides group-level pricing provided by &lt;menu-group-name&gt;" to inform you of the override.



- Save your changes.


- Repeat this procedure with any other menu items that need to override the menu group's price.




10. [If you are done editing prices for your menus, publish your changes.](adminGuide-adminNoteAboutPublishingPrices)



## Setting prices on individual menu items

If all of the menu items in a menu group have a different price, as a best practice you should specify prices on the individual menu items.

**Procedure 8.112. To set prices on individual menu items**

1. [Access Toast Web ](adminGuide-adminAccessToastAdminBackend).


2. Choose Menus &gt; Bulk management &gt; Advanced properties to open the Advanced properties page.


3. Expand the menus and menu groups on the Advanced properties page to locate the menu group that contains the menu items you want to edit.


4. Click the menu group's name to view its details page.


5. In the Pricing section, set Menu group provides pricing to No. (No is the default.)

Next, you set the prices on each of the menu items contained in the group.


6. In the Items section, click a menu item's name to view its details page.


7. In the Pricing section, set Pricing Provider to Specify pricing on this item.



> **Note**
> 
> If the menu item belongs to any other menu groups that use menu group-level pricing, the Toast platform displays the message **`This overrides group-level pricing provided by \<menu-group-name\>`** to inform you of the override.



8. Set the price for the menu item. You can choose a pricing strategy ([Base Price](adminGuide-adminBasePrice), [Size Price](adminGuide-adminSizePrice), [Menu Specific Price](adminGuide-adminMenuSpecificPrice), [Time Specific Price](adminGuide-adminTimeSpecificPrice), [Open Price](adminGuide-adminOpenPrice), [Location Specific Price](adminGuide-adminLocationSpecificPrice)) or use [price levels](adminGuide-adminUsingPriceLevels).


9. Save your changes.


10. Repeat these steps for the other menu items in the menu group.


11. [If you are done editing prices for your menus, publish your changes.](adminGuide-adminNoteAboutPublishingPrices)



