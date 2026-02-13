---
title: "Combination pricing and menu groups"
id: adminCombinationPricingAndMenuGroups
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminDiscountTriggerComponentsOmitChunkFromSearchIndex.md
parentSectionTitle: "Choosing the required items for a discount"
previousSectionFile: adminGuide-adminDiscountsCombiningTriggers.md
previousSectionTitle: "Configuring groups of required items"
nextSectionFile: adminGuide-adminDiscountsMenuGroupsVaryingPrices.md
nextSectionTitle: "Handling menu groups with varying prices"
excerpt: "When you use a menu group as a discount required item, you cannot specify a size or modifiers for the menu items. You cannot specify which menu items from the menu group are eligible."
keywords: ["combination", "pricing", "menu", "groups"]
procedures: 0
codeExamples: 0
---

When you use a menu group as a discount required item, you cannot
      specify a size or modifiers for the menu items. You cannot specify which
      menu items from the menu group are eligible.

If you use a menu group as a required item for a combo discount,
      make sure that all of the menu items in the menu group have prices that
      are compatible with the discount and promotion that you intend.

The following diagram shows a combo discount that uses a menu
      group as a required item. Each menu item in the menu group is equivalent
      for the promotion and has the same price. The discount includes the menu
      group menu items in the combination price in a way that is consistent
      with the intent of the promotion.

![Diagram showing a combo discount and the available items in a required menu group.](https://doc.toasttab.com/doc/media/discount-combo-price-consistent-menu-group.png)

The following diagram shows a combo discount that uses a menu
      group as a required item. In this case, the menu items in the menu group
      use size pricing. Because you cannot specify a size when you use a menu
      group as a discount required item, the discount combination price
      applies to both sizes of the menu group menu items. If the intent of the
      promotion is to include only the small size, this discount configuration
      does not meet the promotion requirements.

![Diagram showing a combo discount with a required menu group that contains items with different prices.](https://doc.toasttab.com/doc/media/discount-combo-price-size-price-menu-group.png)

To configure combo discount required items that only include the
      menu group menu items that you intend to include in a promotion, you
      must use individual required items and separate groups in the discount
      configuration. For more information, see [Handling menu groups with varying prices](adminGuide-adminDiscountsMenuGroupsVaryingPrices).

