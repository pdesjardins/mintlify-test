---
title: "Creating a request for labor reporting data"
id: apiAnalyticsLaborReportingDataCreateRequest
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiAnalyticsLaborReportingDataOmitChunkFromSearchIndex.md
parentSectionTitle: "Labor reporting data"
previousSectionFile: apiDevGuide-apiAnalyticsLaborReportingDataOverview.md
previousSectionTitle: "Labor reporting data overview"
nextSectionFile: apiDevGuide-apiAnalyticsLaborReportingDataRetrieveData.md
nextSectionTitle: "Retrieving the labor reporting data"
excerpt: "You can request labor reporting data for a single day, week, or month. The type of time..."
keywords: [creating,request,labor,reporting,data,startBusinessDate,endBusinessDate,YYYYMMDD,restaurantIds,excludedRestaurantIds]
procedures: 0
codeExamples: 0
---

### Creating a request for labor reporting data

You can request labor reporting data for a single day, week, or month. The type of time range you use determines the rate limit for this endpoint and method type. The rate limit for a `month` time range is 10 requests per hour. The rate limit for `day` and `week` time ranges is 10 requests per minute and 60 requests per hour. For more information about API rate limits for the analytics API, see [Analytics API rate limits](apiAnalyticsRateLimiting.html).

You must include the `startBusinessDate` and `endBusinessDate` properties in the message body to identify the start and end dates for the time range, in `YYYYMMDD`format. For the `day` time range, the dates must be the same.

Optionally, you can use the `restaurantIds` in the message body to list the GUIDs of specific restaurants from the management group that you want to include, or the `excludedRestaurantIds` in the message body to list the GUIDs of specific restaurants from the management group that you want to exclude. If you add restaurant GUIDs to the `restaurantIds`value, all restaurants not listed are excluded from the labor reporting data. If you add restaurant GUIDs to the `excludedRestaurantIds` value, all restaurants not listed are included in the labor reporting data.



> **Important**
> 
> You can include restaurant GUIDs for only one of these values. Listing restaurant GUIDs for both `restaurantIds` and `excludedRestaurantIds` results in a 400 error or blank labor reporting data. They are contradictory values that cannot be used together.


You can optionally include only data from currently inactive restaurants using `onlyInactiveRestaurants` as a query parameter. For more information, see [Viewing inactive restaurant data](apiAnalyticsInactiveRestaurantData.html).

Send a `POST` request to the `/era/v1/labor/{timeRange}` endpoint to request labor reporting data for a specific time range. The time range you specify can be `day`, `week`, or `month`.

To create a request for labor data, you must include:

- The `restaurantIds` value in the message body. This identifies the only restaurants to include in the returned data using the restaurant GUID. All restaurants not listed are excluded from the returned data. This value can be left empty to include all restaurants.


- The `excludedRestaurantIds` value in the message body. This identifies the only restaurants to exclude in the returned data using the restaurant GUID. All restaurants not listed are included in the returned data. This value can be left empty to include all restaurants.



> **Important**
> 
> You can only include restaurant GUIDs for either `restaurantIds` or `excludedRestaurantIds`. Listing restaurant GUIDs for both results in a 400 error or blank data.



- The `startBusinessDate` value in the message body. This identifies the start date for the return data. This value must match the `endBusinessDate` value if using the `day` time range.


- The `endBusinessDate` value in the message body. This identifies the end date for the return data. This value must match the `startBusinessDate` value if using the `day` time range.



#### Request for labor reporting data

The following example **curl** command sends a `POST` request to the `/era/v1/labor/{timeRange}` endpoint. This example uses the `day` time range.

```
curl -i -X POST \ 'https://[toast-api-hostname]/labor/day' \
  -H 'Authorization: Bearer [token]' \
  -H 'Content-Type: application/json' \
  -d @[request-info].json \
```



(1) Send a POST request to the /era/v1/labor/{timeRange} endpoint of the analytics API. The {timeRange} in this example is day.

(2) Include an authentication token. For more information, see Authentication and restaurant access.

(3) Set the data type of the message body to application/json.

(4) Include details about the requested labor reporting data in the message body. The following example is the message body for this curl command example.

#### Message body for labor reporting data

The following example shows the message body for creating a labor reporting data request.

```
{
  "startBusinessDate": "20230205",
  "endBusinessDate": "20230205",
  "restaurantIds": [],
  "excludedRestaurantIds": [],
  "groupBy": [“JOB”]
}

```



(1) The start date of the time range for the labor reporting data, in YYYYMMDD format.

(2) The end date of the time range for the labor reporting data, in YYYYMMDD format. This is the same value as the start date.

(3) The list of restaurant GUIDs from the management group to include in the labor reporting data. Restaurant GUIDs not listed are excluded.

(4) The list of restaurant GUIDs from the management group to exclude from the labor reporting data. In this example, restaurants are included with the restaurantIdsvalue, so all other restaurants are excluded automatically.

(5) This request for labor reporting data is grouped by job.

#### Response to request for labor reporting data

The following example shows the response from the `/era/v1/labor/day` endpoint.

```
"707d9f10-e0fe-4e6d-af49-3123a78cd2b3"
```



(1) The GUID for the labor reporting data request, also called the reportRequestGuid. For more information about how to retrieve data using the analytics API, see Understanding the analytics API process.

For an example that shows how to retrieve the labor reporting data, see [Retrieving the labor reporting data](apiAnalyticsLaborReportingDataRetrieveData.html).

