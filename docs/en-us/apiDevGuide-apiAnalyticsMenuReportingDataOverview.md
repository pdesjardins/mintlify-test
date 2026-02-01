---
title: "Menu reporting data overview"
id: apiAnalyticsMenuReportingDataOverview
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiAnalyticsMenuReportingDataOmitChunkFromSearchIndex.md
parentSectionTitle: "Menu reporting data"
previousSectionFile: apiDevGuide-apiAnalyticsMenuReportingDataOmitChunkFromSearchIndex.md
previousSectionTitle: "Menu reporting data"
nextSectionFile: apiDevGuide-apiAnalyticsMenuReportingDataCreateRequest.md
nextSectionTitle: "Creating a request for menu reporting data"
excerpt: "Menu..."
keywords: [menu,reporting,data,overview,/era/v1/menu/{timeRange},reportRequestGuid,/era/v1/menu/{requestReportGuid}]
procedures: 0
codeExamples: 0
---

### Menu reporting data overview

Menu reporting data includes detailed information about menu entities as they relate to sales. For example, the gross and net sales of the Croissant menu item and the number sold at a restaurant on a specified day. For more information about what is included in the menu reporting data, see [Understanding the menu reporting data](apiAnalyticsMenuReportingDataUnderstandingData.html). For more information about inactive restaurant data, see [Viewing inactive restaurant data](apiAnalyticsInactiveRestaurantData.html).

Retrieving the menu reporting data is a two-step process. You must:

1. Send a `POST` request to the `/era/v1/menu` or `/era/v1/menu/\{timeRange\}`endpoint to create a request for menu reporting data for the restaurants in a management group. The response includes the `reportRequestGuid`, the unique request identifier. These endpoints are for either a custom time range (`/era/v1/menu`), which can include a time range for any number or days, or a specific time range (`/era/v1/menu/\{timeRange\}`), which allows for a maximum number of days depending on the specific time range value chosen. For more information, see [Creating a request for menu reporting data](apiAnalyticsMenuReportingDataCreateRequest.html).


2. Send a `GET` request to the `/era/v1/menu/\{requestReportGuid\}` endpoint to retrieve the menu reporting data. For more information, see [Retrieving the menu reporting data](apiAnalyticsMenuReportingDataRetrieveData.html).





> **Note**
> 
> The `reportRequestGuid` expires seven days after you create it. Using an expired or invalid `reportRequestGuid`results in a 404 error. The `message` of the response body contains additional information about the cause of the error.


