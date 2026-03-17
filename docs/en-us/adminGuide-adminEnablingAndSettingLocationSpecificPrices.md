---
title: "Enabling and setting location-specific prices"
id: adminEnablingAndSettingLocationSpecificPrices
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminSettingLocationSpecificPricesOmitChunkFromSearchIndex.md
parentSectionTitle: "Location-specific prices"
previousSectionFile: adminGuide-adminLocationSpecificPricesAndVersions.md
previousSectionTitle: "Location-specific prices and versions"
nextSectionFile: adminGuide-adminDeletingLocationSpecificPrices.md
nextSectionTitle: "Deleting location-specific prices"
excerpt: "You..."
keywords: ["enabling", "setting", "locationspecific", "prices"]
procedures: 2
codeExamples: 0
---

You must enable location-specific pricing on the details page for a menu item. After you do so, you can edit the location-specific prices either on the **Price editor** page or on the menu item's details page.



> **Note**
> 
> If you have many locations, the **Price editor**page can slow down and you may have to edit your location-specific prices on the menu items' detail pages instead.


**Procedure 5.6. To enable location-specific pricing for a menu item**

1. [Log in to Toast Web](adminGuide-adminAccessToastAdminBackend).


2. Choose **Menus &gt; Bulk management &gt; Advanced properties** to open the **Advanced properties** page.


3. Use the **You are viewing** menu to filter the page so that you see the menu that contains the menu item you want to set location-specific prices for.See [Filtering pages](adminGuide-filteringPagesForSpecificRestaurantGroupsAndLocations)for information on the **You are viewing**menu.


4. Expand the menu and menu groups as needed to locate the menu item, then click the menu item's name to view its details page.


5. In the **Pricing** section, enable **Location Specific Price**. The **Location Prices** table appears with an entry for the first location-specific price. Toast support recommends specifying a price for the top-level restaurant group for this first entry so that any given location will have at least the corporate price to draw from in the event that a more specific price is not specified. To do so, make sure the top-level restaurant group is chosen in the **Location** column and enter a price in the **Price** column.


6. Click **Save**.


7. Follow the next procedure to set additional location-specific prices for the menu item.



**Procedure 5.7. To set location-specific prices for a menu item using the Price Editor**

1. Choose **Menus &gt; Bulk management &gt; Price editor** to open the **Price editor**page.


2. The **You are viewing** menu retains the settings you specified in the previous procedure, so the menu item should be available to edit on this page. To make it easier to find location-specific prices on the **Price editor**page, you can also click the **All Strategies** menu and choose **Location Specific Price**.


3. Expand the menu and menu groups as needed to locate the menu item you enabled location-specific pricing for. Location-specific prices are marked with a location symbol and the name of the restaurant group or location that the price applies to, for example:

![Image](https://doc.toasttab.com/doc/media/location_specific_prices_icon.PNG)


4. Click in the **Price** field for the initial location-specific price and enter a price.


5. Hover your mouse over the **Price** field for the target to see the plus sign, then click the plus sign to add a new location-specific price.

![Image](https://doc.toasttab.com/doc/media/location_specific_prices_add_icon.png)

A new row is added to the table.

![Image](https://doc.toasttab.com/doc/media/location_specific_prices_new_row.png)


6. Choose a restaurant group or location from the drop-down list, enter a price for the group/location, and click the **Save** button in the table. Note that the locations and restaurant groups you see in this drop-down list are limited by the selections you made in the **You are viewing**menu.


7. Repeat these steps to add location-specific prices for any restaurant groups or locations that require them.


8. Click the **Save** button at the top right of the **Price editor** page.


9. Publish your changes using the **Publish config** page. See [Publishing changes for multiple locations](adminGuide-publishingChangesForMultipleLocations) for information on accessing and using that page.



The Toast platform maintains your location-specific price configuration for you, even if you change the pricing strategy for an item. In other words, if you switch the pricing strategy of a menu item from **Location Specific Price** to some other strategy, and then switch back, the location-specific prices you originally specified will still be available.

