---
title: "Creating a request for menu reporting data"
id: apiAnalyticsMenuReportingDataCreateRequest
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiAnalyticsMenuReportingDataOmitChunkFromSearchIndex.md
parentSectionTitle: "Menu reporting data"
previousSectionFile: apiDevGuide-apiAnalyticsMenuReportingDataOverview.md
previousSectionTitle: "Menu reporting data overview"
nextSectionFile: apiDevGuide-apiAnalyticsMenuReportingDataRetrieveData.md
nextSectionTitle: "Retrieving the menu reporting data"
excerpt: "There are two ways to create a request for menu reporting data: you can request menu reporting data for a custom time range or a specific time range. The type of time range you use determines the..."
keywords: [creating,request,menu,reporting,data,startBusinessDate,endBusinessDate,YYYYMMDD,restaurantIds,excludedRestaurantIds]
procedures: 0
codeExamples: 0
---

### Creating a request for menu reporting data

There are two ways to create a request for menu reporting data: you can request menu reporting data for a custom time range or a specific time range. The type of time range you use determines the rate limit for this endpoint and method type. The rate limit for custom, `month`, and `year` time ranges is 10 requests per hour. The rate limit for `day` and `week` time ranges is 10 requests per minute and 60 requests per hour. For more information about API rate limits for the analytics API, see [Analytics API rate limits](apiAnalyticsRateLimiting.html).

You must include the `startBusinessDate` and `endBusinessDate` properties in the message body to identify the start and end dates for the time range, in `YYYYMMDD`format. For the day time range, the dates must be the same.



> **Note**
> 
> The `day` option for the specific time range menu reporting data request does not require the `endBusinessDate`.


Optionally, you can use the `restaurantIds` in the message body to list the GUIDs of specific restaurants from the management group that you want to include, or the `excludedRestaurantIds` in the message body to list the GUIDs of specific restaurants from the management group that you want to exclude. If you add restaurant GUIDs to the `restaurantIds`value, all restaurants not listed are excluded from the menu reporting data. If you add restaurant GUIDs to the `excludedRestaurantIds` value, all restaurants not listed are included in the menu reporting data.



> **Important**
> 
> You can include restaurant GUIDs for only one of these values. Listing restaurant GUIDs for both `restaurantIds` and `excludedRestaurantIds` results in a 400 error or blank menu reporting data. They are contradictory values that cannot be used together.


You can optionally aggregate the menu reporting data into groups by menu, menu group, menu item, or modifier using the `groupBy` value in the message body. For more information about using `groupBy` with the menu reporting data endpoint, see [Aggregating the menu reporting data](apiAnalyticsMenuReportingDataAggregation.html).

Also, you can optionally include only data from currently inactive restaurants using `onlyInactiveRestaurants` as a query parameter. For more information, see [Viewing inactive restaurant data](apiAnalyticsInactiveRestaurantData.html).

#### Creating a menu reporting data request for a custom time range

Send a `POST` request to the `/era/v1/menu` endpoint to request menu reporting data for a customized time range. A custom time range can cover the current date and earlier. For example, if the current date is January 1, 2025, you could choose a range of January 1, 2023 to January 1, 2025, but the end date could not be January 2, 2025.

##### Request for a custom time range of menu reporting data

The following example **curl** command sends a `POST` request to the `/era/v1/menu` endpoint.

```
curl -i -X POST \ 'https://[toast-api-hostname]/era/v1/menu' \
  -H ‘Authorization: Bearer [token]‘ \
  -H 'Content-Type: application/json' \
  -d @[request-info].json \
```



(1) Send a POST request to the /era/v1/menu endpoint of the analytics API.

(2) Include an authentication token. For more information, see Authentication and restaurant access.

(3) Set the data type of the message body to application/json.

(4) Include details about the requested menu reporting data in the message body. The following example is the message body for this curl command example.

##### Message body for a custom time range of menu reporting data

The following example shows the message body for creating a menu reporting data request for a custom time range.

```
\{
  "startBusinessDate": "20220101",
  "endBusinessDate": "20230912",
  "restaurantIds": [
    "95a96d7b-dbf5-46d3-98c5-c65c8ad18021"
  ],
  "excludedRestaurantIds": [],
\}

```



