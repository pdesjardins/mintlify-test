---
title: "Restaurant information"
id: apiAnalyticsRestaurantInfoOmitChunkFromSearchIndex
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiAnalyticsOmitChunkFromSearchIndex.md
parentSectionTitle: "Chapter 11. Analytics"
previousSectionFile: apiDevGuide-apiAnalyticsGuestDataUnderstandData.md
previousSectionTitle: "Understanding the guest reporting data"
nextSectionFile: apiDevGuide-apiAnalyticsRestaurantInfoGetRestaurantList.md
nextSectionTitle: "Getting a list of restaurants in a management group"
keywords: [restaurant,information]
procedures: 0
codeExamples: 0
---

### Restaurant information overview

The restaurant information data includes the restaurant GUID, restaurant name, active status, test mode status, and archive status for every restaurant in a management group.

Send a `GET`request to the `/era/v1/restaurants-information`endpoint to retrieve the `restaurantGUID`, `restaurantName`, `active`, `testMode`, and `archived`values for each restaurant in a management group.

