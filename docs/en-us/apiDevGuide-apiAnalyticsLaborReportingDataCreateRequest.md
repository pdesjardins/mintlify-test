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
keywords: ["creating", "request", "labor", "reporting", "data", "startBusinessDate", "endBusinessDate", "YYYYMMDD", "restaurantIds", "excludedRestaurantIds"]
procedures: 0
codeExamples: 0
---

You can request labor reporting data for a single day, week, or month. The type of time range you use determines the rate limit for this endpoint and method type. The rate limit for a `month` time range is 10 requests per hour. The rate limit for `day` and `week` time ranges is 10 requests per minute and 60 requests per hour. For more information about API rate limits for the analytics API, see [Analytics API rate limits](apiDevGuide-apiAnalyticsRateLimiting).

You must include the `startBusinessDate` and `endBusinessDate` properties in the message body to identify the start and end dates for the time range, in `YYYYMMDD`format. For the `day` time range, the dates must be the same.

Optionally, you can use the `restaurantIds` in the message body to list the GUIDs of specific restaurants from the management group that you want to include, or the `excludedRestaurantIds` in the message body to list the GUIDs of specific restaurants from the management group that you want to exclude. If you add restaurant GUIDs to the `restaurantIds`value, all restaurants not listed are excluded from the labor reporting data. If you add restaurant GUIDs to the `excludedRestaurantIds` value, all restaurants not listed are included in the labor reporting data.



> **Important**
> 
> You can include restaurant GUIDs for only one of these values. Listing restaurant GUIDs for both `restaurantIds` and `excludedRestaurantIds` results in a 400 error or blank labor reporting data. They are contradictory values that cannot be used together.


You can optionally include only data from currently inactive restaurants using `onlyInactiveRestaurants` as a query parameter. For more information, see [Viewing inactive restaurant data](apiDevGuide-apiAnalyticsInactiveRestaurantData).

Send a `POST` request to the `/era/v1/labor/&#123;timeRange&#125;` endpoint to request labor reporting data for a specific time range. The time range you specify can be `day`, `week`, or `month`.

To create a request for labor data, you must include:

- The `restaurantIds` value in the message body. This identifies the only restaurants to include in the returned data using the restaurant GUID. All restaurants not listed are excluded from the returned data. This value can be left empty to include all restaurants.


- The `excludedRestaurantIds` value in the message body. This identifies the only restaurants to exclude in the returned data using the restaurant GUID. All restaurants not listed are included in the returned data. This value can be left empty to include all restaurants.



> **Important**
> 
> You can only include restaurant GUIDs for either `restaurantIds` or `excludedRestaurantIds`. Listing restaurant GUIDs for both results in a 400 error or blank data.



- The `startBusinessDate` value in the message body. This identifies the start date for the return data. This value must match the `endBusinessDate` value if using the `day` time range.


- The `endBusinessDate` value in the message body. This identifies the end date for the return data. This value must match the `startBusinessDate` value if using the `day` time range.



## Request for labor reporting data

The following example **curl** command sends a `POST` request to the `/era/v1/labor/&#123;timeRange&#125;` endpoint. This example uses the `day` time range.


```
curl -i -X POST \ 'https://[toast-api-hostname]/labor/day' \
  -H 'Authorization: Bearer [token]' \
  -H 'Content-Type: application/json' \
  -d @[request-info].json \
```



    <tr>
      <td><a href="#co-d1e4384134B67F3-A975-4412-A030-B6DDC7E2BD35">(1)</a></td>
      <td>Send a <code>POST</code> request to the <code>/era/v1/labor/&#123;timeRange&#125;</code> endpoint of the analytics API. The <code>&#123;timeRange&#125;</code> in this example is <code>day</code>.</td>
    </tr>
    <tr>
      <td><a href="#co-d1e4386134B67F3-A975-4412-A030-B6DDC7E2BD35">(2)</a></td>
      <td>Include an authentication token. For more information, see <a href="apiDevGuide-authentication">Authentication and restaurant access</a>.</td>
    </tr>
    <tr>
      <td><a href="#co-d1e4388134B67F3-A975-4412-A030-B6DDC7E2BD35">(3)</a></td>
      <td>Set the data type of the message body to <code>application/json</code>.</td>
    </tr>
    <tr>
      <td><a href="#co-d1e4390134B67F3-A975-4412-A030-B6DDC7E2BD35">(4)</a></td>
      <td>Include details about the requested labor reporting data in the message body. The following example is the message body for this <strong>curl</strong>  command example.</td>
    </tr>
## Message body for labor reporting data

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



    <tr>
      <td><a href="#co-d1e4444134B67F3-A975-4412-A030-B6DDC7E2BD35">(1)</a></td>
      <td>The start date of the time range for the labor reporting data, in <code>YYYYMMDD</code> format.</td>
    </tr>
    <tr>
      <td><a href="#co-d1e4446134B67F3-A975-4412-A030-B6DDC7E2BD35">(2)</a></td>
      <td>The end date of the time range for the labor reporting data, in <code>YYYYMMDD</code> format. This is the same value as the start date.</td>
    </tr>
    <tr>
      <td><a href="#co-d1e4448134B67F3-A975-4412-A030-B6DDC7E2BD35">(3)</a></td>
      <td>The list of restaurant GUIDs from the management group to include in the labor reporting data. Restaurant GUIDs not listed are excluded.</td>
    </tr>
    <tr>
      <td><a href="#co-d1e4450134B67F3-A975-4412-A030-B6DDC7E2BD35">(4)</a></td>
      <td>The list of restaurant GUIDs from the management group to exclude from the labor reporting data. In this example, restaurants are included with the <code>restaurantIds</code> value, so all other restaurants are excluded automatically.</td>
    </tr>
    <tr>
      <td><a href="#co-d1e4452134B67F3-A975-4412-A030-B6DDC7E2BD35">(5)</a></td>
      <td>This request for labor reporting data is grouped by job.</td>
    </tr>
## Response to request for labor reporting data

The following example shows the response from the `/era/v1/labor/day` endpoint.


```
"707d9f10-e0fe-4e6d-af49-3123a78cd2b3"
```



    <tr>
      <td><a href="#co-d1e4509134B67F3-A975-4412-A030-B6DDC7E2BD35">(1)</a></td>
      <td>The GUID for the labor reporting data request, also called the <code>reportRequestGuid</code>. For more information about how to retrieve data using the analytics API, see <a href="apiDevGuide-apiAnalyticsUnderstandingProcess">Understanding the analytics API process</a>.</td>
    </tr>
For an example that shows how to retrieve the labor reporting data, see [Retrieving the labor reporting data](apiDevGuide-apiAnalyticsLaborReportingDataRetrieveData).

