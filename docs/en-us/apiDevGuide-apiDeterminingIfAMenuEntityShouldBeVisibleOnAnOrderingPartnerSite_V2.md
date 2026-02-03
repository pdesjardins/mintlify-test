---
title: "Determining if a menu entity should be visible on a partner integration"
id: apiDeterminingIfAMenuEntityShouldBeVisibleOnAnOrderingPartnerSite_V2
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiGettingMenuInformationOmitChunkFromSearchIndex.md
parentSectionTitle: "Getting menu information"
previousSectionFile: apiDevGuide-apiDeterminingIfMenuItemsOrModifiersContainAlcohol.md
previousSectionTitle: "Determining if a menu item or modifier contains alcohol"
nextSectionFile: apiDevGuide-apiPosButtonColorHexCodesForLightAndDarkMode.md
nextSectionTitle: "POS button color hex codes for light and dark modes"
excerpt: "In Toast Web, there are channel visibility settings that restaurants use to control where a menu entity is visible and, by extension, available for ordering. For example, these settings control..."
keywords: ["determining", "menu", "entity", "visible", "partner", "integration", "POS", "KIOSK", "TOAST_ONLINE_ORDERING", "ORDERING_PARTNERS"]
procedures: 0
codeExamples: 0
---



> **Important**
> 
> This section applies to partners using menus API V2 only. For partners using menus API V3, menu entities are pre-filtered to exclude menu entities that should not be visible on their sites. For more information, see [Comparing menus API V2 and V3](apiComparingMenusAPIV2AndV3.html).


In Toast Web, there are channel visibility settings that restaurants use to control where a menu entity is visible and, by extension, available for ordering. For example, these settings control whether an entity can be ordered on the Toast POS app, on a Toast Kiosk, through a restaurant's Toast Online Ordering website, or through a restaurant's integration with another, third-party online ordering system.

The channel visibility settings reside on a menu entity's details page in Toast Web. The names of the settings are slightly different depending on whether the restaurant is using the [classic menu details pages or the newer menu builder tool](adminBasicMenuBuilderAndTheLegacyMenuDetailsPages.html) to edit the menu. The table below describes the behavior of the channel visibility settings and how they are represented in the `visibility`array that appears in the menus API for each menu entity:

| Classic menus setting | Menu builder setting | Menus API visibility array enum | Description | 
| --- | --- | --- | --- |
| In-store orders: POS | POS | `POS` | The menu entity is visible on a Toast POS device. | 
| In-store orders: Kiosk | Kiosk, Toast Order and Pay | `KIOSK` | The menu entity is visible on a Toast Kiosk. | 
| Online orders: Toast | Toast Online Ordering, Toast Takeout (Local by Toast) app | `TOAST_ONLINE_ORDERING` | The menu entity is visible on a restaurant's Toast online ordering site. | 
| Online orders: Ordering partners | Online ordering partners | `ORDERING_PARTNERS` | The restaurant wants the menu entity to be visible on all online ordering sites that they have allowed to integrate with their restaurant. | 

Partner integrations should inspect a menu entity's `visibility` array to determine whether an entity should be included in their integration or not.

