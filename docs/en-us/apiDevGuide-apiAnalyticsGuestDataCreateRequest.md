---
title: "Creating a request for guest reporting data"
id: apiAnalyticsGuestDataCreateRequest
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiAnalyticsGuestDataOmitChunkFromSearchIndex.md
parentSectionTitle: "Guest reporting data"
previousSectionFile: apiDevGuide-apiAnalyticsGuestDataOverview.md
previousSectionTitle: "Guest reporting data overview"
nextSectionFile: apiDevGuide-apiAnalyticsGuestDataRetrieveData.md
nextSectionTitle: "Retrieving the guest reporting data"
excerpt: "Send..."
keywords: ["creating", "request", "guest", "reporting", "data", "/era/v1/guest/payments/{timeRange}", "onlyInactiveRestaurants", "startDate", "YYYYMMDD", "endDate"]
procedures: 0
codeExamples: 0
---

Send a `POST` request to the `/era/v1/guest/payments/{timeRange}` endpoint to request guest reporting data organized by payment for a specific time range of `day` or `week`. The rate limit for this endpoint and method type is five requests per minute and 60 requests per day. For more information about API rate limits for the analytics API, see [Analytics API rate limits](apiDevGuide-apiAnalyticsRateLimiting).

You can limit the reporting data to inactive restaurants only using the `onlyInactiveRestaurants` query parameter. For more information, see [Viewing inactive restaurant data](apiDevGuide-apiAnalyticsInactiveRestaurantData).

To create a request for guest reporting data organized by payment, include the following:

- The `startDate` value in the message body, in `YYYYMMDD` format. This identifies the start date for the range of guest payment dates. This value must match the `endDate` value if using the `day` time range.


- The `endDate` value in the message body, in `YYYYMMDD` format. This identifies the end date for the range of guest payment dates. This value must match the `startDate` value if using the `day` time range.


- The `restaurantIds` value in the message body. This identifies the restaurants to include in the returned data using the restaurant GUID. All restaurants not listed are excluded from the returned data. Leave the `restaurantIds` value and the `excludedRestaurantIds` value empty to include all restaurants.


- The `excludedRestaurantIds` value in the message body. This identifies the restaurants to exclude in the returned data using the restaurant GUID. All restaurants not listed are included in the returned data. Leave the `excludedRestaurantIds` value and the `restaurantIds` value empty to include all restaurants.





> **Important**
> 
> You can include restaurant GUIDs for either `restaurantIds` or `excludedRestaurantIds` but not for both. Listing restaurant GUIDs for both results in a 400 error or blank guest reporting data. `restaurantIds` and `excludedRestaurantIds` are contradictory values that cannot be used together.


## Request for guest reporting data

The following example **curl** command sends a `POST` request to the `/era/v1/guest/payments/{timeRange}` endpoint. This example uses the `week` time range.


```
curl -i -X POST \ 'https://[toast-api-hostname]/era/v1/guest/payments/week' \
-H ‘Authorization: Bearer [token]‘ \
  -H 'Content-Type: application/json' \
  -d @[request-info].json \
```



    <tr>
      <td>[(1)](#co-d1e9261AAAFB51B-562D-4033-B77B-6C18243DEDD8)</td>
      <td>Send a `POST` request to the `/era/v1/guest/payments/{timeRange}` endpoint of the analytics API. The `{timeRange}` in this example is `week`.</td>
    </tr>
    <tr>
      <td>[(2)](#co-d1e9263AAAFB51B-562D-4033-B77B-6C18243DEDD8)</td>
      <td>Include an authentication token. For more information, see [Authentication and restaurant access](apiDevGuide-authentication).</td>
    </tr>
    <tr>
      <td>[(3)](#co-d1e9265AAAFB51B-562D-4033-B77B-6C18243DEDD8)</td>
      <td>Set the data type of the message body to `application/json`.</td>
    </tr>
    <tr>
      <td>[(4)](#co-d1e9267AAAFB51B-562D-4033-B77B-6C18243DEDD8)</td>
      <td>Include details about the requested guest reporting data in the message body. The following example is the message body for this **curl** command example.</td>
    </tr>
## Message body for guest reporting data

The following example shows the message body for creating a guest reporting data request for a specific time range. This example is for the `week` time range.


```
{
  "restaurantIds": [
    "95a96d7b-dbf5-46d3-98c5-c65c8ad18021",
    "6b853fa7-b3dc-4db7-a528-c3599823ccd1"
  ],
  "excludedRestaurantIds": [],
  "startDate": "20240924",
  "endDate": "20240926"
}

```



    <tr>
      <td>[(1)](#co-d1e9279AAAFB51B-562D-4033-B77B-6C18243DEDD8)</td>
      <td>The list of restaurant GUIDs from the management group to include in the guest reporting data. Restaurant GUIDs not listed are excluded.</td>
    </tr>
    <tr>
      <td>[(2)](#co-d1e9281AAAFB51B-562D-4033-B77B-6C18243DEDD8)</td>
      <td>The list of restaurant GUIDs from the management group to exclude from the guest reporting data. In this example, restaurants are included with the `restaurantIds` value, so all other restaurants are excluded automatically.</td>
    </tr>
    <tr>
      <td>[(3)](#co-d1e9283AAAFB51B-562D-4033-B77B-6C18243DEDD8)</td>
      <td>The start date of the time range for the guest reporting data, in `YYYYMMDD` format.</td>
    </tr>
    <tr>
      <td>[(4)](#co-d1e9285AAAFB51B-562D-4033-B77B-6C18243DEDD8)</td>
      <td>The end date of the time range for the guest reporting data, in `YYYYMMDD` format.</td>
    </tr>
## Response to request for guest reporting data

The following example shows the response from the `/era/v1/guest/payments/{timeRange}` endpoint.


```
"fb23cfaa-56d7-4cb9-829d-531a8d02274a"
```



    <tr>
      <td>[(1)](#co-d1e9298AAAFB51B-562D-4033-B77B-6C18243DEDD8)</td>
      <td>The GUID for the guest reporting data request, also called the `reportRequestGuid`. For more information about how to retrieve data using the analytics API, see [Understanding the analytics API process](apiDevGuide-apiAnalyticsUnderstandingProcess).</td>
    </tr>
For an example about how to retrieve the guest reporting data, see [Retrieving the guest reporting data](apiDevGuide-apiAnalyticsGuestDataRetrieveData).

