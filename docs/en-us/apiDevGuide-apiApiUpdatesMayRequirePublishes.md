---
title: "API updates may require publishes"
id: apiApiUpdatesMayRequirePublishes
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-generalToastApiInformationOmitChunkFromSearchIndex.md
parentSectionTitle: "General Toast API information"
previousSectionFile: apiDevGuide-apiHandlingDowntimes.md
previousSectionTitle: "Handling Toast API downtime"
nextSectionFile: apiDevGuide-apiDeprecatedApiFunctions.md
nextSectionTitle: "Deprecated API functions"
excerpt: "The Toast development team regularly makes updates to the Toast APIs that add to the data that the APIs return. For some of these API updates, the new data is not available for a restaurant until..."
procedures: 0
codeExamples: 0
---

### API updates may require publishes

The Toast development team regularly makes updates to the Toast APIs that add to the data that the APIs return. For some of these API updates, the new data is not available for a restaurant until after that restaurant has published from Toast Web.

The menus API has the additional requirement that the restaurant must make a *menu-related change* and then publish from the Toast Web. This publish makes the new menu data available via the menus API. Making a menu-related change forces the restaurant's menu data to be re-generated. Non-menu-related changes do not initiate this menu data refresh, hence the requirement that the restaurant makes a menu-related change before publishing.

The release note for an API update will inform you if a publish, or a menu-related change and publish, is required for the updated data to be available.

For information about how to publish configuration changes, see [Publishing updates to restaurant configuration](platformPublishingOverview.html).

