---
title: "Creating a request for aggregated sales reporting data"
id: apiAnalyticsMetricsReportingDataCreateRequest
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiAnalyticsMetricsReportingDataOmitChunkFromSearchIndex.md
parentSectionTitle: "Aggregated sales reporting data"
previousSectionFile: apiDevGuide-apiAnalyticsMetricsReportingDataOverview.md
previousSectionTitle: "Aggregated sales reporting data overview"
nextSectionFile: apiDevGuide-apiAnalyticsMetricsReportingDataRetrieveData.md
nextSectionTitle: "Retrieving the aggregated sales reporting data"
excerpt: "There are two ways to create a request for aggregated sales reporting data:..."
keywords: [creating,request,aggregated,sales,reporting,data,startBusinessDate,endBusinessDate,YYYYMMDD,restaurantIds]
procedures: 0
codeExamples: 0
---

### Creating a request for aggregated sales reporting data

There are two ways to create a request for aggregated sales reporting data: you can request aggregated sales reporting data for a custom time range or a specific time range. The type of time range you use also determines the rate limit for this endpoint and method type. The rate limit for custom, `month`, and `year`time ranges is 10 requests per hour. The rate limit for `day`and `week` time ranges is 10 requests per minute and 60 requests per hour. For more information about API rate limits for the analytics API, see [Analytics API rate limits](apiAnalyticsRateLimiting.html).

You must include the `startBusinessDate` and `endBusinessDate` properties in the message body to identify the start and end dates of your time range, in `YYYYMMDD`format.



> **Note**
> 
> The `day` option for the specific time range aggregated sales reporting data request does not require the `endBusinessDate`.


Optionally, you can use the `restaurantIds` in the message body to list the GUIDs of specific restaurants from the management group that you want to include, or the `excludedRestaurantIds` in the message body to list the GUIDs of specific restaurants from the management group that you want to exclude. If you add restaurant GUIDs to the `restaurantIds`value, all restaurants not listed are excluded from the aggregated sales reporting data. If you add restaurant GUIDs to the `excludedRestaurantIds` value, all restaurants not listed are included in the aggregated sales reporting data.



> **Important**
> 
> You can include restaurant GUIDs for only one of these values. Listing restaurant GUIDs for both `restaurantIds` and `excludedRestaurantIds` results in a 400 error or blank aggregated sales reporting data. They are contradictory values that cannot be used together.


