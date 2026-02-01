---
title: "Taxes on modifiers"
id: adminTaxesOnModifiers
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminTaxesOmitChunkFromSearchIndex.md
parentSectionTitle: "Taxes"
previousSectionFile: adminGuide-adminDisabledTaxRates.md
previousSectionTitle: "Disabled rates"
nextSectionFile: adminGuide-adminSmartTax.md
nextSectionTitle: "Smart tax"
excerpt: "Menu items have tax..."
keywords: ["taxes", "modifiers"]
procedures: 0
codeExamples: 0
---

### Taxes on modifiers

Menu items have tax configurations that determine which tax rates are applied when the menu item is added to a check. If a menu item has modifier options, you can use the Modifier Tax Behavior configuration option to specify how a modifier is taxed.

The Modifier Tax Behavior configuration option is on the detail page of the modifier option's menu item reference. For information on modifier option item references, see [Understanding a modifier item reference](adminPricingModifierOptions.html#adminUnderstandingAModifierOptionsItemReference).



> **Note**
> 
> The modifier tax behavior feature is in limited release.


You can configure a modifier to use one of these tax behaviors:

- Unique tax rate applied to modifiers: The modifier is configured with a tax rate which is different from the parent menu item and which is applied separately from the menu item tax rate. For example, a menu item is taxed at a 6.25% rate and the modifier is taxed at a 2.75% rate.

Note that if the menu item has multiple modifiers, each modifier may have its own unique tax rate. For example, a pizza menu item is taxed at 6.25%, a pineapple modifier has a unique tax rate of 4.25%, and a pepperoni modifier has a unique tax rate of 3.50%.


- Modifier tax rate overrides item tax rate: The modifier has a different tax rate than its parent menu item and the modifier tax rate overrides the menu item tax rate. This means that both the menu item and the modifier are taxed at the rate configured for the modifier. For example, if the menu item is configured for a 6.25% tax rate and the modifier is configured for a 2.75% tax rate, the menu item is taxed at the 2.75% tax rate, as is the modifier.

Note that the menu item's tax rate is overridden only if the modifier is added to the menu item when an order is created. If the modifier is configured on the item but is not applied to the item when an order is created, the menu item's tax rate will not be overridden.


- Inherit item tax rate: The modifier is taxed at the same rate as the parent menu item. This is the default setting for the option. For example, if the menu item is taxed at 6.25%, then the modifier is also taxed at the 6.25% rate.



Keep the following important notes in mind when using the taxes on modifiers feature:

- If two modifiers are set to override the tax rate of their parent menu item and both modifiers are added to the item, the item will default to using the tax rate configured for the parent item and disregard the tax rates configured for either of the modifiers. Both modifiers are ignored even if both have the same override tax rate.


- If a nested modifier (for example, a dressing modifier on a side salad modifier for a sandwich entree) is configured to override its parent item’s tax rate, it will only override the tax rate for its parent modifier (the dressing modifier will override the tax rate of the side salad, not the sandwich entree).


- If a modifier option is configured to use a unique tax rate but is not assigned a tax rate (from the Applicable taxes option), the modifier option is not taxed. Likewise, if a modifier option overrides the tax of its parent item but is not assigned a tax rate, both the modifier option and its parent item are not taxed.



#### Modifier tax behavior examples

The modifier tax behavior feature enables modifiers to have a different tax rate than their parent items or to override the tax rate of their parent item. The following are examples of when each of these settings would be used:

- Unique Tax Rate for Modifier: As a food item, cake is taxed at a rate of 6.5%, but one of its possible non-edible decorations (such as a bow or a candle) is taxed at a rate of 4% as a retail item. Cake is configured as a menu item while the bow and candle are optional modifiers.


- Modifier Tax Rate Overrides Parent Menu Item Tax Rate: A cold ham and cheese sandwich is normally taxed at 5%. However, if the customer requests that it be heated, it is taxed at the higher rate of 7%. The ham and cheese sandwich is configured as a menu item and `hot` is configured as an optional modifier.



#### Tax functionality interaction

The modifier tax behavior feature interacts with other tax functionality as follows:

- Tax Inclusion Setting: A modifier option always inherits its tax inclusion setting from its parent item. Configuring a modifier to either have a specific tax rate or override its parent item’s tax rate will not change the tax inclusion for a modifier or its parent item.


- Take Out Tax: If a tax rate is configured with a Take Out rate, this rate will be charged on the modifier when the parent item's dining option uses the Take Out dining behavior.


