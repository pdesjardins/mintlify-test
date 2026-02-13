---
title: "Creating a request for check reporting data"
id: apiAnalyticsCheckReportingDataCreateRequest
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiAnalyticsCheckReportingDataOmitChunkFromSearchIndex.md
parentSectionTitle: "Check reporting data"
previousSectionFile: apiDevGuide-apiAnalyticsCheckReportingDataOverview.md
previousSectionTitle: "Check reporting data overview"
nextSectionFile: apiDevGuide-apiAnalyticsCheckReportingDataRetrieveData.md
nextSectionTitle: "Retrieving the check reporting data"
excerpt: "Send a POST request to the /era/v1/check/day endpoint to request check reporting data for a single day. The rate limit for this endpoint and method type is five requests..."
keywords: ["creating", "request", "check", "reporting", "data", "onlyInactiveRestaurants", "restaurantIds", "excludedRestaurantIds", "startBusinessDate", "endBusinessDate"]
procedures: 0
codeExamples: 0
---

Send a `POST` request to the `/era/v1/check/day` endpoint to request check reporting data for a single day. The rate limit for this endpoint and method type is five requests per minute and 60 requests per day. For more information about API rate limits for the analytics API, see [Analytics API rate limits](apiDevGuide-apiAnalyticsRateLimiting). 

You can optionally include only the data from currently inactive restaurants using `onlyInactiveRestaurants` as a query parameter. For more information, see [Viewing inactive restaurant data](apiDevGuide-apiAnalyticsInactiveRestaurantData).

To create a request for check data, include the following:

- The `restaurantIds` value in the message body. This identifies the only restaurants to include in the returned data using the restaurant GUID. All restaurants not listed are excluded from the returned data. This value can be left empty to include all restaurants.


- The `excludedRestaurantIds` value in the message body. This identifies the restaurants to exclude from the returned data using the restaurant GUID. All restaurants not listed are included in the returned data. This value can be left empty to include all restaurants.



> **Important**
> 
> You can only include restaurant GUIDs for either `restaurantIds` or `excludedRestaurantIds`. Listing restaurant GUIDs for both results in a 400 error or blank data.



- The `startBusinessDate` value in the message body. This identifies the start date for the return data. This value must match the `endBusinessDate` value.


- The `endBusinessDate` value in the message body. This identifies the end date for the return data. This value must match the `startBusinessDate` value.





> **Note**
> 
> The date used to determine whether a check is within the time range or not is the date the order was initially expected to be fulfilled.


## Request for check reporting data

The following example **curl** command sends a `POST` request to the `/era/v1/check/day` endpoint.

```
curl -i -X POST \ 'https://`[toast-api-hostname]`/check/day' \
  -H 'Authorization: Bearer `[token]`' \
  -H 'Content-Type: application/json' \
  -d @`[request-info]`.json \
```



(1) Send a POST request to the /era/v1/check/day endpoint of the analytics API.

(2) Include an authentication token. For more information, see Authentication and restaurant access.

(3) Set the data type of the message body to application/json.

(4) Include details about the requested check reporting data in the message body. The following example is the message body for this curl command example.

## Message body for check reporting data

The following example shows the message body for creating a check reporting data request.

```
{
  "startBusinessDate": "20230201",
  "endBusinessDate": "20230201",
  "restaurantIds": [
    "95a96d7b-dbf5-46d3-98c5-c65c8ad18021"
  ],
  "excludedRestaurantIds": []
}

```



(1) The start date of the time range for the check reporting data, in YYYYMMDD format.

(2) The end date of the time range for the check reporting data, in YYYYMMDD format. This is the same value as the start date.

(3) The list of restaurant GUIDs from the management group to include in the check reporting data. Restaurant GUIDs not listed are excluded.

(4) The list of restaurant GUIDs from the management group to exclude from the check reporting data. In this example, restaurants are included with the restaurantIdsvalue, so all other restaurants are excluded automatically.

## Response to request for check reporting data

The following example shows the response from the `/era/v1/check/day` endpoint.

```
"83c93717-02ba-4b7c-9891-dfe090274d2d"
```



(1) The GUID for the check reporting data request, also called the reportRequestGuid. For more information about the analytics API process, see Understanding the analytics API process.

For an example that shows how to retrieve the check reporting data, see [Retrieving the check reporting data](apiDevGuide-apiAnalyticsCheckReportingDataRetrieveData).

