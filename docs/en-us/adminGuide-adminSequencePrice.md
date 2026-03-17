---
title: "Sequence price"
id: adminSequencePrice
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminPricingStrategyDetailsOmitChunkFromSearchIndex.md
parentSectionTitle: "Pricing strategies"
previousSectionFile: adminGuide-adminFixedPrice.md
previousSectionTitle: "Fixed price"
nextSectionFile: adminGuide-adminSizePrice.md
nextSectionTitle: "Size price"
excerpt: "Applies to: Modifier groups"
keywords: ["sequence", "price", "Applies to:"]
procedures: 1
codeExamples: 0
---

**Applies to:** Modifier groups



> **Note**
> 
> Sequence pricing for modifiers is supported on the Toast POS app, Toast Online Ordering, and in the menu data returned to online ordering partners. It is not supported on the Toast Takeout (Local by Toast) app, Toast Order and Pay, and Toast Kiosk. For more information, see [Toast product channel support for advanced pricing features](adminGuide-adminToastProductChannelSupportForAdvancedPricingFeatures).


When using sequence pricing, the price of individual modifiers in a modifier group is determined by the sequence in which they are added to a menu item. For example, on a pizza menu item with a Toppings modifier group, the first topping is free, the second topping costs $1.00, the third topping costs $1.50, and all additional toppings cost $2.00. As modifiers are added to or removed from the menu item, the price of the menu item is updated to reflect those choices. The following illustration shows the Toast POS app with a menu item that has four sequence-priced modifiers:

![Example of the Toast POS app showing a menu item with four sequence-priced modifiers.](https://doc.toasttab.com/doc/media/pricing-sequence-pricing.PNG)

When the Toast platform determines the sequence, and the associated price, for a modifier, it only considers the sequence of that modifier in relation to other modifiers in the same modifier group. For example, consider a Sandwich menu item that has two modifier groups, Cheese and Meat. The Cheese and Meat modifier groups are configured to use sequence pricing and set their pricing as follows:

Cheese modifier group

- First option, $0.00


- Second option, $0.50


- All additional options, $1.00



Meat modifier group

- First option, $1.50


- Second option, $2.00


- All additional options, $2.50



A guest places an order for a turkey, ham, and cheddar sandwich and the server enters the modifiers in that order on the Toast POS app. The Toast platform calculates the following prices for the modifiers:

- Turkey, first Meat option, $1.50


- Ham, second Meat option, $2.00


- Cheddar, first Cheese option, $0.00



Even though cheddar was added as the third modifier to the sandwich, it is the first Cheese modifier to be added, so it gets the first modifier price for the Cheese modifier group, which is $0.00.

Sequence pricing is configured at the modifier group level. All modifiers within the modifier group use sequence pricing when they are added to a menu item.

**Procedure 8.133. To set sequence pricing on a modifier group**

1. In the **Pricing** section of a modifier group's details page, set the **How are modifiers in this group priced** setting to **All modifiers share the same price**.


2. Under the **Modifier Group Pricing** section, select **Sequence Price**. The **Sequence Price** grid appears.


3. Click the **Price** field for the first option and enter a price.



> **Note**
> 
> All sequence levels require a price. If you want a level to be free of charge, enter **`0.00`** in the **Price** field.



4. If you need additional sequence prices, click the **Add Level** button to add additional rows to the grid and enter the prices for each level in their **Price**fields.


5. Enter a price in the **Price** field for the **All additional options** level.


6. To remove a sequence price level, click the **Edit** button and then click the trash icon for that level in the grid.


7. Save your changes.


8. [If you are done editing prices for your menus, publish your changes.](adminGuide-adminNoteAboutPublishingPrices)





> **Note**
> 
> The [Price Editor](adminGuide-adminUsingThePriceEditor) does not yet support editing modifier group or modifier prices, so sequence prices for a modifier group must be edited on the modifier group's details page.


