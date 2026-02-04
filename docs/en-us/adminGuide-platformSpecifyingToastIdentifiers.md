---
title: "Specifying Toast identifiers"
id: platformSpecifyingToastIdentifiers
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformMenusBulkMenuImportOmitChunkFromSearchIndex.md
parentSectionTitle: "Bulk menu imports"
previousSectionFile: adminGuide-platformUnderstandingTheOperationId.md
previousSectionTitle: "Understanding the operation ID"
nextSectionFile: adminGuide-platformFillingOutTheBulkImportSpreadsheet.md
nextSectionTitle: "Filling out a bulk import spreadsheet"
excerpt: "To complete a bulk import spreadsheet, you may need one or more Toast identifiers for the following entities:"
keywords: ["specifying", "toast", "identifiers", "versionID", "multiLocationID"]
procedures: 0
codeExamples: 0
---

To complete a bulk import spreadsheet, you may need one or more Toast identifiers for the following entities:

- Menu entities


- Prep stations


- Sales categories


- Tax rates


- Location groups (formerly called *restaurant groups*)


- Individual restaurant locations



You use these identifiers to provide information about the menu entities you are creating or attaching. For example, to attach a modifier group to an existing menu item, you need the existing menu item's `versionID` (this identifier is called GUID in Toast Web). To specify a prep station for a menu item or modifier that you are creating, you need the prep station's `multiLocationID` (this identifier is called Number in Toast Web).

The rest of this section describes where to find the identifiers you need to fill out a bulk import spreadsheet.

### Identifiers for menu entities

To see identifiers for menu entities, Toast support must enable the Order API product module for your restaurant. With this module enabled, you can see a menu entity's identifiers on its details page:

![Example of a menu details page showing the location of the GUID and Number fields.](https://doc.toasttab.com/doc/media/menus-bulk-import-menu-entity-ids.png)

The GUID field corresponds to the menu entity's `versionID`. The Number field corresponds to the menu entity's `multiLocationId`.

### Identifiers for prep stations, sales categories, and tax rates

To see identifiers for prep stations, sales categories, and tax rates, Toast support must enable the multi-location management product module for your restaurant locations. When this module is enabled, a Number column is added to the listing page for each entity type that contains the `multiLocationId` for the entity. For example, this illustration shows the Number column on the Prep Stations page:

![Example of Prep Stations page showing the location of the Number column.](https://doc.toasttab.com/doc/media/menus-bulk-import-prep-station-ids.png)

If you don't provide a prep station ID when you create a menu item or modifier, the menu item or modifier inherits the prep station assigned to its parent menu entity. The same is true for sales categories and tax rates.

### Identifiers for location groups and individual locations

To see identifiers for locations and location groups (formerly called *restaurant groups*), Toast support must enable the multi-location management product module for your restaurant locations. When this module is enabled, the Toast account \> Business and location management \> Location groups (Restaurant groups) page becomes available in Toast Web. You can retrieve a location or a location group's identifier from this page, using the instructions below.

**Procedure 8.141. To retrieve a location group's identifier**

1. [Access Toast Web ](adminAccessToastAdminBackend.html).


2. Choose Toast account \> Business and location management \> Location groups (Restaurant groups). The Location groups (Restaurant groups) page opens.


3. On the Groups tab, search for or navigate to the location group that you need an identifier for. Its name should be listed at the top of the location group card.

![Example of navigating to a location group](https://doc.toasttab.com/doc/media/menus-bulk-import-selected-location-group.png)


4. Select Edit info. The Edit Custom Group window opens. The Group ID field contains the Toast `GUID` for the location group. This is the identifier that the bulk menu import tool uses.


5. Select Copy next to the Group ID field to copy the ID and paste it in your bulk import spreadsheet.

![Location of the Copy button for the Group ID](https://doc.toasttab.com/doc/media/menus-bulk-import-location-group-guid.png)



**Procedure 8.142. To retrieve a single location's identifier**

1. [Access Toast Web ](adminAccessToastAdminBackend.html).


2. Choose Toast account \> Business and location management \> Location groups (Restaurant groups). The Location groups (Restaurant groups) page opens.


3. Select the Locations tab.


4. Search for or scroll to the location you need an identifier for and then select the arrow at the end of its row.

![Example of the arrow at the end of a location row](https://doc.toasttab.com/doc/media/menus-bulk-import-location-arrow-for-guid.png)

The location's page opens and the URL in the browser's address bar is updated with the location's GUID at the end of URL, after `/locations`. You can copy the GUID and paste it in your bulk menu import spreadsheet.

![Example of a location's GUID in the browser's address bar](https://doc.toasttab.com/doc/media/menus-bulk-import-location-guid.png)



