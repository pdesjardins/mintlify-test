---
title: "All versions of a menu use the same menu-specific prices"
id: platformAllVersionsOfAMenuUseTheSameMenuSpecificPrices
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformMenuSpecificPricesForMLMOmitChunkFromSearchIndex.md
parentSectionTitle: "Menu-specific prices"
previousSectionFile: adminGuide-platformMenuSpecificPricesForMultiLocationRestaurants.md
previousSectionTitle: "Menu-specific prices for multi-location restaurants"
nextSectionFile: adminGuide-platformEachVersionOfAMenuHasItsOwnMenuSpecificPrices.md
nextSectionTitle: "Each version of a menu has its own menu-specific prices"
excerpt: "Configuring menu-specific prices for a menu that has multiple versions follows the same basic procedure as configuring menu-specific prices for a menu that has only one version. The only difference..."
keywords: ["versions", "menu", "same", "menuspecific", "prices"]
procedures: 1
codeExamples: 0
---

Configuring menu-specific prices for a menu that has multiple versions follows the same basic procedure as configuring menu-specific prices for a menu that has only one version. The only difference is that, as with all changes affecting multiple locations, you must publish changes to each location that is affected.

**Procedure 5.11. To create menu-specific prices for a menu item on a versioned menu**

1. In the **Pricing Strategy** section of the menu item's details page, select **Menu Specific Price**.


2. In the **Base Price** field, enter a base price for the menu item. This price is used if a menu-specific price for the item cannot be calculated. For example, if you added the menu item to a newly created menu but neglected to update the menu item with a menu-specific price for the new menu.


3. In the **Menu Prices** grid, enter the price to be used for the menu item when it is ordered from each menu.



> **Note**
> 
> You only need to enter a price for each menu that contains the menu item but it is a best practice to enter a price for all menus in case you add the menu item to another menu in the future.



4. Save your changes.


5. Because these changes affect multiple locations, you publish them using the **Publish Config** page, where you can publish changes to multiple locations at once.

- In the left-hand navigation pane, select **Toast account**.


- Go to the **Publishing** section and select **Publish Config**. (Note, previously, the **Publishing** section was called **Internal tools**.)


- If necessary, from the **You are viewing**menu, choose the top-level restaurant group so that you can see all your locations and select **Update**.


- In the **Locations** table, select the locations that are affected by the pricing changes you have made.



> **Note**
> 
> If you are unsure about which locations are affected by your changes and require publishing, see [About the Number column](adminGuide-platformAboutTheNumberColumn) for information on using the **Number** column to determine which locations require publishing.



- Select **Publish Select Restaurants**.





> **Note**
> 
> For more info on the **Publish Config** page, see [Publishing changes for multiple locations](adminGuide-publishingChangesForMultipleLocations).