(1) The start date of the time range for the menu reporting data, in YYYYMMDD format.

(2) The end date of the time range for the menu reporting data, in YYYYMMDD format.

(3) The list of restaurant GUIDs from the management group to include in the menu reporting data. Restaurant GUIDs not listed are excluded.

(4) The list of restaurant GUIDs from the management group to exclude from the menu reporting data. For this example, excludedRestaurantIds must be empty because a restaurant GUID is already included with the restaurantIds value.

##### Response to request for a custom time range of menu reporting data

The following example shows the response from the `/era/v1/menu` endpoint.

```
"fb23cfaa-56d7-4cb9-829d-531a8d02274a"
```



(1) The GUID for the menu reporting data request, also called the reportRequestGuid. For more information about how to retrieve data using the analytics API, see Understanding the analytics API process.

For an example about how to retrieve the menu reporting data, see [Retrieving the menu reporting data](apiAnalyticsMenuReportingDataRetrieveData.html).

#### Creating a menu reporting data request for a specific time range

Send a `POST` request to `/era/v1/menu/\{timeRange\}` endpoint to request menu reporting data for a specific time range. The time range you specify can be a day, week, month, or year, as represented by these options for the `\{timeRange\}` path parameter:

- `day`: This requests data for one day, with the date specified by `startBusinessDate` in the message body. Providing an `endBusinessDate` is optional. If you choose to include the `endBusinessDate`, it must be the same date as the `startBusinessDate`.


- `week`: This requests data for seven or fewer days, with the start date specified by `startBusinessDate` and the end date specified by `endBusinessDate` in the message body.


- `month`: This requests data for 31 or fewer days, with the start date specified by `startBusinessDate`and the end date specified by `endBusinessDate` in the message body.


- `year`: This requests data for 366 or fewer days, with the start date specified by `startBusinessDate`and the end date specified by `endBusinessDate` in the message body.





> **Note**
> 
> The number of days between, and including, the `startBusinessDate` and `endBusinessDate` must be equal to or less than the day limit for the specified time range.


##### Request for a specific time range of menu reporting data

The following example **curl** command sends a `POST` request to the `/era/v1/menu/\{timeRange\}` endpoint. This example uses the `day` time range.

```
curl -i -X POST \ 'https://[toast-api-hostname]/era/v1/menu/day' \
  -H ‘Authorization: Bearer [token]‘ \
  -H 'Content-Type: application/json' \
  -d @[request-info].json \
```



(1) Send a POST request to the /era/v1/menu/\{timeRange\} endpoint of the analytics API. The \{timeRange\} in this example is day.

(2) Include an authentication token. For more information, see Authentication and restaurant access.

(3) Set the data type of the message body to application/json.

(4) Include details about the requested menu reporting data in the message body. The following example is the message body for this curl command example.

##### Message body for a specific time range of menu reporting data

The following example shows the message body for creating a menu reporting data request for a specific time range. This example is for the `day` time range.

```
\{
  "startBusinessDate": "20220901",
  "endBusinessDate": "20220901",
  "restaurantIds": [
    "95a96d7b-dbf5-46d3-98c5-c65c8ad18021"
  ],
  "excludedRestaurantIds": [],
  "groupBy": ["MODIFIER"]
\}

```



(1) The start date of the time range for the menu reporting data, in YYYYMMDD format.

(2) The end date of the time range for the menu reporting data, in YYYYMMDD format.

(3) The list of restaurant GUIDs from the management group to include in the menu reporting data. Restaurant GUIDs not listed are excluded.

(4) The list of restaurant GUIDs from the management group to exclude from the menu reporting data. In this example, restaurants are included with the restaurantIdsvalue, so all other restaurants are excluded automatically.

(5) This request is for menu reporting data grouped by modifier.

##### Response to request for a specific time range of menu reporting data

The following example shows the response from the `/era/v1/menu/\{timeRange\}` endpoint.

```
"fb23cfaa-56d7-4cb9-829d-531a8d02274a"
```



(1) The GUID for the menu reporting data request, also called the reportRequestGuid. For more information about how to retrieve data using the analytics API, see Understanding the analytics API process.

For an example about how to retrieve the menu reporting data, see [Retrieving the menu reporting data](apiAnalyticsMenuReportingDataRetrieveData.html).

