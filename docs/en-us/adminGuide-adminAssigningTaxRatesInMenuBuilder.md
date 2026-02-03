---
title: "Assigning tax rates and tax behavior"
id: adminAssigningTaxRatesInMenuBuilder
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminCreatingYourMenuUsingTheBasicMenuBuilderOmitChunkFromSearchIndex.md
parentSectionTitle: "Menu builder"
previousSectionFile: adminGuide-adminAssigningSalesCategories.md
previousSectionTitle: "Assigning sales categories"
nextSectionFile: adminGuide-platformSettingTimeBasedOrderingRulesForOnlineOrders.md
nextSectionTitle: "Setting time-based ordering rules for online orders"
excerpt: "During..."
keywords: ["assigning", "rates", "behavior"]
procedures: 0
codeExamples: 0
---

During the on-boarding process, you specify the tax rates that apply to your restaurant location. By default, these tax rates are inherited by any menus you create for the restaurant. According to the rules of menu inheritance, the tax rates also flow down to your menu groups, subgroups, and menu items in the following ways:

- Menu groups inherit their tax rates from their parent menus.


- Menu items and subgroups inherit their tax rates from their parent menu groups.



You can override tax rates on individual menus, menu groups, subgroups, or menu items as needed.

In addition to tax rates, Toast Web includes two tax behavior settings that allow you to specify that taxes are included in a menu item's price and takeout orders are exempt from taxes. You can set the tax behavior settings at the menu, menu group, subgroup, or menu item level and they follow the same rules of inheritance as tax rates. You can override these settings as needed on individual menu entities.

For more information on menu inheritance, see [Understanding inheritance](platformUnderstandingInheritance.html).

The following sections provide instructions for setting tax rates and behavior. They also provide more information about the tax behavior settings.

- [Setting tax rates and tax behavior](adminAssigningTaxRatesInMenuBuilder.html#platformSettingTaxRatesAndTaxBehavior)


- [Understanding tax inclusion](adminAssigningTaxRatesInMenuBuilder.html#platformUnderstandingTaxInclusion)


- [Understanding takeout tax exception](adminAssigningTaxRatesInMenuBuilder.html#platformUnderstandingTakeoutTaxException)



#### Setting tax rates and tax behavior

To override the inherited tax rates for a menu, menu group, or subgroup, go to the Taxes section of the entity's details page, select the link icon next to Tax rates to unlink the configuration, and then select the tax rates from the list. To override the Calculate prices with tax included or Takeout exception setting, select its link icon to unlink the configuration and then configure the setting as needed.

![Example of a menu group that does not inherit its tax rates and tax behavior settings.](https://doc.toasttab.com/doc/media/menu-builder-menu-group-does-not-inherit-tax-settings.png)

To configure a menu, menu group, or subgroup so it inherits its tax rates, select the link icon next to Tax ratesso the tax rates setting is grayed out. To inherit the Calculate prices with tax included or Takeout exception setting, select its link icon so that the setting is grayed out.

![Example of a menu group that inherits its tax rates and tax behavior settings.](https://doc.toasttab.com/doc/media/menu-builder-menu-group-inherits-tax-settings.png)

To override the inherited tax rates for a menu item, go to the Tax settings section on its details page, set its Inherit tax rates? setting to No, and then select the tax rates from the list. To override the Tax inclusion or Takeout tax exception setting, set Inherit tax inclusion? or Inherit takeout tax? to No and then configure the setting as needed. When you configure settings directly on a menu item, those settings apply *any time the menu item is ordered, from any menu path*.

![Example of a menu item that does not inherit its tax rates and tax behavior settings.](https://doc.toasttab.com/doc/media/menu-builder-item-does-not-inherit-tax-settings.png)

To configure a menu item so that it inherits its tax rates, set the Inherit tax rates? setting to Yes. To inherit the Tax inclusion or Takeout tax exceptionsetting, set the Inherit tax inclusion? or Inherit takeout tax? setting to Yes.

If you do not have any tax rates configured yet, you see a Manage tax rates link that you can select to go to the Tax rates page where you can create them. For more information on creating tax rates, see [Taxes overview](adminTaxesOverview.html).

#### Understanding tax inclusion

When tax is included in a menu item's price, the guest pays the price you have set and any applicable taxes are taken out of that price, instead of being added to it. Use this option when you want a guest's check total to be a round number. This eliminates the need for employees to deal with coins and makes tipping simpler to calculate. It can, however, decrease net revenue if the price you set does not account for applicable taxes.

To better understand the effect of tax inclusion on your revenue, consider an item that has a price of $10 and a tax rate of 7%. When tax is included, the Toast platform calculates a price and tax combination that equals the price you have set but also covers any applicable taxes. In this case, the guest pays $10 ($9.35 for the item and $0.65 for the tax) and your revenue is $9.35:

- $9.35 item price x .07 tax rate = $0.65 tax


- $9.35 item price + $0.65 tax = $10 price with tax included


- Your revenue is $9.35



When tax is not included, the guest pays $10.70 ($10 for the item and $0.70 for the tax) and your revenue is $10:

- $10.00 item price x .07 tax rate = $0.70 in tax


- $10.00 item price + $0.70 tax = $10 price without tax included


- Your revenue is $10



Your sales reports display the item price and tax amount that the Toast platform has calculated for any tax included items, so you can see the breakdown of revenue versus tax when tax is included.

For information on enabling tax inclusion, see [Setting tax rates and tax behavior](adminAssigningTaxRatesInMenuBuilder.html#platformSettingTaxRatesAndTaxBehavior).

#### Understanding takeout tax exception

For states that do not tax takeout orders, you can specify that menu items are tax-exempt when ordered for takeout. To determine if an order is a takeout order, the Toast platform looks at the dining option associated with the order and then it looks at that dining option's behavior. Dining options that use the Take Outbehavior are considered takeout orders and are not be taxed.

For more information on setting takeout tax exemption behavior, see [Setting tax rates and tax behavior](adminAssigningTaxRatesInMenuBuilder.html#platformSettingTaxRatesAndTaxBehavior).

For more information on dining options, see [Dining options](adminDiningOptions.html).

