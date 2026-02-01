---
title: "Aggregated sales reporting data overview"
id: apiAnalyticsMetricsReportingDataOverview
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiAnalyticsMetricsReportingDataOmitChunkFromSearchIndex.md
parentSectionTitle: "Aggregated sales reporting data"
previousSectionFile: apiDevGuide-apiAnalyticsMetricsReportingDataOmitChunkFromSearchIndex.md
previousSectionTitle: "Aggregated sales reporting data"
nextSectionFile: apiDevGuide-apiAnalyticsMetricsReportingDataCreateRequest.md
nextSectionTitle: "Creating a request for aggregated sales reporting data"
excerpt: "Aggregated sales reporting data includes a high-level view of active restaurant metrics based on orders, including sales and labor information. For more information on what is included in the..."
keywords: [aggregated,sales,reporting,data,overview,/era/v1/metrics/{timeRange},reportRequestGuid,/era/v1/metrics/{reportRequestGuid}]
procedures: 0
codeExamples: 0
---

### Aggregated sales reporting data overview

Aggregated sales reporting data includes a high-level view of active restaurant metrics based on orders, including sales and labor information. For more information on what is included in the aggregated sales reporting data, see [Understanding aggregated sales reporting data](apiAnalyticsMetricsReportingDataUnderstandingData.html). For more information about inactive restaurant data, see [Viewing inactive restaurant data](apiAnalyticsInactiveRestaurantData.html).

Retrieving the aggregated sales reporting data is a two-step process. You must:

1. Send a `POST` request to the `/era/v1/metrics` or `/era/v1/metrics/\{timeRange\}` endpoint to create a request for aggregated sales reporting data for the restaurants in a management group and receive the `reportRequestGuid`, the unique request identifier. These endpoints are for either a custom time range (`/era/v1/metrics`) or a specific time range (`/era/v1/metrics/\{timeRange\}`). For more information, see [Creating a request for aggregated sales reporting data](apiAnalyticsMetricsReportingDataCreateRequest.html).


2. Send a `GET` request to the `/era/v1/metrics/\{reportRequestGuid\}` endpoint to retrieve the aggregated sales reporting data. For more information, see [Retrieving the aggregated sales reporting data](apiAnalyticsMetricsReportingDataRetrieveData.html).





> **Note**
> 
> The `reportRequestGuid` expires seven days after you create it. Using an expired or invalid `reportRequestGuid`results in a 404 error. The `message` of the response body contains additional information about the cause of the error.


