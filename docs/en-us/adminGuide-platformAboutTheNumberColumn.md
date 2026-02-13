---
title: "About the Number column"
id: platformAboutTheNumberColumn
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformMenuSpecificPricesForMLMOmitChunkFromSearchIndex.md
parentSectionTitle: "Menu-specific prices"
previousSectionFile: adminGuide-platformEachVersionOfAMenuHasItsOwnMenuSpecificPrices.md
previousSectionTitle: "Each version of a menu has its own menu-specific prices"
nextSectionFile: adminGuide-managingPrepStationsAndPrintersForEnterprises.md
nextSectionTitle: "Prep stations and printers for enterprises"
excerpt: "For multi-location restaurants, a Number column is added the Menu Prices table. This additional column appears in the Menu Prices table on a menu item's details page:"
keywords: ["about", "number", "column"]
procedures: 0
codeExamples: 0
---

For multi-location restaurants, a Number column is added the Menu Prices table. This additional column appears in the Menu Prices table on a menu item's details page:

![Example of the Number column in the Menu Prices table on the menu items details page.](https://doc.toasttab.com/doc/media/menus-mlm-msp-number-column-item-details-page.png)

It also appears in the Menu Prices table for a nested menu-specific price on the Location Specific Price page.

![Example of the Number column in the Location Specific Price page.](https://doc.toasttab.com/doc/media/menus-mlm-msp-number-column-nested-lsp-page.png)

To understand the purpose of the Number column, you must understand how the Menu Prices table displays a menu with multiple versions.

The Menu Prices table has a single row for each menu, regardless of whether the menu has multiple versions or not. For example, in the illustrations above, the Lunch menu has a single row in the Menu Prices table, despite the fact that the Lunch menu has two different versions, one for the Boston location and another for the Portland location. When the Toast platform collapses a collection of menu versions into a single row in the Menu Prices table, it has to pick a name for the menu from the names assigned to the versions. If the versions have different names, then you will only see one of those names in the Menu Pricestable.

You can use the Number column to identify all of the menu versions represented by a single row in the Menu Prices table. By comparing the identifier you see in the Number column of the Menu Pricestable to the identifiers you see in the Number column of the Advanced Properties page, you can see how many versions of the menu exist and what locations use them.

For example, the Lunch menu in the Menu Pricestable above has an identifier ending in 0601. Looking at the Advanced Properties page below, you can see that there are two versions of the Lunch menu that have the same 0601 identifier. This means that the Lunch row in the Menu Prices table corresponds to two versions of the Lunch menu. Those versions are targeted at Boston and Portland, which means you must publish your pricing changes to the Boston and Portland locations.

![Example of the Number column on the Advanced Properties page.](https://doc.toasttab.com/doc/media/menus-mlm-msp-number-column-adv-props-page.png)





> **Note**
> 
> On the Advanced Properties page, be sure to choose your top-level restaurant group from the You are viewing menu and select Update. This ensures that you are viewing your entire restaurant group hierarchy and will see all the versions of each menu. Also, if you don't see the Number column on the Advanced Properties page, select the Show/Hidemenu and make sure Properties &gt; Number is selected.


