---
title: "Check reporting data"
id: apiAnalyticsCheckReportingDataOmitChunkFromSearchIndex
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiAnalyticsOmitChunkFromSearchIndex.md
parentSectionTitle: "Chapter 11. Analytics"
previousSectionFile: apiDevGuide-apiAnalyticsMetricsReportingDataUnderstandingData.md
previousSectionTitle: "Understanding aggregated sales reporting data"
nextSectionFile: apiDevGuide-apiAnalyticsCheckReportingDataCreateRequest.md
nextSectionTitle: "Creating a request for check reporting data"
keywords: [check,reporting,data]
procedures: 0
codeExamples: 0
---

### Check reporting data overview

Check reporting data includes detailed check information for all orders created on a specific day. For more information on what is included in the check reporting data, see [Understanding the check reporting data](apiAnalyticsCheckReportingDataUnderstandingData.html). For more information about inactive restaurant data, see [Viewing inactive restaurant data](apiAnalyticsOmitChunkFromSearchIndex.html#apiAnalyticsInactiveRestaurantData).

Retrieving the check reporting data is a two-step process. You must:

1. Send a `POST`request to `/era/v1/check/{timeRange}`endpoint to create a request for check reporting data for the restaurants in a management group. The response is the `reportRequestGuid`, the unique request identifier. The analytics API currently only supports retrieving check reporting data for the `day`time range. For more information, see [Creating a request for check reporting data](apiAnalyticsCheckReportingDataCreateRequest.html).


2. Send a `GET`request to `/era/v1/check/{reportRequestGuid}`endpoint to retrieve the check reporting data. For more information, see [Retrieving the check reporting data](apiAnalyticsCheckReportingDataRetrieveData.html).





> **Note**
> 
> The `reportRequestGuid`expires seven days after you create it. Using an expired or invalid `reportRequestGuid`results in a 404 error. The `message`of the response body contains additional information about the cause of the error.


