---
title: "Advanced properties and price editor pages"
id: usingTheAdvancedPropertiesAndPriceEditorPages
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformMultiLocationOmitChunkFromSearchIndex.md
parentSectionTitle: "Chapter 5. Multiple restaurant locations"
previousSectionFile: adminGuide-filteringPagesForSpecificRestaurantGroupsAndLocations.md
previousSectionTitle: "Filtering pages"
nextSectionFile: adminGuide-publishingChangesForMultipleLocations.md
nextSectionTitle: "Publishing changes for multiple locations"
excerpt: "When you are editing menus for multiple locations, you should use the Advanced properties page as the starting point for your edits. This page provides better visibility into the multiple locations..."
procedures: 0
codeExamples: 0
---

When you are editing menus for multiple locations, you should use the Advanced properties page as the starting point for your edits. This page provides better visibility into the multiple locations and versions you are managing than the standard Menus page does. To access the Advanced properties page, log in to Toast Web and choose Menus > Bulk management > Advanced properties. Toast support recommends keeping the Advanced properties page open in another browser window so you can quickly return to it after editing a specific menu entity (note that you will need to refresh the Advanced propertiespage when you return to it to see your changes). Do not use the breadcrumbs you see at the top of a configuration entity's detail page to navigate back up the menu hierarchy. The breadcrumbs can lead you back to a menu entity that you were not previously editing and, as a result, you can unintentionally edit an entity that you did not mean to change.

To filter the restaurants you see on the Advanced properties page so that you only see the restaurants you want to work with, use the You are viewing menu (described in the [Filtering pages](filteringPagesForSpecificRestaurantGroupsAndLocations.html)section). Note that after you make your selections in the You are viewing menu and click Update, you will see menus for those selections *and their parents* on the page. As you select a menu to edit, be sure to look at the menu's target to ensure you are editing the correct version. If you are editing a menu whose target is a restaurant group, you are, by definition, editing the menu for multiple locations (that is, any locations that the restaurant group and its sub-groups contain). If you intend to edit a menu for a specific location, you should choose the version of the menu that is targeted at that location; if a location-specific version does not exist, you should create one and edit the location-specific version.

The Target and Owner columns you see on the Advanced properties page are read-only and cannot be used to set the target and owner of a menu. Setting the target and owner for a configuration entity must be done on the entity's details page. For information about targets and owners, see [Targets](targets.html) and [Owners and permissions](ownersAndPermissions.html), respectively.

The Advanced properties page also has a Show/Hide menu. You can use this menu to customize the columns in the table you see on the Advanced propertiespage, adding information you want to see and removing information you do not.

For editing prices for multiple locations, Toast recommends using the Price editor page. To access the Price editor page, log into Toast Web and choose Menus > Bulk management > Price editor.

