---
title: "Retrieving the aggregated sales reporting data"
id: apiAnalyticsMetricsReportingDataRetrieveData
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiAnalyticsMetricsReportingDataOmitChunkFromSearchIndex.md
parentSectionTitle: "Aggregated sales reporting data"
previousSectionFile: apiDevGuide-apiAnalyticsMetricsReportingDataCreateRequest.md
previousSectionTitle: "Creating a request for aggregated sales reporting data"
nextSectionFile: apiDevGuide-apiAnalyticsMetricsReportingDataAggregation.md
nextSectionTitle: "Aggregating the aggregated sales reporting data"
excerpt: "Send..."
keywords: ["retrieving", "aggregated", "sales", "reporting", "data", "/era/v1/metrics/{reportRequestGuid}", "fetchRestaurantNames", "fetchRestaurantName"]
procedures: 0
codeExamples: 0
---

Send a `GET` request to the `/era/v1/metrics/{reportRequestGuid}` endpoint to retrieve aggregated sales reporting data. The rate limit for this endpoint and method type is five requests per second and 30 requests per minute. For more information about API rate limits for the analytics API, see [Analytics API rate limits](apiDevGuide-apiAnalyticsRateLimiting).

Optionally, you can choose to include a `fetchRestaurantNames` query parameter. The `fetchRestaurantNames` query parameter set to `true` adds the restaurant name to the aggregated sales reporting data. If set to `false`, it does not add the restaurant name, which acts the same as not including the `fetchRestaurantName` query parameter.

## Request to retrieve aggregated sales reporting data

The following example **curl** command sends a `GET` request to `/era/v1/metrics/{reportRequestGuid}` endpoint.


```
curl -X GET \ 'https://`[toast-api-hostname]`/era/v1/metrics/
fb23cfaa-56d7-4cb9-829d-531a8d02274a/' \
  -H 'Authorization: Bearer `[token]`'

```



(1) Send a GET request to the /era/v1/metrics endpoint of the analytics API.

(2) Include the GUID for the aggregated sales reporting data request, also called the reportRequestGuid. For more information about how to retrieve data using the analytics API, see Understanding the analytics API process.

(3) Include an authentication token. For more information, see Authentication and restaurant access.

## Response to the retrieval request for aggregated sales reporting data

The following example shows the response from the `/era/v1/metrics/{reportRequestGuid}` endpoint.


```
[
    {
        "restaurantGuid": "b6bae410-1316-4d3b-b01f-47a758811db2",
        "businessDate": "20220824",
        "guestCount": 64,
        "voidOrdersCount": 0,
        "discountOrderCount": 12,
        "ordersCount": 64,
        "openOrdersCount": 0,
        "closedOrdersCount": 64,
        "netSalesAmount": 975.75,
        "grossSalesAmount": 1162.5,
        "discountAmount": 186.75,
        "voidOrdersAmount": 0.0,
        "refundAmount": 0.0,
        "avgOrderValue": 15.25,
        "revenueCenter": "Dining Room"
    },
    {
        "restaurantGuid": "b6bae410-1316-4d3b-b01f-47a758811db2",
        "businessDate": "20220825",
        "guestCount": 39,
        "voidOrdersCount": 2,
        "discountOrderCount": 12,
        "ordersCount": 39,
        "openOrdersCount": 0,
        "closedOrdersCount": 39,
        "netSalesAmount": 507.25,
        "grossSalesAmount": 695.5,
        "discountAmount": 188.25,
        "voidOrdersAmount": 16.0,
        "refundAmount": 0.0,
        "avgOrderValue": 13.01,
        "revenueCenter": "Dining Room"
    },
    [content omitted]
    {
        "restaurantGuid": "b6bae410-1316-4d3b-b01f-47a758811db2",
        "businessDate": "20220824",
        "guestCount": 974,
        "voidOrdersCount": 9,
        "discountOrderCount": 15,
        "ordersCount": 974,
        "openOrdersCount": 0,
        "closedOrdersCount": 974,
        "netSalesAmount": 14939.25,
        "grossSalesAmount": 15063.25,
        "discountAmount": 124.0,
        "voidOrdersAmount": 93.5,
        "refundAmount": 0.0,
        "avgOrderValue": 15.34,
        "revenueCenter": "No Revenue Center"
    },
    {
        "restaurantGuid": "b6bae410-1316-4d3b-b01f-47a758811db2",
        "businessDate": "20220825",
        "guestCount": 945,
        "voidOrdersCount": 2,
        "discountOrderCount": 8,
        "ordersCount": 945,
        "openOrdersCount": 0,
        "closedOrdersCount": 945,
        "netSalesAmount": 14499.1,
        "grossSalesAmount": 14573.1,
        "discountAmount": 74.0,
        "voidOrdersAmount": 23.75,
        "refundAmount": 0.0,
        "avgOrderValue": 15.34,
        "revenueCenter": "No Revenue Center"
    },
    [content omitted]
]

```

For more information about the values in the response, see [Understanding aggregated sales reporting data](apiDevGuide-apiAnalyticsMetricsReportingDataUnderstandingData).

