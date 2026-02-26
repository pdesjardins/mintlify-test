---
title: "Analytics API rate limits"
id: apiAnalyticsRateLimiting
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiAboutAnalyticsOmitChunkFromSearchIndex.md
parentSectionTitle: "About the analytics API"
previousSectionFile: apiDevGuide-apiAnalyticsScope.md
previousSectionTitle: "Required scope for the analytics API"
nextSectionFile: apiDevGuide-apiAnalyticsDataDiscrepancies.md
nextSectionTitle: "Understanding data discrepancies"
excerpt: "The rate limit used by..."
keywords: ["analytics", "rate", "limits", "/era/v1/metrics/{timeRange}", "{timeRange", "/era/v1/metrics/{reportRequestGuid}", "/era/v1/check/{timeRange}", "{timeRange}", "/era/v1/check/{reportRequestGuid}", "/era/v1/labor/{timeRange}"]
procedures: 0
codeExamples: 0
---

The rate limit used by an endpoint depends on the endpoint and its time range. The following table lists the endpoints of the analytics API, organized by endpoint, method type, and rate limit. Notes are included when applicable.



> **Note**
> 
> As a Toast API, the analytics API adheres to the global rate limits. For more information, see [Rate limiting](docs/en-us/apiDevGuide-apiRateLimiting).


| Method and endpoint | Rate limits | Notes | 
| --- | --- | --- |
| `POST``/era/v1/metrics` | 10 requests per hour | This endpoint uses a custom time range. | 
| `POST``/era/v1/metrics/{timeRange}` | If `{timeRange`&#125; is:- `month` or `year`: 10 requests per hour
- `day` or `week`: 10 requests per minute, 60 requests per hour

 |  | 
| `GET``/era/v1/metrics/{reportRequestGuid}` | 5 requests per second30 requests per minute |   | 
| `POST``/era/v1/check/{timeRange}` | 5 requests per minute60 requests per day | This endpoint uses `day` as the `{timeRange}`. | 
| `GET``/era/v1/check/{reportRequestGuid}` | 5 requests per second30 requests per minute |  | 
| `POST``/era/v1/labor/{timeRange}` | If `{timeRange`&#125; is:- `month`: 10 requests per hour
- `day` or `week`: 10 requests per minute, 60 requests per hour

 |  | 
| `GET``/era/v1/labor/{reportRequestGuid}` | 5 requests per second30 requests per minute |  | 
| `POST``/era/v1/menu` | 10 requests per hour | This endpoint uses a custom time range. | 
| `POST``/era/v1/menu/{timeRange}` | If `{timeRange`&#125; is:- `month` or `year`: 10 requests per hour
- `day` or `week`: 10 requests per minute, 60 requests per hour

 |  | 
| `GET``/era/v1/menu/{reportRequestGuid}` | 5 requests per second30 requests per minute |  | 
| `POST``/era/v1/payout/{timeRange}` | If `{timeRange`&#125; is:- `month`: 10 requests per hour
- `day` or `week`: 10 requests per minute and 60 requests per hour

 |  | 
| `GET``/era/v1/payout/{reportRequestGuid}` | 5 requests per second30 requests per minute |  | 
| `POST``/era/v1/payout/payments/{timeRange}` | 5 requests per minute60 requests per day | This endpoint uses `day` as the `{timeRange}`. | 
| `GET``/era/v1/payout/payments/{reportRequestGuid}` | 5 requests per second30 requests per minute |  | 
| `POST``/era/v1/payout/sales-date/{timeRange}` | If `{timeRange`&#125; is:- `month`: 10 requests per hour
- `day` or `week`: 10 requests per minute and 60 requests per hour

 |  | 
| `GET``/era/v1/payout/sales-date/{reportRequestGuid}` | 5 requests per second30 requests per minute |  | 
| `POST``/era/v1/guest/payments/{timeRange}` | 5 requests per second60 requests per minute | This endpoint uses `day` or `week` as the `{timeRange}`. | 
| `GET``/era/v1/guest/payments/{reportRequestGuid}` | 5 requests per second30 requests per minute |   | 
| `GET``/era/v1/restaurant-info` | 5 requests per second30 requests per minute |  | 

