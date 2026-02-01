---
title: "Menus API structure mirrors Toast Web structure"
id: apiMenusApiStructureMirrorsToastAdministrationBackEndStructure
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiAboutTheMenusApiOmitChunkFromSearchIndex.md
parentSectionTitle: "About the menus API"
previousSectionFile: apiDevGuide-apiComparingMenusAPIV2AndV3.md
previousSectionTitle: "Comparing menus API V2 and V3"
nextSectionFile: apiDevGuide-apiUsingMenusApiDataToConstructValidOrders.md
nextSectionTitle: "Using menus API data to construct valid orders"
excerpt: "The..."
keywords: [menus,structure,mirrors,toast]
procedures: 0
codeExamples: 0
---

### Menus API structure mirrors Toast Web structure

The menus API returns JSON that reflects the structure that a Toast customer has defined for their restaurant's menus in Toast Web. This is also the structure that the Toast platform uses to display menus on Toast devices. For example, if a restaurant's Breakfast menu is configured to appear on a Toast POS device before a Lunch menu, then the JSON returned by the menus API will include the Breakfast menu data before the Lunch menu data. To use the menus API effectively, it is important to understand the Toast menu structure and rules described in [Menu hierarchy](adminMenuHierarchy.html).

