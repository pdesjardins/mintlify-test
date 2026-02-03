---
title: "Configuring groups of required items"
id: adminDiscountsCombiningTriggers
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminDiscountTriggerComponentsOmitChunkFromSearchIndex.md
parentSectionTitle: "Choosing the required items for a discount"
previousSectionFile: adminGuide-adminDiscountMenuGroupTriggers.md
previousSectionTitle: "Selecting a menu group as a required item"
nextSectionFile: adminGuide-adminCombinationPricingAndMenuGroups.md
nextSectionTitle: "Combination pricing and menu groups"
excerpt: "For BOGO and combo discounts, you configure groups of required menu items, menu groups, and menus."
keywords: ["configuring", "groups", "required", "items"]
procedures: 0
codeExamples: 0
---

For BOGO and combo discounts, you configure groups of required menu items, menu groups, and menus.

Each group represents a different way for a check to be eligible for the discount. The check must contain all of the required items from at least one of the configured groups.

Each group can contain one or more items. The group can have a combination of individual items, menu groups, and menus. Each item can have a specified quantity. For items that are individual menu items, you can specify eligible sizes and modifiers. See [Selecting an individual menu item as a required item](adminDiscountSingleItemTriggers.html).

The following example shows a combo discount configuration with two groups. To be eligible for the discount, the check must contain either:

- A sandwich and a drink


- A burger and a drink



![Two combo groups, each with two items.](https://doc.toasttab.com/doc/media/discount-combo-fields-filled.png)

