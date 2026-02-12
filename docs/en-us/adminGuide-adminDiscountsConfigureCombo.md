---
title: "Configuring a combo discount"
id: adminDiscountsConfigureCombo
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminDiscountsTypeSpecificConfigOmitChunkFromSearchIndex.md
parentSectionTitle: "Configuring type-specific settings for a discount"
previousSectionFile: adminGuide-adminDiscountsConfigureBogo.md
previousSectionTitle: "Configuring a BOGO discount"
nextSectionFile: adminGuide-adminDiscountTriggerComponentsOmitChunkFromSearchIndex.md
nextSectionTitle: "Choosing the required items for a discount"
excerpt: "For a combo discount, you configure the discount value and the eligible combinations of menu items."
keywords: ["configuring", "combo", "discount"]
procedures: 0
codeExamples: 0
---

For a combo discount, you configure the discount value and the eligible combinations of menu items.

## Configuring the combo discount value

When you select Combo as the discount type, a Value field displays.

![Value and items fields for a combo discount.](https://doc.toasttab.com/doc/media/discount-combo-fields-initial.png)

In the Value field, provide the price to charge for the combo.

For example, if the combo discount offers a sandwich and a drink for $13.00, enter 13 in the Value field.

## Selecting the required items for the combo discount

In the Items section, provide the eligible combinations of items.

For a combo discount, you configure one or more eligible combinations of items. A check is eligible for the discount if it includes any one of those combinations.

In the following example configuration, a check is eligible for the combo discount if it includes either:

- A sandwich and a drink


- A burger and a drink



![Combo discount that is configured with multiple combo groups.](https://doc.toasttab.com/doc/media/discount-combo-fields-filled.png)

For more information about selecting required items for discounts, see [Choosing the required items for a discount](adminGuide-adminDiscountRequiredItemsAbout).

## Required item behavior for combo discounts

When working with combo discounts, keep in mind the following discount behavior:

- Combo discounts that include modifier options apply to the least expensive modifiers for an item.

For example, a combo discount is configured to apply to a pizza with up to three toppings. An order includes a pizza with five toppings.

In this case, the system applies the combo discount to the least expensive three toppings. The remaining toppings are full price.


- Combo discounts can apply multiple times to modifier options.

For example, a combo discount applies to a pizza with up to three toppings. An order includes two pizzas with three toppings each.

In this case, you can apply the combo discount to the check twice. The combo discount price is applied to each pizza, including the three modifiers for each item, for a total of six discounted modifier options.


- If you apply a combo discount to a check that includes more than one of the same menu item and that menu item is eligible for a combo discount, the discount applies to only one of the items.

For example, a combo discount offers a cup of coffee and a bagel for $3.00. You apply the discount to a check that includes two cups of coffee and a bagel. In this case, the discount includes one cup of coffee and a bagel.



For more information about required items for discounts, see [Choosing the required items for a discount](adminGuide-adminDiscountRequiredItemsAbout).

## Setting the maximum quantity to apply the discount to

You can configure a combo discount as a bulk discount, which includes the minimum and maximum quantity to apply the discount to. See [Bulk discounts](adminGuide-adminBulkDiscounts).

If you do not configure the combo discount as a bulk discount, then in the Advanced Settings section, the Total Quantity field allows you to specify the number of eligible combos in an order.

For example, a combo discount sets a discount price of $5 when you purchase a drink and a dessert together. An order contains three drinks and three desserts.

If Total Quantity is 1, then one drink and dessert are charged as a combo, and the other drinks and desserts are charged the individual prices.

If Total Quantity is 3, then the drinks and desserts are charged as three combos.

