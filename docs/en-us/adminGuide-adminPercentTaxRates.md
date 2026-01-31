---
title: "Percent rates"
id: adminPercentTaxRates
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminTaxesOmitChunkFromSearchIndex.md
parentSectionTitle: "Taxes"
previousSectionFile: adminGuide-adminTaxesOmitChunkFromSearchIndex.md
previousSectionTitle: "Taxes"
nextSectionFile: adminGuide-adminFixedTaxRates.md
nextSectionTitle: "Fixed rates"
excerpt: "A percent tax rate calculates the..."
keywords: [percent,rates]
procedures: 0
codeExamples: 0
---

### Percent rates

A percent tax rate calculates the sales tax on a menu item based on a fixed percentage of the item price. You configure a percent tax rate for your restaurant if your region uses a percent-based sales tax rate.

For example, suppose a state has a sales tax of 5% on meals sold by restaurants. If your restaurant were in that state, you could create a percent tax rate of 5% that is imposed on menu items. With that tax rate, a meal with a subtotal of $108.80 would have a sales tax of $5.44, for a total of $114.24. Keep in mind that additional taxes (such as a local tax) could also be applied to the check.

You can configure multiple percent tax rates for your restaurant. For example, you could configure a tax rate of 6% for food items and a tax rate of 9% for alcoholic beverages. You would then configure the food items on a menu to use the 6% tax rate, and the beverage items to use the 9% tax rate.

