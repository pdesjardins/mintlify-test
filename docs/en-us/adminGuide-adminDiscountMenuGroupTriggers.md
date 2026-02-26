---
title: "Selecting a menu group as a required item"
id: adminDiscountMenuGroupTriggers
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminDiscountTriggerComponentsOmitChunkFromSearchIndex.md
parentSectionTitle: "Choosing the required items for a discount"
previousSectionFile: adminGuide-adminDiscountSingleItemTriggers.md
previousSectionTitle: "Selecting an individual menu item as a required item"
nextSectionFile: adminGuide-adminDiscountsCombiningTriggers.md
nextSectionTitle: "Configuring groups of required items"
excerpt: "When you search for an item for a discount, the results include matching items, menu groups, and menus."
keywords: ["selecting", "menu", "group", "required", "item"]
procedures: 0
codeExamples: 0
---

When you search for an item for a discount, the results include matching items, menu groups, and menus.

![Search list of matching items.](https://doc.toasttab.com/doc/media/discount-item-search-mixed-results.png)

You can choose a menu or menu group to be a required item for a discount. Any individual menu item in the selected menu or menu group is then an applicable item for the discount.

For example, you might configure a discount with a 20 ounce bottled drinks menu group as its required item. If a check includes any menu item from that menu group, the discount applies to that check.

When you use a menu group as a discount required item, you cannot specify sizes or modifiers. Every menu item in the menu group applies the discount. Every menu item, size price, and modifier combination in the menu group is included in the combination price for a discount.

Using menu groups as discount required items is convenient. However, the menu items in a menu group do not necessarily have the same size pricing configuration, modifier items, or prices. Because of this, using menu groups for discount required items can make it more difficult to configure very specific combination pricing. For example, an Appetizers menu group might include menu items that have different size prices and significantly different base prices. A discount that includes any item in that appetizers menu group would affect check prices inconsistently.

If the menu items in a menu group are similar and similarly priced you can use that menu group as a discount required item without increasing the complexity of the discount configuration. If the menu group items use size pricing, have different base prices, or have other significant differences, you can configure an equivalent discount required item by explicitly including the menu items in that group using more complicated discount required item combinations.

For more information about discount required item combinations, see [Configuring groups of required items](adminGuide-adminDiscountsCombiningTriggers).

For more information about configuring discounts for menu groups that have size pricing or different prices, see [Combination pricing and menu groups](adminGuide-adminCombinationPricingAndMenuGroups) and [Handling menu groups with varying prices](adminGuide-adminDiscountsMenuGroupsVaryingPrices).

