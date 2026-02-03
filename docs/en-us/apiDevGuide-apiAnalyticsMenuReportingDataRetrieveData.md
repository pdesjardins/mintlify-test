---
title: "Retrieving the menu reporting data"
id: apiAnalyticsMenuReportingDataRetrieveData
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiAnalyticsMenuReportingDataOmitChunkFromSearchIndex.md
parentSectionTitle: "Menu reporting data"
previousSectionFile: apiDevGuide-apiAnalyticsMenuReportingDataCreateRequest.md
previousSectionTitle: "Creating a request for menu reporting data"
nextSectionFile: apiDevGuide-apiAnalyticsMenuReportingDataAggregation.md
nextSectionTitle: "Aggregating the menu reporting data"
excerpt: "Send a GET request to the /era/v1/menu/{reportRequestGuid} endpoint to retrieve menu reporting data. The rate limit for this endpoint and method type is five requests per second and 30 requests per..."
keywords: ["retrieving", "menu", "reporting", "data", "/era/v1/menu/{reportRequestGuid}"]
procedures: 0
codeExamples: 0
---

Send a `GET` request to the `/era/v1/menu/\{reportRequestGuid\}` endpoint to retrieve menu reporting data. The rate limit for this endpoint and method type is five requests per second and 30 requests per minute. For more information about API rate limits for the analytics API, see [Analytics API rate limits](apiAnalyticsRateLimiting.html).

#### Request to retrieve menu reporting data

The following example **curl** command sends a `GET` request to `/era/v1/menu/\{reportRequestGuid\}` endpoint.

```
curl -X GET \ 'https://[toast-api-hostname]/era/v1/menu/
fb23cfaa-56d7-4cb9-829d-531a8d02274a/' \
  -H 'Authorization: Bearer [token]'
```



(1) Send a GET request to the /era/v1/menu endpoint of the analytics API.

(2) Include the GUID for the menu reporting data request, also called the reportRequestGuid. For more information about how to retrieve data using the analytics API, see Understanding the analytics API process.

(3) Include an authentication token. For more information, see Authentication and restaurant access.

#### Response to the retrieval request for menu reporting data

The following example shows the response from the `/era/v1/menu/\{reportRequestGuid\}` endpoint.

```
[
   \{
       "restaurantGuid": "95a96d7b-dbf5-46d3-98c5-c65c8ad18021",
       "restaurantName": "Grove Place Cafe",
       "restaurantLocationName": null,
       "restaurantLocationCode": "",
       "businessDate": "20220901",
       "netSalesAmount": 24.5,
       "grossSalesAmount": 24.5,
       "discountAmount": 0.0,
       "refundAmount": 0.0,
       "voidAmount": 0.0,
       "quantitySold": 7.0,
       "averagePrice": 3.5,
       "wasteCount": 0.0,
       "wasteAmount": 0.0,
       "modifierGuid": "025d8278-edc3-409a-a16e-c082ccd9e5a5",
       "modifierName": "Soup de Jour"
   },
   \{
       "restaurantGuid": "95a96d7b-dbf5-46d3-98c5-c65c8ad18021",
       "restaurantName": "Grove Place Cafe",
       "restaurantLocationName": null,
       "restaurantLocationCode": "",
       "businessDate": "20220901",
       "netSalesAmount": 0.0,
       "grossSalesAmount": 0.0,
       "discountAmount": 0.0,
       "refundAmount": 0.0,
       "voidAmount": 0.0,
       "quantitySold": 5.0,
       "averagePrice": 0.0,
       "wasteCount": 0.0,
       "wasteAmount": 0.0,
       "modifierGuid": "d1a45259-de30-48fc-950b-7ff2b3a31c75",
       "modifierName": "Chocolate Chip"
   },
   \{
       "restaurantGuid": "95a96d7b-dbf5-46d3-98c5-c65c8ad18021",
       "restaurantName": "Grove Place Cafe",
       "restaurantLocationName": null,
       "restaurantLocationCode": "",
       "businessDate": "20220901",
       "netSalesAmount": 0.0,
       "grossSalesAmount": 0.0,
       "discountAmount": 0.0,
       "refundAmount": 0.0,
       "voidAmount": 0.0,
       "quantitySold": 1.0,
       "averagePrice": 0.0,
       "wasteCount": 0.0,
       "wasteAmount": 0.0,
       "modifierGuid": "ab57a7ca-b6b4-435f-be49-e86ba8215253",
       "modifierName": "Decaf"
   },
   \{
       "restaurantGuid": "95a96d7b-dbf5-46d3-98c5-c65c8ad18021",
       "restaurantName": "Grove Place Cafe",
       "restaurantLocationName": null,
       "restaurantLocationCode": "",
       "businessDate": "20220901",
       "netSalesAmount": 0.0,
       "grossSalesAmount": 0.0,
       "discountAmount": 0.0,
       "refundAmount": 0.0,
       "voidAmount": 0.0,
       "quantitySold": 7.0,
       "averagePrice": 0.0,
       "wasteCount": 0.0,
       "wasteAmount": 0.0,
       "modifierGuid": "4640fd82-e973-40b3-98fb-d1b57d035aa5",
       "modifierName": "Vegetarian"
   },
   [content omitted]
   \{
       "restaurantGuid": "95a96d7b-dbf5-46d3-98c5-c65c8ad18021",
       "restaurantName": "Grove Place Cafe",
       "restaurantLocationName": null,
       "restaurantLocationCode": "",
       "businessDate": "20220901",
       "netSalesAmount": 0.0,
       "grossSalesAmount": 0.0,
       "discountAmount": 0.0,
       "refundAmount": 0.0,
       "voidAmount": 0.0,
       "quantitySold": 2.0,
       "averagePrice": 0.0,
       "wasteCount": 0.0,
       "wasteAmount": 0.0,
       "modifierGuid": "0580b349-d885-45bb-9097-197fe5f9eb40",
       "modifierName": "Blueberry"
   },
   \{
       "restaurantGuid": "95a96d7b-dbf5-46d3-98c5-c65c8ad18021",
       "restaurantName": "Grove Place Cafe",
       "restaurantLocationName": null,
       "restaurantLocationCode": "",
       "businessDate": "20220901",
       "netSalesAmount": 6.0,
       "grossSalesAmount": 6.0,
       "discountAmount": 0.0,
       "refundAmount": 0.0,
       "voidAmount": 0.0,
       "quantitySold": 2.0,
       "averagePrice": 3.0,
       "wasteCount": 0.0,
       "wasteAmount": 0.0,
       "modifierGuid": "3c0b4332-cd0e-4fd5-ae7f-30e1480c46b7",
       "modifierName": "Croissant"
   \},
   [content omitted]
]

```

For more information about the values in the response, see [Understanding the menu reporting data](apiAnalyticsMenuReportingDataUnderstandingData.html).

