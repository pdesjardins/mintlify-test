---
title: "Restaurant information overview"
id: apiAnalyticsRestaurantInfoOverview
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiAnalyticsRestaurantInfoOmitChunkFromSearchIndex.md
parentSectionTitle: "Restaurant information"
previousSectionFile: apiDevGuide-apiAnalyticsRestaurantInfoOmitChunkFromSearchIndex.md
previousSectionTitle: "Restaurant information"
nextSectionFile: apiDevGuide-apiAnalyticsRestaurantInfoGetRestaurantList.md
nextSectionTitle: "Getting a list of restaurants in a management group"
excerpt: "The restaurant information data includes the restaurant GUID, restaurant name, active status, test mode status, and archive status for every restaurant in a management group."
keywords: ["restaurant", "information", "overview", "restaurantGUID", "restaurantName", "testMode"]
procedures: 0
codeExamples: 0
---

The restaurant information data includes the restaurant GUID, restaurant name, active status, test mode status, and archive status for every restaurant in a management group.

Send a `GET` request to the `/era/v1/restaurants-information` endpoint to retrieve the `restaurantGUID`, `restaurantName`, `active`, `testMode`, and `archived`values for each restaurant in a management group.

