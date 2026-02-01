---
title: "Prep stations and printers for enterprises"
id: managingPrepStationsAndPrintersForEnterprises
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformMultiLocationOmitChunkFromSearchIndex.md
parentSectionTitle: "Chapter 5. Multiple restaurant locations"
previousSectionFile: adminGuide-platformAboutTheNumberColumn.md
previousSectionTitle: "About the Number column"
nextSectionFile: adminGuide-specifyingTaxRatesForEnterprisesOmitChunkFromSearchIndex.md
nextSectionTitle: "Tax rates for enterprises"
excerpt: "Similar to tax rates, Toast support recommends that, in an enterprise environment, you handle prep stations by creating a master..."
procedures: 3
codeExamples: 0
---

Similar to [tax rates](adminCreatingMasterTaxRates.html), Toast support recommends that, in an enterprise environment, you handle prep stations by creating a master version of each prep station and then creating location-specific versions of those masters for each location. This configuration makes it easier to assign prep stations to menu groups and items because only the master version of each prep station is shown, either on the Advanced properties page or on the menu entity's details page, reducing the number of prep stations you have to pick from (see [Creating a master version with location-specific versions for every location](understandingHowAndWhenToUseVersioning.html#creatingAMasterVersionWithLocationSpecificVersionsForEveryLocation)for more information). When you select a master prep station for a menu entity, the Toast platform automatically calculates which version of the prep station to use at each given location.

Also similar to tax rates, you should remove any auto-created prep stations before creating the masters and their location-specific versions.

Unlike tax rates, printer configuration does not get shared between locations because printers can only physically exist in one location at a time. The expectation is that you will have a set of printers for each location, configured exclusively for that location with the Target and Owner fields set to that location. You can then assign those location-specific printers to the location-specific versions of each prep station. In an enterprise environment, therefore, the workflow is as follows:

- You archive any auto-created prep stations.


- You create master prep stations and accompanying location-specific versions of the prep stations.


- You create location-specific printers.


- You configure the location-specific prep stations to use the location-specific printers.


- You assign the master prep stations to your menus/menu groups/menu items as needed.


- When a menu item is ordered, the Toast platform determines which location-specific version of the master prep station to use for the item.


- That location-specific prep station determines which location-specific printer to use and sends the menu item to it.



For example, assuming the configuration in the illustration below, when the customer orders Trout at the Boston location, the Boston version of the Hot Station prep station is used and it sends the Trout order to the Boston printer.

![Image](https://doc.toasttab.com/doc/media/prep-stations-and-printers-for-enterprise.png)

**Procedure 5.13. To archive auto-created prep stations**

1. [Log in to Toast Web](adminAccessToastAdminBackend.html).


2. Choose Kitchen \> Kitchen stations \> Prep stations to open the Prep stationspage.


3. Use the You are viewing menu to show the prep stations for the corporate restaurant group (the corporate restaurant group is your top-level restaurant group and it should show all locations). See [Filtering pages](filteringPagesForSpecificRestaurantGroupsAndLocations.html) for information on the You are viewing menu.


4. Click the actions button for the prep station you want to archive and choose Archive from the menu.

![Image](https://doc.toasttab.com/doc/media/actions_button.PNG)


5. Click Save.


6. Repeat these steps for the other prep stations that were automatically created.


7. Continue with the [next procedure](managingPrepStationsAndPrintersForEnterprises.html#toCreateMasterPrepStations) to create master prep stations.



**Procedure 5.14. To create master prep stations**

1. Choose Kitchen \> Kitchen stations \> Prep stations to open the Prep stationspage.


2. Use the You are viewing menu to show the prep stations for the corporate restaurant group (this group will show all locations). See [Filtering pages](filteringPagesForSpecificRestaurantGroupsAndLocations.html) for information on the You are viewing menu.


3. Click the plus button to add a new prep station.

![Image](https://doc.toasttab.com/doc/media/plus_button.PNG)


4. Enter a name for the prep station and set its other properties.


5. Set the Target and Ownerfields to the corporate restaurant group.


6. Click Save.


7. Repeat these steps to add any other master prep stations your restaurants use.


8. Continue with the [Procedure 5.15, “To create location-specific prep stations”](managingPrepStationsAndPrintersForEnterprises.html#toCreateLocationSpecificPrepStations) procedure.



**Procedure 5.15. To create location-specific prep stations**

1. Choose Kitchen \> Kitchen stations \> Prep stations to open the Prep stationspage.


2. Use the You are viewing menu to show the prep stations for the corporate restaurant group (this group should show all locations). See [Filtering pages](filteringPagesForSpecificRestaurantGroupsAndLocations.html) for information on the You are viewing menu.


3. Click the actions button for a master prep station and choose New Version.

![Image](https://doc.toasttab.com/doc/media/actions_button.PNG)


4. Set the Target field to a location in your enterprise. The Owner field is automatically set to that same location. You can leave the Owner field as is or set it to some other point in the restaurant group hierarchy (the value you choose for this setting should be driven by who in your enterprise should be able to edit the prep station).


5. Click Submit. The new version is added to the Prep Stations table.


6. Configure the new version's properties so that they are appropriate for the location you chose in step 4.


7. Click Save.


8. Repeat these steps to create a version of each master prep station for every location in your enterprise.


9. Publish your changes using the Publish configpage. See [Publishing changes for multiple locations](publishingChangesForMultipleLocations.html) for information on accessing and using that page.



