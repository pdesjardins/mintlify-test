---
title: "Size/sequence price"
id: adminSizeSequencePrice
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminPricingStrategyDetailsOmitChunkFromSearchIndex.md
parentSectionTitle: "Pricing strategies"
previousSectionFile: adminGuide-adminSizePrice.md
previousSectionTitle: "Size price"
nextSectionFile: adminGuide-adminStackingPricingStrategies.md
nextSectionTitle: "Stacking pricing strategies"
excerpt: "Applies to: Modifier groups"
keywords: ["sizesequence", "price", "Applies to:"]
procedures: 1
codeExamples: 0
---

**Applies to:** Modifier groups



> **Note**
> 
> Size/sequence pricing for modifiers is supported on the Toast POS app, Toast Online Ordering, and in the menu data returned to online ordering partners. It is not supported on the Toast Takeout (Local by Toast) app, Toast Order and Pay, and Toast Kiosk. For more information, see [Toast product channel support for advanced pricing features](adminGuide-adminToastProductChannelSupportForAdvancedPricingFeatures).


Size/sequence pricing strategy expands on the [sequence pricing](adminGuide-adminSequencePrice) strategy. With size/sequence pricing, the cost of a modifier depends on the size of the menu item it is applied to and the order in which it is applied to the menu item. For example, the first topping on a small pizza is $0.50 and additional toppings are $1 while the first topping on a large pizza is $1.50 and additional toppings are $2.50.

Size/sequence pricing is specified at the modifier group level and the size of the modifier is determined by the size of the menu item it is applied to. This means that the sizes you specify when defining size/sequence prices for a modifier must exactly match the sizes of the menu items that the modifier will apply to, as described in [Creating matching sizes for menu items and modifiers](adminGuide-adminSizePrice#adminCreatingMatchingSizesForMenuItemsAndModifierOptions).

**Procedure 8.138. To enable size/sequence pricing on a modifier group**

1. In the **Pricing** section of a modifier group's details page, set the **How are modifiers in this group priced** setting to **All modifiers share the same price**.


2. Under the **Modifier Group Pricing** section, select **Size/Sequence Price**. The **Size/Sequence Price** grid appears.

![Example of the Size/Sequence Price grid.](https://doc.toasttab.com/doc/media/pricing-size-sequence-price-empty-grid.png)


3. Click the **Size** label in the first non-heading row of the grid and enter a name for the first size, for example, **`Small`**:

![Example of the Size/Sequence Price grid with the first size, Small, entered.](https://doc.toasttab.com/doc/media/pricing-size-sequence-price-small.png)


4. Specify the pricing details for the size you created in the previous step:

- In the **Price** column for the **1st option**, enter a price for the first modifier added to this size of menu item.


- Optionally, click **Add Level** to additional rows for 2nd option, 3rd option, and so on, and enter prices for those levels.


- Optionally, enter a price for **All additional options**. For example, the first modifier costs $0.50, the second costs $1, and all additional options cost $1.50.




5. Repeat this process to add additional sizes and their pricing details. The sizes you create *must exactly match*the sizes defined for the menu items these modifiers will apply to, as described in [Creating matching sizes for menu items and modifiers](adminGuide-adminSizePrice#adminCreatingMatchingSizesForMenuItemsAndModifierOptions). Also, you must enter pricing information for each size you create.


6. To add additional size rows to the grid, click the **Add Size** button.


7. To delete any sizes or pricing levels:

- Click the **Edit** button. A new column appears to the right with the trash can icon.


- Click the trash can icon for the size or level you want to delete.


- Click **Done** when you are finished deleting.




8. Save your changes.


9. [If you are done editing prices for your menus, publish your changes.](adminGuide-adminNoteAboutPublishingPrices)





> **Note**
> 
> The [Price Editor](adminGuide-adminUsingThePriceEditor) does not yet support editing modifier group or modifier prices, so size/sequence prices for a modifier group must be edited on the modifier group's details page.


