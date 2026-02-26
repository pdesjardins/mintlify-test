---
title: "Smart tax"
id: adminSmartTax
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminTaxesOmitChunkFromSearchIndex.md
parentSectionTitle: "Taxes"
previousSectionFile: adminGuide-adminTaxesOnModifiers.md
previousSectionTitle: "Taxes on modifiers"
nextSectionFile: adminGuide-adminMarketplaceFacilitatorTaxPayments.md
nextSectionTitle: "Marketplace facilitator tax payments"
externalReferences: [https://central.toasttab.com/s/article/Creating-and-Assigning-Revenue-Centers]
excerpt: "The smart tax feature allows a restaurant to specify that a menu item's price includes tax when it is ordered in one..."
keywords: ["smart"]
procedures: 1
codeExamples: 0
---

The smart tax feature allows a restaurant to specify that a menu item's price includes tax when it is ordered in one section of the restaurant and does not include tax when it is ordered in another section of the restaurant. For example, a guest can order an item at either the bar or in the main dining room. To prevent bartenders from having to handle coins, which can slow down service, and to make tipping easier, you want the price of the item to be a whole number that includes tax when it is ordered at the bar. In the main dining room, where speed of service is less of a concern, you don't want the item's price to include tax, so that you don't lose out on the extra revenue.

To better understand the effect of tax inclusion on your revenue, consider an item that has a price of $10 and a tax rate of 7%. When tax is included, the Toast platform calculates a price and tax combination that equals the price you have set but also covers any applicable taxes. In this case, the guest pays $10 ($9.35 for the item and $0.65 for the tax) and your revenue is $9.35:

- $9.35 item price x .07 tax rate = $0.65 tax


- $9.35 item price + $0.65 tax = $10 price with tax included


- Your revenue is $9.35



When tax is not included, the guest pays $10.70 ($10 for the item and $0.70 for the tax) and your revenue is $10:

- $10.00 item price x .07 tax rate = $0.70 in tax


- $10.00 item price + $0.70 tax = $10 price without tax included


- Your revenue is $10



Your sales reports display the item price and tax amount that the Toast platform has calculated for any tax included items, so you can see the breakdown of revenue versus tax when tax is included.

**Procedure 6.125. To use smart tax**

1. Turn on the smart tax feature in Toast Web:

- [Access Toast Web](adminGuide-adminAccessToastAdminBackend).


- Choose Front of house &gt; Order screen setup &gt; UI options to open the UI Optionspage.


- In the Tax options section, set Smart tax to On.


- Save your changes.




2. Turn on smart tax for the menu components that should use it:

- Choose Menus &gt; Bulk management &gt; Advanced properties to open the Advanced properties page.


- From the Show/Hide drop-down menu, select Tax Inclusion Option to add that column to the view.


- Expand your menu hierarchy and choose Smart Tax in the Tax Inclusion Optioncolumn for the menu entities you want to apply smart tax to. You can apply smart tax to menus, menu groups, or menu items.


- Save your changes.




3. Create revenue centers for your restaurant sections (for example, Bar and Dining Room). When you create the revenue centers, turn on the Smart Tax setting for the revenue centers where you want to tax *to be included* (the Bar, in this example). See this [Toast Central article](https://central.toasttab.com/s/article/Creating-and-Assigning-Revenue-Centers) for detailed instructions on creating revenue centers.


4. Publish all your changes in Toast Web.


5. Configure the Toast POS devices in the restaurant to be associated with the revenue centers you created. For example, configure the bar POS device to be associated with the Bar revenue center and the dining room POS device to be associated with the Dining Room revenue center. Alternatively, you can configure specific tables to be associated with the different revenue centers. See this [Toast Central article](https://central.toasttab.com/s/article/Creating-and-Assigning-Revenue-Centers) for detailed instructions on associated revenue centers with devices and tables.



With this configuration, when menu items are ordered, their tax inclusion status will be determined by the revenue center associated with the POS device that placed the order or the table the ordered was placed for.



> **Note**
> 
> For the smart tax feature to work properly, all menu items that might be ordered at the revenue center that has Smart Tax enabled should have their Tax Inclusion Option set to Smart Tax (either by inheriting the value from a parent menu or menu group, or by having it set explicitly on the menu item). If a mix of menu items are ordered where some use smart tax and others don't, then the Toast platform ignores the Smart Tax setting and treats all of the menu items as if tax is not included in their prices.


