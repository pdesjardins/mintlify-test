---
title: "Menus API returns published data only"
id: apiMenusApiReturnsPublishedDataOnly
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiAboutTheMenusApiOmitChunkFromSearchIndex.md
parentSectionTitle: "About the menus API"
previousSectionFile: apiDevGuide-apiMenusApiSupportsDataRetrievalOnly.md
previousSectionTitle: "Menus API supports data retrieval only"
nextSectionFile: apiDevGuide-apiEnsuringYourMenuDataIsUpToDate.md
nextSectionTitle: "Ensuring your menu data is up-to-date"
excerpt: "To conserve the use of system resources, the menus API service only generates the JSON that it returns when a menu-related change has been made and published. This means that:"
keywords: ["menus", "returns", "published", "data", "only"]
procedures: 0
codeExamples: 0
---

### Menus API returns published data only

To conserve the use of system resources, the menus API service only generates the JSON that it returns when a menu-related change has been made and published. This means that:

- The menus API returns published data only.


- The menus API does not return data for archived menu entities.


- If changes have been made to a restaurant's menu configuration in Toast Web, the Toast customer must publish those changes before the menus API can return them.



There is a period of time after a menu has been published during which the Toast platform publishes the new data and then creates the menu JSON file that the menus API returns in response to requests made to the `/menus` endpoint. The length of this time period depends on the size and complexity of the restaurant's menu. You must wait for this process to complete before the newly published data will be returned by the menus API.

