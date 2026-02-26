---
title: "Bulk discounts"
id: adminBulkDiscounts
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminDiscountsEffectsOmitChunkFromSearchIndex.md
parentSectionTitle: "Effects of applied discounts"
previousSectionFile: adminGuide-adminDiscountExclusivity.md
previousSectionTitle: "Exclusive and nonexclusive discounts"
nextSectionFile: adminGuide-adminDiscountsTargetsAndOwners.md
nextSectionTitle: "Discount configurations for multi-location restaurants"
excerpt: "A bulk discount..."
keywords: ["bulk", "discounts"]
procedures: 0
codeExamples: 0
---

A bulk discount applies a discount multiple times to eligible items on the check. As part of the configuration, you must specify the minimum and maximum number of items to which the discount can be applied.

For example, you can create a check-level discount that applies a 20% bulk discount to a minimum of two garden salads and a maximum of four garden salads on the check. The application rules for this sample bulk discount are the following:

- If the check does not have a garden salad or has only one garden salad, the check does not qualify for the discount.


- If the check has at least two and up to four garden salads, the 20% discount applies to all the garden salads.


- If the check has five or more garden salads, the 20% discount applies to four of the garden salads but not to the rest.



## Eligible discount types for bulk discounts

You can configure these discount types to be bulk discounts:

- Fixed currency amount check-level discounts. Open currency amount discounts cannot be bulk discounts.

The discount must have one required item, which can be a menu item, menu group, or menu.


- Fixed percent check-level discounts. Open percent discounts cannot be bulk discounts.

The discount must have one required item, which can be a menu item, menu group, or menu.


- Combo discounts.

The discount must have one and only one required item, which can be a menu item, menu group, or menu. For example, an eligible combo discount can be configured for one cheese pizza for $20, but not for one cheese pizza and one soda for $20.



Item-level discounts, open amount and percent discounts, and BOGO discounts are not eligible to be bulk discounts.

## Configuring a bulk discount

On the discount configuration page, under Advanced Settings, the Bulk Discount setting determines whether a discount can apply in bulk to the number of eligible items that you configure.



> **Note**
> 
> When enabled, the Bulk Discount setting displays for all fixed amount and fixed percent check-level discounts, and for combo discounts.
> The setting displays even when a discount has multiple required items, which makes it ineligible to be a bulk discount.
> Make sure that you do not configure an ineligible discount to be a bulk discount.


![Bulk Discount setting in the Advanced Settings section of the discount configuration page.](https://doc.toasttab.com/doc/media/discount-bulk-option.png)

If you check the Bulk Discount setting, you must also configure the Min Quantity and Max Quantity fields. These fields specify the number of eligible items to which the discount can be applied in bulk during a single application of the discount:

- Min Quantity specifies the minimum number of eligible (required) items that the check must have before the bulk discount can apply. The value must be a positive integer.


- Max Quantity specifies the maximum number of eligible items to which the bulk discount can apply at one time. The value must be a positive integer and must be equal to or greater than the Min Quantityvalue.



If you check the Bulk Discount setting but leave the Quantity fields blank, the system sets them to *1* when you save the configuration.



> **Note**
> 
> You use the Min Quantity and Max Quantity fields to control the application of the bulk discount based on the number of eligible items on the check. You can also use the Min/Maxconfiguration option to control the application of the bulk discount based on the monetary total of the check. For details on the Required Min/Max Check Amount setting, see [Configuring required minimum and maximum check totals](docs/en-us/adminGuide-adminDiscountsMinMax).


## Viewing a bulk discount on the Toast POS app

On the Toast POS app order screen, when you apply a bulk discount to a check, the items to which the discount applies are grouped under the name of the discount.

For example, a bulk discount named *Bulk Discount* is configured as follows:

- *Large Coffee* is the required item.


- Min Quantity is *2*.


- Max Quantity is *10*.



The discount is applied to a check that has six large coffees.

On the Toast POS app:

- The 10 large coffees receive the discount, because Max Quantity is *10*. The coffee items are grouped under the *Bulk Discount* discount name.



![Toast POS app screen showing a bulk discount that is applied to 10 large coffees.](https://doc.toasttab.com/doc/media/discount-bulk-example.png)

