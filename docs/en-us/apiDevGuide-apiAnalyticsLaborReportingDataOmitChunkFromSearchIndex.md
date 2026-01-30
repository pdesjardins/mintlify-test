---
title: "Labor reporting data"
id: apiAnalyticsLaborReportingDataOmitChunkFromSearchIndex
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiAnalyticsOmitChunkFromSearchIndex.md
parentSectionTitle: "Chapter 11. Analytics"
previousSectionFile: apiDevGuide-apiAnalyticsCheckReportingDataUnderstandingData.md
previousSectionTitle: "Understanding the check reporting data"
nextSectionFile: apiDevGuide-apiAnalyticsLaborReportingDataCreateRequest.md
nextSectionTitle: "Creating a request for labor reporting data"
keywords: [labor,reporting,data]
procedures: 0
codeExamples: 0
---

### Labor reporting data overview

Labor reporting data includes detailed information about employees and jobs that are paid hourly. For more information about what is included in the labor reporting data, see [Understanding the labor reporting data](apiAnalyticsLaborReportingDataUnderstandingData.html). For more information about inactive restaurant data, see [Viewing inactive restaurant data](apiAnalyticsOmitChunkFromSearchIndex.html#apiAnalyticsInactiveRestaurantData).

Retrieving the labor reporting data is a two-step process. You must:

1. Send a `POST` request to the `/era/v1/labor/{timeRange}` endpoint to create a request for labor reporting data for the restaurants in a management group. The response is the `reportRequestGuid`, the unique request identifier. The analytics API supports retrieving labor reporting data for the `day`, `week`, and `month` time ranges. For more information, see [Creating a request for labor reporting data](apiAnalyticsLaborReportingDataCreateRequest.html).


2. Send a `GET` request to the `/era/v1/labor/{reportRequestGuid}` endpoint to retrieve the labor reporting data. For more information, see [Retrieving the aggregated sales reporting data](apiAnalyticsMetricsReportingDataRetrieveData.html).





> **Note**
> 
> The `reportRequestGuid` expires seven days after you create it. Using an expired or invalid `reportRequestGuid`results in a 404 error. The `message` of the response body contains additional information about the cause of the error.


