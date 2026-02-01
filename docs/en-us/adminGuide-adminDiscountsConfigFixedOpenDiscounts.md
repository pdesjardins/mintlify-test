---
title: "Configuring fixed or open amount or percent discounts"
id: adminDiscountsConfigFixedOpenDiscounts
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminDiscountsTypeSpecificConfigOmitChunkFromSearchIndex.md
parentSectionTitle: "Configuring type-specific settings for a discount"
previousSectionFile: adminGuide-adminDiscountsTypeSpecificConfigOmitChunkFromSearchIndex.md
previousSectionTitle: "Configuring type-specific settings for a discount"
nextSectionFile: adminGuide-adminDiscountsConfigureBogo.md
nextSectionTitle: "Configuring a BOGO discount"
excerpt: "For fixed amount, fixed percent, open amount, and open percent discounts, you choose what the discount applies to. For fixed discounts, you also provide the discount value."
keywords: ["configuring", "fixed", "open", "amount", "percent", "discounts"]
procedures: 0
codeExamples: 0
---

### Configuring fixed or open amount or percent discounts

For fixed amount, fixed percent, open amount, and open percent discounts, you choose what the discount applies to. For fixed discounts, you also provide the discount value.

#### Providing the discount value for fixed discounts

On the discount configuration page, when you select either Fixed $ Off or Fixed % Offas the discount type, a Value field is displayed.

In the Value field, specify the amount of the discount.

For a Fixed $ Off discount, the value is the currency amount to discount from the item or check. The default value is $0.00.

![Value field for a fixed currency amount discount.](https://doc.toasttab.com/doc/media/discount-fixed-amount-value.png)

For a Fixed % Off discount, the value is the percent to discount from the item or check. The default value is 100%.

![Value field for a fixed percent discount.](https://doc.toasttab.com/doc/media/discount-fixed-percent-value.png)

#### Selecting what the discount applies to

In the configuration for both fixed and open discounts, the Applies to setting specifies how the discount is applied.

![Applies to configuration setting that determines how the discount applies.](https://doc.toasttab.com/doc/media/discount-fixed-open-applies.png)

The available values for Applies toare:



**Any item**
: Creates an item-level discount that applies to any menu item on the check. You do not configure required items for this type of discount.



**Entire check**
: Creates a check-level discount. Check-level discounts apply to the entire check. You can optionally specify excluded items and required items for the discount.

![Discount configured to apply to an entire check.](https://doc.toasttab.com/doc/media/discount-applies-to-entire-check.png)

To configure excluded items for the discount, select Discount will apply to all items except the following items/groups, then add the excluded items. For information about excluding items from a discount, see [Excluding items from a check-level discount](adminDiscountsConfigFixedOpenDiscounts.html#adminExclusionDiscounts).

To configure required items for the discount, select Check must include one of the following items/groups, then choose the required items. The discount applies to the check only if the check has at least one of the required items. For information about selecting required items, see [Choosing the required items for a discount](adminDiscountRequiredItemsAbout.html).



**Specific item/group**
: Creates an item-level discount that applies to the required items that you configure for the discount. The discount can only be applied if at least one of the required items is on the check. For information about selecting required items, see [Choosing the required items for a discount](adminDiscountRequiredItemsAbout.html).

![Discount configured to apply to a specific item.](https://doc.toasttab.com/doc/media/discount-applies-to-specific-item.png)





#### Excluding items from a check-level discount

For check-level discounts, you can exclude specific menu items, menu groups, or menus. When the discount is applied to a check, the discount ignores the excluded items and applies the discount to the rest of the check.



> **Note**
> 
> This feature is in limited release.


##### Rules for configuring and applying a discount with exclusions

The rules for configuring and applying a discount with excluded items are as follows:

- You cannot configure excluded items for discounts that use the following:

- Bulk Discount


- Allow with other discountsenabled. Discounts that have excluded items must be exclusive.


- Auto apply discount enabled. Discounts that have excluded items must be applied manually.




- If you specify multiple excluded items, then all of those items are excluded.


- You cannot specify sizes or modifiers for excluded items. For example, if a cheese pizza item has small and large sizes, you cannot only exclude large pizzas. All sizes of the pizza item are excluded.


- You can apply a discount with excluded items to any check, even a check that does not contain any of the excluded items. The check only needs to have any required items.



##### Selecting the excluded items

When you select Entire check for a fixed or open discount, the discount configuration page displays a check box that allows you to select items to exclude.

**Procedure 9.3. To configure the list of excluded items**

1. Select the Discount will apply to all items except the following items/groups check box.

The Search for items search box displays.

![Item search box used to find items to exclude.](https://doc.toasttab.com/doc/media/discount-exclusion-search.png)


2. For each menu item or group to exclude, begin to type the name in the search box. As you type, the list of matching items and groups is displayed. In the results list, click the menu item or group.

The selected menu item or group is added to the list of excluded items. To remove an item, click its remove icon.

![Multiple excluded items selected.](https://doc.toasttab.com/doc/media/discount-exclusion-items.png)

For excluded items, you cannot specify sizes or modifiers. All of the items are excluded by the discount.



