---
title: "Fixed rates"
id: adminFixedTaxRates
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminTaxesOmitChunkFromSearchIndex.md
parentSectionTitle: "Taxes"
previousSectionFile: adminGuide-adminPercentTaxRates.md
previousSectionTitle: "Percent rates"
nextSectionFile: adminGuide-adminTaxTableRates.md
nextSectionTitle: "Tax table rates"
excerpt: "A fixed tax rate levies the same monetary amount on a menu item, regardless of its price. You would use a fixed tax rate for special cases, such as for bottle deposits."
keywords: ["fixed", "rates", "Fixed Rate", "Bottle Deposit"]
procedures: 1
codeExamples: 0
---

### Fixed rates

A fixed tax rate levies the same monetary amount on a menu item, regardless of its price. You would use a fixed tax rate for special cases, such as for bottle deposits.

Note that comping an order that has items with a fixed rate leaves the tax amount on the check total. When you comp an order that has items on it with a fixed tax rate, the tax remains as an open balance. This occurs whether only the item with the fixed rate is comped or if the entire order is comped.

**Procedure 6.120. To configure a fixed rate**

1. [Access Toast Web](adminAccessToastAdminBackend.html).


2. Choose Menus \> Menu management \> Settings \> Manage tax rates  to open the Tax rates page.


3. Click + Add Tax Rate.


4. In the Basic section of the New tax rate page, enter the configuration information for the tax rate:

- Name: Enter a name for the tax rate, such as `Fixed Rate` or `Bottle
            Deposit`.


- Target: Specifies the location in a restaurant group to which this tax rate applies. (This control is visible only if you have the enterprise module.) For information about targets, see [Targets](targets.html).


- Owner: Specifies which group level permission is needed to edit this tax rate. (This control is visible only if you have the enterprise module.) For information about owners, see [Owners and permissions](ownersAndPermissions.html).


- Import ID: Leave this field blank. It is for internal use only.


- Type: Select Fixed.


- Rate: Enter the monetary amount to be charged as a tax.


- Default: Select Yes to have the tax rate inherited by menus and menu items that are configured to inherit tax rates or select No to disable tax rate inheritance (for this setting, menus and menu items that do not inherit tax rates must be configured with specific tax rates).




5. Save and publish your changes.



