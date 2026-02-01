---
title: "Required items overview"
id: adminDiscountRequiredItemsAbout
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminDiscountTriggerComponentsOmitChunkFromSearchIndex.md
parentSectionTitle: "Choosing the required items for a discount"
previousSectionFile: adminGuide-adminDiscountTriggerComponentsOmitChunkFromSearchIndex.md
previousSectionTitle: "Choosing the required items for a discount"
nextSectionFile: adminGuide-adminDiscountSingleItemTriggers.md
nextSectionTitle: "Selecting an individual menu item as a required item"
excerpt: "Required items, sometimes referred to as trigger items, are the items or combinations of items that make the check eligible for a discount."
keywords: [required,items,overview,Fixed and open percent and amount discounts,BOGO discounts,Combo discounts]
procedures: 0
codeExamples: 0
---

### Required items overview

Required items, sometimes referred to as trigger items, are the items or combinations of items that make the check eligible for a discount.

A single item can be a specific menu item, a menu group, or a menu. When you select a menu item that has sizes or other modifiers, you are prompted to select the specific modifier. You can also specify the required quantity.

When you select a menu or menu group, then any item in that menu or group applies. You cannot select specific items, sizes, or modifiers.

Here is an overview of how required items are configured for each discount type:



****Fixed and open percent and amount discounts****
: For these types of discounts, you can choose to apply the discount to any item, to an entire check, or to a specific item or group.

If you choose to apply the check to a specific item or group, then you choose the eligible items for the discount. For each eligible item, you can set the quantity that the discount can apply to. To be eligible for the discount, the check must have at least one of the eligible items.

If you choose to apply the discount to the entire check, you can choose specific items that are excluded from the discount, or that must be present to be eligible for the discount.

See [Configuring fixed or open amount or percent discounts](adminDiscountsConfigFixedOpenDiscounts.html).



****BOGO discounts****
: For BOGO discounts, you configure buy items and get items.

For the buy items, you configure one or more combinations of items. The check must have one of those combinations in order to be eligible for the discount. Within each combination, you can specify the required quantity for each item.

For the get items, you configure one or more eligible items. You do not specify quantities for those items.

See [Configuring a BOGO discount](adminDiscountsConfigureBogo.html).



****Combo discounts****
: For combo discounts, you configure one or more combinations of items. The check must have one of those combinations in order to be eligible for the discount.

Within each combination, you can specify the required quantity for each item.

See [Configuring a combo discount](adminDiscountsConfigureCombo.html).