- Smart Tax: A modifier option always inherits the tax inclusion setting from its parent item. If the parent item's tax inclusion setting is changed as a result of smart tax, this will also apply to its modifiers even if they are set to a different rate or set to override the tax rate of the parent item.=


- Size Pricing: If a menu item is configured with the size pricing strategy and any of the size modifiers are set to either have a unique tax rate or override the tax rate of the parent item, the tax rate configured on the modifier will apply to the price of the parent item and the tax rate configured for the menu item will be ignored.


- Tax Exemption: If an order is set to Tax Exempt on the Toast POS device, the Modifier Tax Behavior setting will be ignored and no tax is charged for the modifier option.


- Master Menu Management: If a modifier is versioned, the Modifier Tax Behavior setting can be changed on a specific version without affecting the setting on the other versions.



#### Configuring taxes on modifiers

The following configuration procedures require that you access the detail page for modifier option's item reference. For instructions on how to view this page, see [Understanding a modifier item reference](adminPricingModifierOptions.html#adminUnderstandingAModifierOptionsItemReference).

##### Configuring unique tax rates

You can configure with a tax rate for a modifier option which is different from the tax configured for its parent menu item. The modifier option's unique tax rate is applied separately from the menu item tax rate.

**Procedure 6.123. To configure a unique tax rate for a modifier**

1. Locate the modifier you want to configure.


2. Select the arrow on the modifier to access its menu item reference.

![Opening the menu item reference for a modifier.](https://doc.toasttab.com/doc/media/tax-modifier-tax-rate.png)


3. Scroll to the bottom of the menu item page to the Taxes section. In the Inherit Tax Rates from Menu Group option, select No, specify tax rates here.

![Selecting the option to specify tax rates here.](https://doc.toasttab.com/doc/media/tax-modifier-inherit-tax-rate.png)


4. Select a tax rate from the Applicable taxes section. In this example, ME STATE TAX (8%) is selected.

![Selecting a configured tax rate for the modifier.](https://doc.toasttab.com/doc/media/tax-modifier-applicable-tax.png)


5. For the Modifier Tax Behavior option, select Unique tax rate applied to modifiers.

![Selecting the unique tax tax rate for the modifier.](https://doc.toasttab.com/doc/media/tax-modifier-unique-tax.png)


6. Save and publish your changes.



##### Configuring override tax rates

You can configure with a tax rate for a modifier option which is different from the tax configured for its parent menu item and which overrides the parent item's tax rate. In this case, both the modifier option and its parent item are taxed using the rate configured for the modifier option.

1. Locate the modifier you want to configure.


2. Select the arrow on the modifier to access its menu item reference.

![Opening the menu item reference for a modifier.](https://doc.toasttab.com/doc/media/tax-override-tax-rate.png)


3. Scroll to the bottom of the menu item page to the Taxes section. In the Inherit Tax Rates from Menu Group option, select No, specify tax rates here.

![Selecting the option to specify tax rates here.](https://doc.toasttab.com/doc/media/tax-inherit-override-tax-rate.png)


4. Select a tax rate from the Applicable taxes section. In this example, CA SPECIAL TAX (1.38%) is selected.

![Selecting a configured tax rate for the modifier.](https://doc.toasttab.com/doc/media/tax-override-applicable-tax.png)


5. For the Modifier Tax Behavior option, select Modifier tax rate overrides item tax rate.

![Selecting the override tax tax rate for the modifier.](https://doc.toasttab.com/doc/media/tax-modifier-override-tax.png)


6. Save and publish your changes.



##### Configuring inherited tax rates

If you want the unique or override tax rate setting to no longer apply and want the modifier to inherit its tax rate from its parent item, simply change the Modifier Tax Behaviorsetting to the Inherit item tax rate option. This will cause the modifier to ignore any selected tax rates in the Applicable taxes section.

**Procedure 6.124. To configure a modifier to inherit its tax rate from its parent menu item**

1. Locate the modifier you want to configure.


2. Select the arrow on the modifier to access its menu item reference

![Opening the menu item reference for a modifier.](https://doc.toasttab.com/doc/media/tax-override-tax-rate.png)


3. Scroll to the bottom of the menu item page to the Taxes section. For the Modifier Tax Behavior option, select Inherit item tax rate.

![Selecting the unique tax tax rate for the modifier.](https://doc.toasttab.com/doc/media/tax-modifier-inherit-tax.png)

In this example, the modifier will ignore the Retail Tax that is selected in the Applicable taxes section and instead use the tax rate configured for the parent menu item.


4. Save and publish your changes.



