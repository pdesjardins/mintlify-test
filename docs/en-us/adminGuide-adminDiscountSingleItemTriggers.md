---
title: "Selecting an individual menu item as a required item"
id: adminDiscountSingleItemTriggers
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminDiscountTriggerComponentsOmitChunkFromSearchIndex.md
parentSectionTitle: "Choosing the required items for a discount"
previousSectionFile: adminGuide-adminDiscountRequiredItemsAbout.md
previousSectionTitle: "Required items overview"
nextSectionFile: adminGuide-adminDiscountMenuGroupTriggers.md
nextSectionTitle: "Selecting a menu group as a required item"
excerpt: "You can choose any individual menu item in your restaurant menu configuration to be a required item for a discount. The item might be one of a list of..."
keywords: ["selecting", "individual", "menu", "item", "required"]
procedures: 0
codeExamples: 0
---

You can choose any individual menu item in your restaurant menu configuration to be a required item for a discount. The item might be one of a list of items, or might be part of a combo group of items.

To make the selected item more specific, you can specify eligible sizes or modifiers.

## Searching for and selecting the item

To search for a menu item, begin to type the name in the item search box.

![Item search with matching items for the search text.](https://doc.toasttab.com/doc/media/discount-item-search.png)

In the list of matching items, menu groups, and menus, click the item name.

![Single selected item for an item-level discount.](https://doc.toasttab.com/doc/media/discount-item-trigger.png)

For an individual menu item, you can also choose the required modifiers or sizes. You cannot configure modifiers for a required item that is a menu group.

## Selecting the eligible sizes for an item

For a menu item that uses size pricing, you specify the sizes that qualify for the discount. For example, a discount might apply to large and extra-large cheese pizzas but not to small cheese pizzas.

When you select a menu item that uses size pricing, you are prompted to select the eligible sizes. On the size dialog, click the dropdown list for the sizes, then click each size that is eligible for the discount. To save the selected sizes, click Save.

![Dialog to choose the size modifiers that apply to the discount.](https://doc.toasttab.com/doc/media/discount-trigger-size-and-modifier.png)

For a combo discount, if you select more than one size, the Toast platform treats the lowest-priced size, which is typically the smallest, as the base size for the combo price. The Toast platform increases the combo price for the higher-priced sizes, which are typically larger, by the additional amount for those larger sizes. For more information, see [Upcharging discounted items in a combo discount](adminGuide-adminDiscountPricing#adminUpchargingDiscountedItems).

The order in which the Toast platform considers sizes for size upcharging is based purely on the size pricing for the menu item. The names that you give to sizes, such as glass or bottle, do not affect how the platform considers the sizes.

## Selecting eligible modifiers for required items

For a menu item that has modifiers, you can specify which modifiers qualify as required items or are included in the discount price.

- You can specify that a discount price includes, but does not require, one or more modifiers for a menu item. For example, a discount price might include a cheese pizza with up to two modifiers from a pizza toppings menu group.


- You can specify that a menu item must have a specific number of modifiers or specific modifiers to qualify for a discount. For example, a discount might apply to a cheese pizza with a jalapeno topping, but not to a cheese pizza with no toppings or to a cheese pizza with toppings other than jalapenos.



Combo discounts that include modifier options apply to the least expensive modifiers for an item. For more information, see [Configuring a combo discount](adminGuide-adminDiscountsConfigureCombo).

**Procedure 9.5. To select the modifiers for an item**

1. Click the selected menu item.

The item dialog is displayed. If the item has modifiers, then the dialog includes an Add Modifier Groups option.

![Dialog to configure the eligible modifiers.](https://doc.toasttab.com/doc/media/discount-item-modifier-initial.png)


2. On the item dialog, click Add Modifier Groups, then select a modifier group.

You can add more than one modifier group to the item.

![Item dialog with a modifier group selected.](https://doc.toasttab.com/doc/media/discount-item-modifier-group-selected.png)


3. To allow up to a specified number of modifiers, chose the Up to option.

To require a specific number of modifiers, chose the Must have option.


4. Click Select Modifiers. In the list of modifiers, click each eligible modifier.

![List of modifiers in the selected modifier group.](https://doc.toasttab.com/doc/media/discount-item-modifier-list.png)


5. Click Save.



