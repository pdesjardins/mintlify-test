---
title: "Each version of a menu has its own menu-specific prices"
id: platformEachVersionOfAMenuHasItsOwnMenuSpecificPrices
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformMenuSpecificPricesForMLMOmitChunkFromSearchIndex.md
parentSectionTitle: "Menu-specific prices"
previousSectionFile: adminGuide-platformAllVersionsOfAMenuUseTheSameMenuSpecificPrices.md
previousSectionTitle: "All versions of a menu use the same menu-specific prices"
nextSectionFile: adminGuide-platformAboutTheNumberColumn.md
nextSectionTitle: "About the Number column"
excerpt: "This section provides detailed instructions for creating a pricing configuration where each version of a menu has its own menu-specific prices for a menu item, for example:"
keywords: [each,version,menu,menuspecific,prices]
procedures: 1
codeExamples: 1
---

### Each version of a menu has its own menu-specific prices

This section provides detailed instructions for creating a pricing configuration where each version of a menu has its own menu-specific prices for a menu item, for example:

```
At the Boston location:
  On the Lunch menu, Crab Cakes cost $10
  On the Dinner menu, Crab Cakes cost $14

At the Portland location:
  On the Lunch menu, Crab Cakes cost $12
  On the Dinner menu, Crab Cakes cost $16
```

In general, this procedure follows this flow:

- Set the pricing strategy for the menu item to Location Specific Price.


- Add rows to the Location Prices table for each version of the menu. For example, if you have a version of the menu for Boston and another for Portland, you create two rows in the Location Prices table, one for Boston and another for Portland.


- In each location's row, specify nested menu-specific prices for the different menus.


- Publish your changes to each affected location.



**Procedure 5.12. To configure each version of a menu to have its own menu-specific prices for a menu item**

1. [Log in to Toast Web](adminAccessToastAdminBackend.html).


2. Select Menus from the left-hand navigation bar.


3. Select Bulk management \> Advanced properties to open the Advanced Properties page.


4. From the You are viewing menu, choose your top-level restaurant group so that you can see your entire restaurant group hierarchy and select Update.


5. Expand one of the menus that contains the menu item you want to set prices for and select it to open its details page.


6. In the Pricing section, set the Pricing Strategy to Location Specific Price.

The Location Prices table appears with a row for the top-level restaurant group in your [restaurant group hierarchy](restaurantGroupsAndSubgroups.html).

The Toast platform requires that you specify a location-specific price for the top-level restaurant group so that any given location will have at least the corporate price to draw from in the event that a more specific price is not specified.


7. Add rows to the Location Prices table for each version of the menu:

- Select Add. A new row is added to the Location Prices table.


- The first column of this row contains a drop-down menu that shows your restaurant group hierarchy. Select this drop-down menu and choose the restaurant group or location where this location-specific price should apply.


- Repeat this step for any additional locations that you need to define location-specific prices for.


- Select Save. After you save, the location names in the newly added rows of the Location Prices table become selectable links.




8. Specify nested menu-specific prices:

- In the Location Prices table, select one of the location name links. You see the Location-Specific Price page.


- In the Pricing Strategy section, select Menu Specific Price. The Base Price field and the Menu Pricestable appear.

![Example of the Pricing Strategy section with the Base Price field and the Menu Prices table showing.](https://doc.toasttab.com/doc/media/menus-mlm-msp-nested-lsp-page.png)


- Enter a price in the Base Price field. This price is used if a menu-specific price for the item cannot be calculated. For example, if you added the menu item to a newly created menu but forgot to update the menu item with a menu-specific price for the new menu.


- Enter a price for each menu in the Menu Prices table.


- Save your changes.


- In the breadcrumbs at the top of the page, select the menu item's name to return to its details page.


- Repeat these steps for the other rows in the Location Prices table.




9. Because these changes affect multiple locations, you publish them using the Publish Config page, where you can publish changes to multiple locations at once.

- In the left-hand navigation pane, select Toast account.


- Go to the Publishing section and select Publish Config. (Note, previously, the Publishing section was called Internal tools.)


- If necessary, from the You are viewingmenu, choose the top-level restaurant group so that you can see all your locations and select Update.


- In the Locations table, select the locations that are affected by the pricing changes you have made.



> **Note**
> 
> If you are unsure about which locations are affected by your changes and require publishing, see [About the Number column](platformAboutTheNumberColumn.html) for information on using the Number column to determine which locations require publishing.



- Select Publish Select Restaurants.





> **Note**
> 
> For more info on the Publish Config page, see [Publishing changes for multiple locations](publishingChangesForMultipleLocations.html).