If you use the `day` time range, you can aggregate the aggregated sales reporting data hourly instead of the default of daily by using the `aggregateBy` query parameter set to `HOUR`. For more information, see [Using the `aggregateBy` query parameter](apiAnalyticsMetricsReportingDataAggregation.html#apiAnalyticsMetricsReportingDataAggregateBy).

You can optionally aggregate the aggregated sales reporting data into groups by either dining option, order source, revenue center, or a combination of two of these values, using the `groupBy` value in the message body. For more information about using `groupBy`, see [Using the `groupBy` value](apiAnalyticsMetricsReportingDataAggregation.html#apiAnalyticsMetricsReportingDataGroupBy).

Also, you can optionally include only data from currently inactive restaurants using `onlyInactiveRestaurants` as a query parameter. For more information, see [Viewing inactive restaurant data](apiAnalyticsInactiveRestaurantData.html).

#### Creating an aggregated sales reporting data request for a custom time range

Send a `POST` request to the `/era/v1/metrics` endpoint to request aggregated sales reporting data for a customized time range. A custom time range can cover the current date and earlier. For example, if the current date is January 1, 2025, you could choose a range of January 1, 2023 to January 1, 2025, but the end date could not be January 2, 2025.

To create a request for aggregated sales reporting data that covers a customized time range, you must include:

- The `startBusinessDate` value in the message body. This identifies the start date for the custom time range.


- The `endBusinessDate` value in the message body. This identifies the end date for the custom time range.



##### Request for a custom time range of aggregated sales reporting data

The following example **curl** command sends a `POST` request to the `/era/v1/metrics` endpoint.

```
curl -i -X POST \ 'https://`[toast-api-hostname]`/era/v1/metrics' \
  -H ‘Authorization: Bearer `[token]`‘ \
  -H 'Content-Type: application/json' \
  -d @`[request-info]`.json \

```



(1) Send a POST request to the /era/v1/metrics endpoint of the analytics API.

(2) Include an authentication token. For more information, see Authentication and restaurant access.

(3) Set the data type of the message body to application/json.

(4) Include details about the requested aggregated sales reporting data in the message body. The following example is the message body for this curl command example.

##### Message body for the custom time range aggregated sales reporting data request

The following example shows the message body for creating an aggregated sales reporting data request for a custom time range.

```
{
  "startBusinessDate": "20220824",
  "endBusinessDate": "20220903",
  "restaurantIds": [
    "95a96d7b-dbf5-46d3-98c5-c65c8ad18021"
  ],
  "excludedRestaurantIds": [],
  "groupBy": [
    "REVENUE_CENTER"
  ]
}

```



(1) The start date of the time range for the aggregated sales reporting data, in YYYYMMDD format.

(2) The end date of the time range for the aggregated sales reporting data, in YYYYMMDD format.

(3) The list of restaurant GUIDs from the management group to include in the aggregated sales reporting data. Restaurant GUIDs not listed are excluded.

(4) The list of restaurant GUIDs from the management group to exclude from the aggregated sales reporting data. In this example, restaurants are included with the restaurantIds value, so all other restaurants are excluded automatically.

(5) This request is for aggregated sales reporting data grouped by revenue center.

##### Response to the request for custom time range aggregated sales reporting data

The following example shows the response from the `/era/v1/metrics` endpoint.

```
"fb23cfaa-56d7-4cb9-829d-531a8d02274a"
```



(1) The GUID for the aggregated sales reporting data request, also called the reportRequestGuid. For more information about how to retrieve data using the analytics API, see Understanding the analytics API process.

For an example that shows how to retrieve the aggregated sales reporting data, see [Retrieving the aggregated sales reporting data](apiAnalyticsMetricsReportingDataRetrieveData.html).

#### Creating an aggregated sales reporting data request for a specific time range

Send a `POST` request to `/era/v1/metrics/{timeRange}` endpoint to request aggregated sales reporting data for a specific time range. The time range you specify can be a day, week, month, or year. Accordingly, the options for the `{timeRange}` path parameter are:

- `day`: This requests data for one day, with the date specified by `startBusinessDate` in the message body. Providing an `endBusinessDate` is optional. If you choose to include the `endBusinessDate`, it must be the same date as the `startBusinessDate`.


- `week`: This requests data for seven or fewer days, with the start date specified by `startBusinessDate` and the end date specified by `endBusinessDate` in the message body.


- `month`: This requests data for 31 or fewer days, with the start date specified by `startBusinessDate`and the end date specified by `endBusinessDate` in the message body.


- `year`: This requests data for 366 or fewer days, with the start date specified by `startBusinessDate`and the end date specified by `endBusinessDate` in the message body.



If you choose the `day` time range, you can choose to group the aggregated sales reporting data by hour instead of day. For more information about aggregating by hour, see [Using the `aggregateBy` query parameter](apiAnalyticsMetricsReportingDataAggregation.html#apiAnalyticsMetricsReportingDataAggregateBy). For an example of using the `aggregateBy` query parameter, see [Example using `aggregateBy` and `groupBy`](apiAnalyticsMetricsReportingDataAggregation.html#apiAnalyticsMetricsReportingDataAggregateByGroupByExample).



> **Note**
> 
> The number of days between, and including, the `startBusinessDate` and `endBusinessDate` must be equal to or less than the day limit for the specified time range.


##### Request for specific time range aggregated sales reporting data

The following example **curl** command sends a `POST` request to the `/era/v1/metrics/{timeRange}` endpoint. This example uses the `week` time range.

```
curl -i -X POST \ 'https://`[toast-api-hostname]`/era/v1/metrics/week' \
  -H 'Authorization: Bearer `[token]`' \
  -H 'Content-Type: application/json' \
  -d @`[request-info]`.json \

```



(1) Send a POST request to the /era/v1/metrics/{timeRange} endpoint of the analytics API. The {timeRange} in this example is week.

(2) Include an authentication token. For more information, see Authentication and restaurant access.

(3) Set the data type of the message body to application/json.

(4) Include details about the requested aggregated sales reporting data in the message body. The following example is the message body for this curl command example.

##### Message body for the specific time range aggregated sales reporting data request

The following example shows the message body for creating an aggregated sales reporting data request for a specific time range. This example is for the `week` time range.

```
{
  "startBusinessDate": "20230205",
  "endBusinessDate": "20230207",
  "restaurantIds": [
    "b6bae410-1316-4d3b-b01f-47a758811db2",
    "43211888-2860-46c7-a8c8-32ba462e1280"
  ],
  "excludedRestaurantIds": [],
  "groupBy": []
}

```



(1) The start date of the time range for the aggregated sales reporting data, in YYYYMMDD format.

(2) The end date of the time range for the aggregated sales reporting data, in YYYYMMDD format. The number of days in the time range must be seven or fewer because the request is for a week time range.

(3) The list of restaurant GUIDs from the management group to include in the aggregated sales reporting data. Restaurant GUIDs not listed are excluded.

(4) The list of restaurant GUIDs from the management group to exclude from the aggregated sales reporting data. In this example, restaurants are included with the restaurantIds value, so all other restaurants are excluded automatically.

(5) This request for aggregated sales reporting data is not grouped by dining option, order source, or revenue center.

##### Response to the request for specific time range aggregated sales reporting data

The following example shows the response from the `/era/v1/metrics/{timeRange}` endpoint.

```
"d3d1ebdb-5e46-46ea-9491-f091466c5f22"
```



(1) The GUID for the aggregated sales reporting data, or the reportRequestGuid. For more information about how to retrieve data using the analytics API, see Understanding the analytics API process.

For the example about how to retrieve the aggregated sales reporting data for this request, see [Retrieving the aggregated sales reporting data](apiAnalyticsMetricsReportingDataRetrieveData.html).

