---
title: "Configuring a BOGO discount"
id: adminDiscountsConfigureBogo
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminDiscountsTypeSpecificConfigOmitChunkFromSearchIndex.md
parentSectionTitle: "Configuring type-specific settings for a discount"
previousSectionFile: adminGuide-adminDiscountsConfigFixedOpenDiscounts.md
previousSectionTitle: "Configuring fixed or open amount or percent discounts"
nextSectionFile: adminGuide-adminDiscountsConfigureCombo.md
nextSectionTitle: "Configuring a combo discount"
excerpt: "For a BOGO discount, you choose the required buy items, and the eligible get items. For the get items, you set the amount of the discount, and the priority for discounting the items."
keywords: ["configuring", "bogo", "discount"]
procedures: 0
codeExamples: 0
---

For a BOGO discount, you choose the required buy items, and the eligible get items. For the get items, you set the amount of the discount, and the priority for discounting the items.

You can also specify the required number of buy items and the maximum number of get items.

### Configuring the required buy items

For buy items, you select the required items. You also configure the required number of buy items.

A buy item in a BOGO discount cannot have any other discounts applied to it. If the buy item has a different discount applied to it, then it cannot trigger the BOGO discount.

#### Selecting the buy items

You use the Buy Items section of the discount configuration page to configure the required buy items for a BOGO discount.

Under Applies to, to allow any item to be eligible for the discount, select Any item.

To select specific items and quantities as the buy items, select Specific item/group. You can set up one or more combinations of items. Each combination represents an available option to qualify for the discount. The check must include one of these combinations. For details on selecting required items, see [Choosing the required items for a discount](adminDiscountRequiredItemsAbout.html).

#### Setting the required number of buy items

In the Advanced Settings section of the discount configuration page, you use the Required # of Buy Items field to configure the number of buy items that must be on the order. By default the value is 1.

For example, if you configure the discount to allow any item as the buy item, then you use this field to specify the number of items that must be present in the order before the discount can be applied.

### Configuring the get items

For get items, you select the eligible items, and configure the discount to apply. You can also configure the maximum number of get items that can receive the discount.

#### Selecting the get items

You use the Get Items section of the discount configuration page to select the eligible get items for a BOGO discount.

Under Applies to, to allow any item to be a get item, select Any item.

To select specific items to be get items, select Specific items/group, then select the items. For get items, you select individual items or groups. When selecting individual items, you can specify which sizes are eligible for the discount. For more information on selecting required items, see [Choosing the required items for a discount](adminDiscountRequiredItemsAbout.html).

#### Setting the discount amount and eligible item priority

Under Discount, you set the type and amount of the discount on the get item. For example, you can discount $2 or 10% off of the price.

You also choose how to determine which eligible get item receives the discount.

**Procedure 9.4. To configure the discount for the get items**

1. From the discount type dropdown list, select whether to apply a currency amount discount or a percent discount.


2. In the value field that displays, provide the currency amount or percent.


3. From the priority dropdown list, select how to choose the specific get item to discount if there are multiple eligible items. The options are:

- Of first eligible item: Discounts the first eligible item, regardless of the cost of the item.


- Of least expensive eligible item: Discounts the eligible item that has the lowest price.


- Of most expensive eligible item: Discounts the eligible item that has the highest price.



![Get item configuration with the drop-down list of item priority options.](https://doc.toasttab.com/doc/media/discount-bogo-get.png)



#### Setting the maximum number of get items to discount

In the Advanced Settings section of the discount configuration page, you use the Eligible # of Get Items field to configure the number of get items that can receive the discount. By default, the value is 1.

### BOGO discounts on receipts

The layout of BOGO receipts shows how the discount was applied. These receipt changes are visible on printed receipts, on the order screen of the Toast POS app, and on Toast Web (for example, on receipts on the Reports \> Payments \> Payments page).

The receipt uses the following format to group the elements of a BOGO discount:

- BOGO name

- buy item


- get item

- percent/fixed amount discounted with total amount discounted







This example shows a receipt where a BOGO discount named *BOGO Drinks* is applied to the check.

![Receipt that displays information for an applied BOGO discount.](https://doc.toasttab.com/doc/media/discount-bogo-receipt.png)

The receipt groups the elements of the *BOGO Drinks* discount:

- The Grilled Salmon buy item, including the Garden salad modifier option


- The Soda get item


- The 50.00% discount (for a total of minus $1.50) on the get item