In addition to the basic (primary) percent tax rate, you can optionally configure a secondary [takeout tax rate](adminPercentTaxRates.html#takeoutTaxRate) for takeout orders.

#### Rounding options

When you configure a percent tax rate, you select a rounding option for the tax rate. A rounding option determines how tax amounts that have three or more decimal places are rounded to two decimal places. This type of rounding is often called penny rounding, because each fractional penny is rounded to a whole penny.

For example, a tax rate of 6.25%, when applied to a $50.75 check, results in a tax amount of $3.171875. Depending on which rounding option you select, the sales tax would be rounded down to $3.17 or rounded up to $3.18.



> **Note**
> 
> If you also create a takeout tax rate, the rounding option applies to both the basic percent tax rate and the secondary takeout tax rate.


The following table describes the four Toast rounding options.

| Rounding Option | Rounding Behavior | Rounding Examples | 
| --- | --- | --- |
| Half Even Rounding | Except for half-way values, always round fractional pennies to the nearest whole number (either up or down). For example, $1.234 rounds down to $1.23 and $1.236 rounds up to $1.24.For half-way values (where the number-to-round is exactly between two numbers, such as the 5 in $1.235), round to the nearest **even** number. For example, $1.235 rounds to $1.24. | $0.112 -> $0.11$0.115 -> $0.12$0.125 -> $0.12$0.135 -> $0.14 | 
| Half Up Rounding | Except for half-way values, always round fractional pennies to the nearest number (either up or down). For example, $1.234 rounds down to $1.23 and $1.236 rounds up to $1.24.For half-way values (where the number-to-round is exactly between two numbers, such as the 5 in 1.235), always round up. For example, $1.235 rounds up to $1.24 and $1.345 rounds up to $1.35. | $0.112 -> $0.11$0.115 -> $0.12$0.125 -> $0.13$0.135 -> $0.14 | 
| Always Round Down | Always round down every fractional penny, including half-way values.For example, $1.234, $1.235, and $1.236 all round down to $1.23. | $0.112 -> $0.11$0.115 -> $0.11$0.125 -> $0.12$0.135 -> $0.13 | 
| Always Round Up | Always round up every fractional penny, including half-way values.For example, $1.234, $1.235, and $1.236 all round up to 1.24. | $0.112 -> $0.12$0.115 -> $0.12$0.125 -> $0.13$0.135 -> $0.14 | 

#### Takeout tax rates

The tax code in some states specify that different tax rates must be charged for takeout food items versus dine-in food items. For example, meals consumed in the restaurant may be taxed at a higher rate than meals taken out and consumed at home.

Using the same configuration page that you use to create a percent tax rate, you can configure a second percent rate for takeout orders. The takeout tax rate applies only to menu items in orders using a dining option with the Take Out behavior. Menu items that are specifically assigned on the Toast POS device to a dining option with the Take Out behavior will also be charged with the takeout tax rate. The takeout tax rate is optional and does not affect the basic percent tax rate.



> **Note**
> 
> You create a basic percent tax rate in the Basic section of the tax rate configuration page and a takeout tax rate in the Take Out Taxsection of the same page. The Take Out Taxsection is dynamically added to the page when you select Percent as the Type for the tax rate. You must configure a basic percent tax rate (even if its rate is 0.0) before you can save your takeout tax rate configuration.


Keep the following in mind when you create a takeout tax rate:

- The takeout tax rate applies to menu items using a dining option with the Take Out behavior. It does not apply to menu items using a dining option with a behavior of Dine In, Delivery, Curbside, or None.


- Your restaurant must have at least one dining option with the Take Out behavior configured on the Kitchen > Dining options > Dining options page, as in this example:

![Dining Options page with a Take Out behavior example.](https://doc.toasttab.com/doc/media/tax-dining-options.png)

If your restaurant does not have a dining option with the Take Out behavior, you cannot configure a takeout tax rate because the Take Out Taxsection of the [percent tax rate configuration page](adminPercentTaxRates.html#configurePercentTaxRate) will be unavailable.


- Menus that can be used for takeout orders must have the Dining Option Tax setting configured as No Effect on the Menus > Bulk management > Advanced properties page, as in this example:

![Dining Options Tax set to No Effect.](https://doc.toasttab.com/doc/media/tax-no-effect.png)



When you take an order that must be taxed at the takeout tax rate, make sure you select a takeout dining option for the order, as in this example:

![Dining Option dialog on the Toast POS device.](https://doc.toasttab.com/doc/media/tax-pos-dining-option.png)

#### Configuring percent rates

1. [Access Toast Web](platformToastPlatformConceptsOmitChunkFromSearchIndex.html#adminAccessToastAdminBackend).


2. Choose Menus > Menu management > Settings > Manage tax rates to open the Tax rates page.


3. Click + Add Tax Rate.


4. In the Basic section of the New tax rate page, enter the configuration for the basic percent tax rate:

- Name: Enter a name for the tax rate, such as `State Tax`.


- Target: Specifies the location in a restaurant group to which this tax rate applies. (This control is visible only if you have the enterprise module.) For information about targets, see [Targets](targets.html).


- Owner: Specifies which group level permission is needed to edit this tax rate. (This control is visible only if you have the enterprise module.) For information about owners, see [Owners and permissions](ownersAndPermissions.html).


- Import ID: Leave this field blank. It is for internal use only.


- Type: Select Percent.


- Rate: Enter the tax percent value to be charged. The rate must be between 0.0 and 100.0, inclusive.


- Default: Select Yes to have the tax rate inherited by menus and menu items that are configured to inherit tax rates or select No to disable tax rate inheritance (for this setting, menus and menu items that do not inherit tax rates must be configured with specific tax rates).




5. In the Take Out Tax section, you can optionally configure a take out tax rate:

- Enable Take Out Tax Rate: Select Yes to create a takeout tax rate for orders using a dining option with the Take Out behavior. If you do not want to create a takeout tax rate, select No, charge the rate configured above for all dining options.


- Takeout Tax Rate: If you have enabled a takeout tax rate, enter the tax percent rate to be charged for takeout orders. The rate must be between 0.0 and 100.0, inclusive. 




6. In the Advanced Settings section, select one of the four [rounding options](adminPercentTaxRates.html#roundingOptions) for this tax rate.


7. You can test the percent tax rate with the Calculate Your Tax calculator. Enter any dollar amount in the Menu Item Price field and click Calculate. The system uses your configured percent tax rate to calculate the sales tax that is shown in the Tax Applied field, as shown in the following example. (Note that the calculator does not work with takeout tax rates).

![Calculating the tax rate using the tax calculator.](https://doc.toasttab.com/doc/media/tax-calculate-your-tax-calculator.png)


8. Save and publish your changes.



