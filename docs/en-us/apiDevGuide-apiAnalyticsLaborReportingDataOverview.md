---
title: "Labor reporting data overview"
id: apiAnalyticsLaborReportingDataOverview
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiAnalyticsLaborReportingDataOmitChunkFromSearchIndex.md
parentSectionTitle: "Labor reporting data"
previousSectionFile: apiDevGuide-apiAnalyticsLaborReportingDataOmitChunkFromSearchIndex.md
previousSectionTitle: "Labor reporting data"
nextSectionFile: apiDevGuide-apiAnalyticsLaborReportingDataCreateRequest.md
nextSectionTitle: "Creating a request for labor reporting data"
excerpt: "Labor reporting data includes detailed information..."
keywords: ["labor", "reporting", "data", "overview", "/era/v1/labor/{timeRange}", "reportRequestGuid", "/era/v1/labor/{reportRequestGuid}"]
procedures: 0
codeExamples: 0
---

Labor reporting data includes detailed information about employees and jobs that are paid hourly. For more information about what is included in the labor reporting data, see [Understanding the labor reporting data](apiDevGuide-apiAnalyticsLaborReportingDataUnderstandingData). For more information about inactive restaurant data, see [Viewing inactive restaurant data](apiDevGuide-apiAnalyticsInactiveRestaurantData).

Retrieving the labor reporting data is a two-step process. You must:

1. Send a `POST` request to the `/era/v1/labor/{timeRange}` endpoint to create a request for labor reporting data for the restaurants in a management group. The response is the `reportRequestGuid`, the unique request identifier. The analytics API supports retrieving labor reporting data for the `day`, `week`, and `month` time ranges. For more information, see [Creating a request for labor reporting data](apiDevGuide-apiAnalyticsLaborReportingDataCreateRequest).


2. Send a `GET` request to the `/era/v1/labor/{reportRequestGuid}` endpoint to retrieve the labor reporting data. For more information, see [Retrieving the aggregated sales reporting data](apiDevGuide-apiAnalyticsMetricsReportingDataRetrieveData).





> **Note**
> 
> The `reportRequestGuid` expires seven days after you create it. Using an expired or invalid `reportRequestGuid`results in a 404 error. The `message` of the response body contains additional information about the cause of the error.


