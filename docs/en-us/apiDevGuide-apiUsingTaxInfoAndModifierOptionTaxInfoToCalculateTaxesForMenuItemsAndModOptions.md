---
title: "Using taxInfo and modifierOptionTaxInfo to calculate taxes for menu items and modifier options"
id: apiUsingTaxInfoAndModifierOptionTaxInfoToCalculateTaxesForMenuItemsAndModOptions
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiGettingMenuInformationOmitChunkFromSearchIndex.md
parentSectionTitle: "Getting menu information"
previousSectionFile: apiDevGuide-apiUsingPricingRulesAndPricingStrategyToCalculatePrices_V2.md
previousSectionTitle: "Using PricingRules and PricingStrategy to calculate prices"
nextSectionFile: apiDevGuide-apiUsingMenusApiDataToSubmitProperlyFormedOrders_V2.md
nextSectionTitle: "Using menus API data to submit properly formed orders"
excerpt: "In Toast Web, you can configure a modifier option's underlying item reference to use one of the following tax behaviors:"
keywords: ["taxinfo", "modifieroptiontaxinfo", "calculate", "taxes", "menu", "items", "modifier", "options", "modifierOptionTaxInfo", "ModifierOption"]
procedures: 0
codeExamples: 4
---

### Using taxInfo and modifierOptionTaxInfo to calculate taxes for menu items and modifier options

In Toast Web, you can configure a modifier option's underlying [item reference](adminPricingModifierOptions.html#adminUnderstandingAModifierOptionsItemReference) to use one of the following tax behaviors:

- Inherit item tax rate: The modifier is taxed at the same rate as the parent menu item. For example, if the menu item is taxed at 6.25%, then the modifier option is also taxed at the 6.25% rate. This is the default behavior.


- Unique tax rate applied to modifiers: The modifier option is configured with a tax rate that is different from the parent menu item and is applied separately from the menu item tax rate. For example, a menu item is taxed at a 6.25% rate and the modifier option is taxed at a 2.75% rate.

If the menu item has multiple modifier options, each modifier option may have its own unique tax rate. For example, a pizza menu item is taxed at 6.25%, a pineapple modifier option has a unique tax rate of 4.25%, and a pepperoni modifier option has a unique tax rate of 3.50%.


- Modifier tax rate overrides item tax rate: The modifier option has a different tax rate than its parent menu item and the modifier option tax rate overrides the menu item tax rate. This means that both the menu item and the modifier option are taxed at the rate configured for the modifier option. For example, if the menu item is configured for a 6.25% tax rate and the modifier option is configured for a 2.75% tax rate, when that modifier option is applied to the menu item, both are taxed at the 2.75% tax rate. Note that the menu item's tax rate is overridden only if the modifier option is added to the menu item on a Toast POS device. The modifier option may be available to apply to the menu item, but if it is not added to the menu item on an order, then the menu item's tax rate is not overridden.

Also, if more than one modifier option that is configured to override the menu item's tax rates is added to a menu item, the Toast platform defaults to using the menu item's tax rate and ignores all of the modifier option tax rates.



These three settings are represented by the `modifierOptionTaxInfo` value of the `ModifierOption` object that is returned by the `/menus` endpoint of the menus API. You can use the `modifierOptionTaxInfo` value in conjunction with the `taxInfo` value on a `MenuItem` object to determine the tax on menu items and the modifier options that are applied to them when an order is placed on the Toast platform.



> **Note**
> 
> For detailed instructions for configuring the tax behavior of a modifier option's item reference in Toast Web, see [Taxes on modifiers](adminTaxesOnModifiers.html).




> **Note**
> 
> The `modifierOptionTaxInfo` value always reflects the parent menu item tax rate, unless Toast grants the restaurant the ability to override modifier tax rates. If this permission is not granted, then even if the restaurant configured the modifier with a different tax rate, `modifierOptionTaxInfo` reflects the parent menu item tax rate.


