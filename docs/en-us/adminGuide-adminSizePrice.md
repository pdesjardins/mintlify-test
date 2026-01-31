---
title: "Size price"
id: adminSizePrice
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminPricingStrategyDetailsOmitChunkFromSearchIndex.md
parentSectionTitle: "Pricing strategies"
previousSectionFile: adminGuide-adminSequencePrice.md
previousSectionTitle: "Sequence price"
nextSectionFile: adminGuide-adminSizeSequencePrice.md
nextSectionTitle: "Size/sequence price"
excerpt: "Applies to: Menu items, modifier groups, modifier item references"
keywords: [size,price,Applies to:]
procedures: 0
codeExamples: 0
---

### Size price

**Applies to:** Menu items, modifier groups, [modifier item references](adminPricingModifierOptions.html#adminUnderstandingAModifierOptionsItemReference)



> **Note**
> 
> Size pricing for menu items is supported on all product channels.
> Size pricing for modifiers is supported on the Toast POS app, Toast Online Ordering, and in the menu data returned to online ordering partners. It is not supported on the Toast Takeout (Local by Toast) app, Toast Order and Pay, and Toast Kiosk. For more information, see [Toast product channel support for advanced pricing features](adminToastProductChannelSupportForAdvancedPricingFeatures.html).


With size pricing, the price of a menu item changes based on the size chosen for the menu item. For example, a small pizza costs $10 and a large pizza costs $14.

The effect of size pricing on modifiers depends on the configuration you have specified. There are two possible scenarios:

- The price of a modifier changes based on the size of the menu item it modifies, for example, toppings on a small pizza cost $2 and toppings on a large pizza cost $3.


- The price of a modifier changes based on the size chosen for the modifier itself, for example, the small size of pepperoni costs $1.50 and the large size costs $2.50.



In both scenarios, you configure the prices for the modifiers separately from the price of the menu item.

For more information on configuring and using size prices, see the following topics:

- [Using size pricing in the Toast POS app](adminSizePrice.html#adminUsingSizePricingInTheToastPosApp)


- [Configuring size pricing on menu groups and menu items](adminSizePrice.html#adminConfiguringSizePricingOnMenuGroupsAndMenuItems)


- [Configuring size pricing on modifier groups and modifiers](adminSizePrice.html#adminConfiguringSizePricingOnModifierGroupsAndModifierOptions)



#### Using size pricing in the Toast POS app

This section provides an example of the most common scenario when working with size pricing in the Toast POS app. The configuration for this example sets size-based prices on the Cheese Pizza menu item ($10 for a small and $14 for a large). It also sets size-based prices on the Toppings modifier group and configures the group so that the price of a modifier in the group is determined by the size of the menu item it is applied to. In this case, that means toppings on a small pizza are $2 and toppings on a large pizza are $3.

When you select a menu item in the Toast POS app that has size pricing enabled, you see a Size button in the list of modifier group buttons and it is selected by default, allowing you to immediately specify the size of the menu item you are adding to the order:

![Toast POS app example showing the Size button you use to modify the size of a menu item.](https://doc.toasttab.com/doc/media/pricing-size-price-mod-grp-size-button.PNG)

Tap a size option, for example, Small. The menu item is added to the order and priced according to the size you chose.

![Toast POS app example showing a menu item that is priced according to its size.](https://doc.toasttab.com/doc/media/pricing-size-price-mod-grp-sm-pizza.PNG)

To add a modifier to the menu item, tap the modifier group name, then tap a modifier. The modifier is added to the menu item and priced according to the size of the menu item. For example, in the illustration below, you ordered one small cheese pizza and then chose Toppings of Pepperoni and Onions. You then ordered a large cheese pizza and added Toppings of Sausage and Mushrooms. The toppings on the small pizza cost $2 while toppings on the large pizza cost $3.

![Toast POS app example showing two menu items with different sizes and their modifiers, which are priced according to size.](https://doc.toasttab.com/doc/media/pricing-size-price-mod-grp-sm-and-lg-pizzas.PNG)

Tap Done when you are finished specifying the modifiers for a menu item to add it to the order.

#### Configuring size pricing on menu groups and menu items

You create size prices for a menu group or item on the group or item's details page. After you have created size prices for a menu item, you can view them in the Items grid that appears on the details page for any of the item's parent menu groups. However, the size prices are not editable from the Items grid. To edit a size price, you can either return to the menu group or item's details page and edit it there, or, edit it on the [Price editor](adminUsingThePriceEditor.html) page.

**Procedure 8.129. To enable size pricing on a menu group or item**

1. In the Pricing Strategy section of the menu group or item's details page, select Size Price. The Size Prices grid appears. Each row in the grid represents a size.


2. Define your sizes by entering a size name in the Size column and a corresponding price for the size in the Price column. You must enter a price for each size you create.


3. To add additional rows to the grid, click the Add button.


4. To reorder sizes:

- Click the Edit button. A new column appears to the left with the reordering icon.

![Example of the Size Prices grid showing the location of the reordering icon.](https://doc.toasttab.com/doc/media/pricing-reorder-column.png)


- Click the reordering icon for a row and drag it to its new location.


- Click Done when you are finished reordering.




5. To delete sizes:

- Click the Edit button. A new column appears to the right with the trash can icon.


- Click the trash can icon for the row you want to delete.


- Click Done when you are finished deleting.




6. Save your changes.


7. [If you are done editing prices for your menus, publish your changes.](adminNoteAboutPublishingPrices.html)



#### Configuring size pricing on modifier groups and modifiers

For modifiers, size pricing can be configured at either the modifier group level or the individual modifier level:

- If you configure size pricing at the modifier group level, all modifiers in the group use the same size-based prices. For example, all of the toppings in a Toppings modifier group cost $0.50 for a small pizza, $1 for a medium pizza, and $1.50 for a large pizza. When you configure size pricing at the modifier group level, the size of the modifier is always dictated by the size of the menu item it is applied to, for example, if you order a small pizza and add a topping to it, the small size price is used for that topping.


- If you configure size pricing at the individual modifier level, modifiers in a group can set their own size-based prices. For example, pepperoni costs $1 on a small pizza and $2 on a large while mushrooms costs $0.50 on a small pizza and $1 on a large. When you configure size pricing at the individual modifier level, you can choose whether the size of the modifier is dictated by the size of the menu item it is applied to or if the size of the modifier can be specified independently from the menu item size on the Toast POS app.



##### Creating matching sizes for menu items and modifiers

For scenarios where the price of a modifier is determined by the size of the menu item it is applied to, you must specify sizes on the individual menu items and then create corresponding sizes for the modifiers themselves. The sizes on the menu items and modifiers must match exactly, both in the number of sizes and the text used for the size names. For example, this configuration is acceptable:

| Menu Item Sizes | Modifier Sizes | 
| --- | --- |
| Small | Small | 
| Medium | Medium | 
| Large | Large | 
| XLarge | XLarge | 

This configuration *is not acceptable*because the size names not match:

| Menu Item Sizes | Modifier Sizes | 
| --- | --- |
| Small | Sm | 
| Medium | Med | 
| Large | Lg | 
| XLarge | XLg | 

This configuration *is not acceptable*because XLarge is missing from the modifier sizes:

| Menu Item Sizes | Modifier Sizes | 
| --- | --- |
| Small | Small | 
| Medium | Medium | 
| Large | Large | 
| XLarge |  | 

##### Size pricing for modifier groups

Follow the instructions below to configure size pricing for a modifier group. All of the modifiers in the group follow the same size pricing rules, for example, all of the toppings in a Toppings modifier group cost $0.50 for a small pizza, $1 for a medium pizza, and $1.50 for a large pizza.

**Procedure 8.130. To enable size pricing on a modifier group**

1. In the Pricing section of a modifier group's details page, set the How are modifiers in this group priced setting to All modifiers share the same price.


2. Under the Modifier Group Pricingsection, select Size Price. The Size Price grid appears.


3. Define your sizes by entering a size name in the Size column and a corresponding price for the size in the Price column. The sizes you create *must exactly match* the sizes defined for the menu items this modifier group will apply to, as described in [Creating matching sizes for menu items and modifiers](adminSizePrice.html#adminCreatingMatchingSizesForMenuItemsAndModifierOptions). Also, you must enter a price for each size you create.


4. To add additional rows to the grid, click the Add Size button.


5. To remove a row from the grid, click the Edit button, click the trash can icon for that row, and then click Done.


6. Save your changes.


7. [If you are done editing prices for your menus, publish your changes.](adminNoteAboutPublishingPrices.html)





> **Note**
> 
> The [Price Editor](adminUsingThePriceEditor.html) does not yet support editing modifier group or modifier prices. You can edit size prices for a modifier group on the modifier group's details page.


##### Size pricing for individual modifiers

Follow the instructions below to configure size pricing for individual modifiers. When specifying size pricing for an individual modifier, you actually configure the sizes and their associated prices on the [modifier's underlying item reference](adminPricingModifierOptions.html#adminUnderstandingAModifierOptionsItemReference).

When configuring size pricing at the individual modifier level, you can choose whether the size of the modifier is:

- Dictated by the [size of the associated menu item](adminSizePrice.html#adminToConfigureSizePricingOnAModOptionDependentOnMenuItemSize). If you choose this configuration, the sizes you specify for the [modifier's item reference](adminPricingModifierOptions.html#adminUnderstandingAModifierOptionsItemReference) must match the sizes specified for the associated menu items exactly, both in the number of sizes and the text used for the size names, as described in [Creating matching sizes for menu items and modifiers](adminSizePrice.html#adminCreatingMatchingSizesForMenuItemsAndModifierOptions).


- Specified [independently from the menu item size](adminSizePrice.html#adminToConfigureSizePricingOnAModOptionSizeSetIndependently). If you choose this configuration, the sizes you specify for the modifier's item reference do not have to match menu item sizes. Also, the Toast POS app will prompt you for a size after the modifier is selected.



**Procedure 8.131. To configure size pricing on a modifier (size dependent on menu item size)**

1. In Toast Web, view the details page for the modifier group whose modifiers should have size pricing enabled.


2. In the Pricing section of a modifier group's details page, set the How are modifiers in this group priced setting to Each modifier has a unique price.


3. Under the Size behavior section, set the How should sized priced modifiers behavesetting to Modifier automatically use the same size as the items they are applied to.


4. In the Modifiers section, locate the Modifiers grid.


5. In the Modifiers grid, click the Edit Item icon for a modifier to see the details page for the [modifier's item reference](adminPricingModifierOptions.html#adminUnderstandingAModifierOptionsItemReference).

![Example of the Modifiers grid showing the location of the Edit Item icon.](https://doc.toasttab.com/doc/media/pricing-edit-icon-pizza-toppings.png)


6. Under the Pricing section, set Pricing Strategy to Size Price. The Size Prices grid appears.


7. Define your sizes by entering a size name in the Size column and a corresponding price in the Price column. The sizes you create for the modifier's item reference *must exactly match*the sizes defined for the menu items the modifier will apply to, as described in [Creating matching sizes for menu items and modifiers](adminSizePrice.html#adminCreatingMatchingSizesForMenuItemsAndModifierOptions). Also, you must enter a price for each size you create.


8. To add additional rows to the grid, click the Add button.


9. To reorder sizes:

- Click the Edit button. A new column appears to the left with the reordering icon.

![Example of the Size Prices grid showing the location of the reordering icon.](https://doc.toasttab.com/doc/media/pricing-reorder-column.png)


- Click the reordering icon for a row and drag it to its new location.


- Click Done when you are finished reordering.




10. To delete sizes:

- Click the Edit button. A new column appears to the right with the trash can icon.


- Click the trash can icon for the row you want to delete.


- Click Done when you are finished deleting.




11. Save your changes.


12. [If you are done editing prices for your menus, publish your changes.](adminNoteAboutPublishingPrices.html)



**Procedure 8.132. To configure size pricing on a modifier (size set independently)**

1. In Toast Web, view the details page for the modifier group whose modifiers should have size pricing enabled.


2. In the Pricing section of a modifier group's details page, set the How are modifiers in this group priced setting to Each modifier has a unique price.


3. Under the Size behavior section, set the How should sized priced modifiers behavesetting to The size of the modifier can differ from the size of the item. Guests and servers select the modifier's size after choosing the modifier..


4. In the Modifiers section, locate the Modifiers grid.


5. In the Modifiers grid, click the Edit Item icon for a modifier to see the details page for the [modifier's item reference](adminPricingModifierOptions.html#adminUnderstandingAModifierOptionsItemReference).

![Example of the Modifiers grid showing the location of the Edit Item icon.](https://doc.toasttab.com/doc/media/pricing-edit-icon-pizza-toppings.png)


6. Under the Pricing section, set Pricing Strategy to Size Price. The Size Prices grid appears.


7. Define your sizes by entering a size name in the Size column and a corresponding price in the Price column. The sizes you create for the modifier's item reference *do not have to match* sizes specified for the menu items the modifier will apply to. You must enter a price for each size you create.


8. To add additional rows to the grid, click the Add button.


9. To reorder sizes:

- Click the Edit button. A new column appears to the left with the reordering icon.

![Example of the Size Prices grid showing the location of the reordering icon.](https://doc.toasttab.com/doc/media/pricing-reorder-column.png)


- Click the reordering icon for a row and drag it to its new location.


- Click Done when you are finished reordering.




10. To delete sizes:

- Click the Edit button. A new column appears to the right with the trash can icon.


- Click the trash can icon for the row you want to delete.


- Click Done when you are finished deleting.




11. Save your changes.


12. [If you are done editing prices for your menus, publish your changes.](adminNoteAboutPublishingPrices.html)





> **Note**
> 
> The [Price Editor](adminUsingThePriceEditor.html) does not yet support editing modifier group or modifier prices, so size prices for a modifier must be edited on the details page for the modifier's item reference.


