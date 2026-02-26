---
title: "Manually assigning applicable taxes"
id: manuallyAssigningApplicableTaxes
type: section
documentId: adminGuide
parentSectionFile: adminGuide-specifyingTaxRatesForEnterprisesOmitChunkFromSearchIndex.md
parentSectionTitle: "Tax rates for enterprises"
previousSectionFile: adminGuide-adminCreatingMasterTaxRates.md
previousSectionTitle: "Creating master tax rates"
nextSectionFile: adminGuide-usingDefaultTaxRatesAndInheritanceToAssignApplicableTaxes.md
nextSectionTitle: "Using default tax rates and inheritance to assign applicable taxes"
excerpt: "The preferred technique for managing taxes is to manually assign the master versions of your tax rates to your menus. With this configuration, the correct version of the tax will be applied to a..."
keywords: ["manually", "assigning", "applicable", "taxes"]
procedures: 1
codeExamples: 0
---

The preferred technique for managing taxes is to manually assign the master versions of your tax rates to your menus. With this configuration, the correct version of the tax will be applied to a menu, depending on location. For example, assuming the following tax rates, if the current location is Boston, the state tax would be 6.25% while when the current location is Atlanta, the state tax is 4%.

![Image](https://doc.toasttab.com/doc/media/tax_rates_no_defaults.PNG)

**Procedure 5.19. To assign tax rates manually**

1. Choose Menus &gt; Menu management &gt; Tax rates setup to open the Tax ratespage.


2. Use the You are viewing menu to show the tax rates for the corporate restaurant group (this group should show all locations). See [Filtering pages](docs/en-us/adminGuide-filteringPagesForSpecificRestaurantGroupsAndLocations)for information on the You are viewingmenu.


3. Make sure your tax rates are not marked as default.


4. Choose Menus &gt; Bulk management &gt; Advanced properties to open the Advanced properties page.


5. Use the You are viewing menu to view the menus you want to assign taxes to.


6. Click the Show/Hide menu, scroll down to the Taxes section and check the Applicable Taxes option to display that column on the Advanced properties page.


7. In the row for the menu you want to apply taxes to, click the Applicable Taxes field.


8. All of the master tax rates you have created are listed below the line in the Applicable Taxes field. Click a master tax rate to select it and apply its taxes to this menu. To deselect a master tax rate, click it again to remove the checkmark. Check all of the master tax rates that should apply to this menu, for example:

![Image](https://doc.toasttab.com/doc/media/tax_rates_manually_assigned_adv_props_page.PNG)


9. Click Save.


10. Repeat these steps for each menu.


11. Publish your changes using the Publish config page. See [Publishing changes for multiple locations](docs/en-us/adminGuide-publishingChangesForMultipleLocations) for information on accessing and using that page.