To understand how to calculate menu item and modifier option taxes, consider the following example of three modifier options that apply to the same menu item but use different tax behavior configurations. To begin, we need to know the tax rate assigned to the menu item, which is specified in the menu item's `taxInfo`value. The Cheese Pizza menu item below uses the tax rate identified by the GUID `1a2b`:

```
"menuItems": [
  \{
    "name": "Cheese Pizza",
    ...
    "taxInfo": [
      "1a2b"
    ],
    ...
  \},
  ...
]
```

Modifier Option 1, shown below, is configured in Toast Web to inherit its tax rate from a parent menu item. As such, its `taxRateGuids` value contains the same tax rate GUID as Cheese Pizza (`1a2b`) and its `overrideItemTaxRates` value is set to `false`. With this scenario, you would use the `taxInfo` value in the `MenuItem` object (`1a2b`) to determine the tax rate for Cheese Pizza and the `taxRateGuids` value in the `ModifierOptionTaxInfo` object (also `1a2b`) to determine the tax rate for Modifier Option 1.

**Example 4.9. Modifier Option 1 inherits the parent menu item's tax rate**

```
"modifierOptionReferences": \{
  "7": \{
    "referenceId": 7,
    "name": "Modifier Option 1",
    ...
    "modifierOptionTaxInfo": [
      "taxRateGuids": ["1a2b"],
      "overrideItemTaxRates": false
    ],
    ...
  \},
  ...
\},
```

  
Modifier Option 2 is configured to use its own unique tax rate. Its `taxRateGuids` value contains the tax rate GUID from its underlying modifier option item reference (`3c4d`) and its `overrideItemTaxRates` value is set to `false`. With this scenario, you use the `taxInfo` value in the `MenuItem` object (`1a2b`) to determine the tax rate for Cheese Pizza and the `taxRateGuids` value in the `ModifierOptionTaxInfo` object (`3c4d`) to determine the tax rate for Modifier Option 2.

**Example 4.10. Modifier Option 2 has its own unique tax rate**

```
"modifierOptionReferences": \{
  "9": \{
    "referenceId": 9,
    "name": "Modifier Option 2",
    ...
    "modifierOptionTaxInfo": [
      "taxRateGuids": ["3c4d"],
      "overrideItemTaxRates": false
    ],
    ...
  \},
  ...
\},
```

  
Modifier Option 3 is configured so that its tax rate overrides the parent menu item's tax rate. Its `taxRateGuids` value contains the tax rate GUID from its underlying modifier option item reference (`3c4d) `and its `overrideItemTaxRates`value is set to `true`. When Modifier Option 3 is applied to Cheese Pizza in an order, the `taxInfo` value in the `MenuItem` object for Cheese Pizza (`1a2b`) should be overridden by the `taxRateGuids` value in the `ModifierOptionTaxInfo` object for Modifier Option 3 (`3c4d`). This means your integration should use the `3c4d` tax rate for both Cheese Pizza and Modifier Option 3.

**Example 4.11. Modifier Option 3's tax rate overrides the parent menu item's tax rate**

```
"modifierOptionReferences": \{
  "12": \{
    "referenceId": 12,
    "name": "Modifier Option 3",
    ...
    "modifierOptionTaxInfo": [
      "taxRateGuids": ["3c4d"],
      "overrideItemTaxRates": true
    ],
    ...
  \},
  ...
\},
```

  


> **Important**
> 
> It is not shown in the examples in this section but the `ModifierOption` object still contains the original `taxInfo` value that stored the tax rate GUIDs for a modifier option's parent menu item. Your integration should switch from using the `taxInfo` value to using the `modifierOptionTaxInfo` value. The `taxInfo`value is no longer accurate for modifier options that do not inherit their tax rates from a parent menu item.


#### Impact of tax-related features not returned in the ModifierOptionTaxInfo object

There are other tax-related features that can impact the tax of a modifier option, such as tax inclusion and smart tax, that *are not* returned in the `ModifierOptionTaxInfo` object. More information on these features and their impact on modifier option taxes is provided in [Tax functionality interaction](adminTaxesOnModifiers.html#adminModifierTaxInteraction).

