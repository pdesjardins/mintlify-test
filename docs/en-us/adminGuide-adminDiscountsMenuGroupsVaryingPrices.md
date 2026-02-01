---
title: "Handling menu groups with varying prices"
id: adminDiscountsMenuGroupsVaryingPrices
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminDiscountTriggerComponentsOmitChunkFromSearchIndex.md
parentSectionTitle: "Choosing the required items for a discount"
previousSectionFile: adminGuide-adminCombinationPricingAndMenuGroups.md
previousSectionTitle: "Combination pricing and menu groups"
nextSectionFile: adminGuide-adminDiscountsOverallAvailabilityOmitChunkFromSearchIndex.md
nextSectionTitle: "Configuring discount availability and status"
excerpt: "To configure a combo discount to only include some of the menu items in a menu group, you can add a separate combo group for each individual menu item permutation of the combination."
keywords: ["handling", "menu", "groups", "varying", "prices"]
procedures: 0
codeExamples: 0
---

### Handling menu groups with varying prices

To configure a combo discount to only include some of the menu items in a menu group, you can add a separate combo group for each individual menu item permutation of the combination.

The following example shows items in a menu group that use size pricing. You might want to include any small order of fries as a required item in a combination discount. However, if you use the fries menu group as a required item, the discount combination price would include both small and large orders of fries.

![List of items in the fries menu group.](https://doc.toasttab.com/doc/media/menu-group-with-size-pricing.png)

The following example shows the required item configuration for a combination discount for a chicken Caesar salad and a small order of fries. The configuration includes a separate combo group for each item in the fries menu group. Each combo group includes the salad and the small size of a fries menu item. The blue dots on the menu item blocks for the fries indicate that a size or modifier is selected for the menu item.

![Combo groups configuration with each fries option in a separate combo group.](https://doc.toasttab.com/doc/media/discount-combination-multiple-combo-groups.png)

Using separate combo groups to create a discount required item that includes only some of the menu items in a menu group results in discount behavior that is consistent with the intent of your promotion. However, using this type of configuration for a menu group that has a large number of menu items requires extensive manual work and is difficult to check for errors. A discount that uses selective menu items from more than one menu group requires a large number of groups and is extremely difficult to configure reliably.



> **Note**
> 
> If you require Toast support to configure discounts, make sure to review the complexity of discount required items that are based on selective menu items from menu groups. The number of menu groups and the number of menu items in those groups can make configuring a discount too complicated and not supportable.


