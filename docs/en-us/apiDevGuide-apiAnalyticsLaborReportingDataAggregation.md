---
title: "Aggregating the labor reporting data"
id: apiAnalyticsLaborReportingDataAggregation
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiAnalyticsLaborReportingDataOmitChunkFromSearchIndex.md
parentSectionTitle: "Labor reporting data"
previousSectionFile: apiDevGuide-apiAnalyticsLaborReportingDataRetrieveData.md
previousSectionTitle: "Retrieving the labor reporting data"
nextSectionFile: apiDevGuide-apiAnalyticsLaborReportingDataUnderstandingData.md
nextSectionTitle: "Understanding the labor reporting data"
excerpt: "The default way to view the labor reporting data is by day for each location. You can choose to aggregate the data into subsections by either employee or job. Use the groupBy value in the message..."
keywords: ["aggregating", "labor", "reporting", "data", "groupBy", "/era/v1/labor/{timeRange}", "EMPLOYEE", "JOB", "YYYYMMDD"]
procedures: 0
codeExamples: 1
---

The default way to view the labor reporting data is by day for each location. You can choose to aggregate the data into subsections by either employee or job. Use the `groupBy` value in the message body of the `/era/v1/labor/&#123;timeRange&#125;` request to create these subsections. Use `EMPLOYEE` to group the labor reporting data by employee and `JOB` to group by job.



> **Note**
> 
> You can only aggregate using one value, either `EMPLOYEE` or `JOB`. Using both values results in an error.


The following example shows the message body for a `/era/v1/labor/week` request that uses the `groupBy` value with `EMPLOYEE`.


```
{
  “startBusinessDate”: “20230203”,
  “endBusinessDate”: “20230209”,
  “restaurantIds”: [],
  “groupBy”:  [“EMPLOYEE”]
}

```



    <tr className="">
      <td className=""><div className=""><a href="#co-d1e3346134B67F3-A975-4412-A030-B6DDC7E2BD35" className="">(1)</a></div></td>
      <td className=""><div className="">The start date of the time range for the labor reporting data, in <code className="">YYYYMMDD</code> format.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><a href="#co-d1e3348134B67F3-A975-4412-A030-B6DDC7E2BD35" className="">(2)</a></div></td>
      <td className=""><div className="">The end date of the time range for the labor reporting data, in <code className="">YYYYMMDD</code> format.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><a href="#co-d1e3350134B67F3-A975-4412-A030-B6DDC7E2BD35" className="">(3)</a></div></td>
      <td className=""><div className="">The list of restaurant GUIDs from the management group to include in the labor reporting data. Restaurant GUIDs not listed are excluded.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><a href="#co-d1e3352134B67F3-A975-4412-A030-B6DDC7E2BD35" className="">(4)</a></div></td>
      <td className=""><div className="">This request is for labor reporting data grouped by employee.</div></td>
    </tr>
When you use `EMPLOYEE`, the data is split into subsections by restaurant, then by day for the restaurant, and then by employee for the day at that restaurant. For example, the following list shows the structure of labor reporting data for two example restaurants, covering two days and four employees.

- Restaurant 1, Day 1, Employee 1


- Restaurant 1, Day 1, Employee 2


- Restaurant 1, Day 2, Employee 2


- Restaurant 1, Day 2, Employee 3


- Restaurant 2, Day 1, Employee 3


- Restaurant 2, Day 1, Employee 4


- Restaurant 2, Day 2, Employee 1


- Restaurant 2, Day 2, Employee 4





> **Note**
> 
> The data is not organized chronologically by day or alphabetically by employee name.


When you use `JOB`, the data is split into subsections by restaurant, then by day for the restaurant, and then by job for the day at that restaurant. For example, the following list shows the structure of labor reporting data for two example restaurants, covering two days and four jobs.

- Restaurant 1, Day 1, Job 1


- Restaurant 1, Day 1, Job 2


- Restaurant 1, Day 2, Job 2


- Restaurant 1, Day 2, Job 3


- Restaurant 2, Day 1, Job 3


- Restaurant 2, Day 1, Job 4


- Restaurant 2, Day 2, Job 1


- Restaurant 2, Day 2, Job 4





> **Note**
> 
> The data is not organized chronologically by day or alphabetically by job name.


## Example of labor reporting data aggregated by employee

The following example requests labor reporting data for three days and two restaurants, and is grouped into subsections by employee.

### Request for labor reporting data

The following example **curl** command sends a `POST` request to the `/era/v1/labor/week` endpoint.


```
curl -i -X POST \ 'https://[toast-api-hostname]/era/v1/labor/week' \
  -H 'Authorization: Bearer [token]' \
  -H 'Content-Type: application/json' \
  -d @[request-info].json \
```



    <tr className="">
      <td className=""><div className=""><a href="#co-d1e3545134B67F3-A975-4412-A030-B6DDC7E2BD35" className="">(1)</a></div></td>
      <td className=""><div className="">Send a <code className="">POST</code> request to the <code className="">/era/v1/labor/&#123;timeRange&#125;</code> endpoint of the analytics API. The <code className="">&#123;timeRange&#125;</code> in this example is <code className="">week</code>.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><a href="#co-d1e3547134B67F3-A975-4412-A030-B6DDC7E2BD35" className="">(2)</a></div></td>
      <td className=""><div className="">Include an authentication token. For more information, see <a href="apiDevGuide-authentication" className="">Authentication and restaurant access</a>.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><a href="#co-d1e3549134B67F3-A975-4412-A030-B6DDC7E2BD35" className="">(3)</a></div></td>
      <td className=""><div className="">Set the data type of the message body to <code className="">application/json</code>.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><a href="#co-d1e3551134B67F3-A975-4412-A030-B6DDC7E2BD35" className="">(4)</a></div></td>
      <td className=""><div className="">Include details about the requested labor reporting data in the message body. The following example is the message body for this <strong className="">curl</strong>  command example.</div></td>
    </tr>
### Message body for the labor reporting data request

The following example shows the message body for the `/era/v1/labor/week` request that uses the `groupBy` value with `EMPLOYEE`.


```
{
  "startBusinessDate": "20230203",
  "endBusinessDate": "20230205",
  "restaurantIds": [],
  "excludedRestaurantIds": [],
  "groupBy": ["EMPLOYEE"]
}

```



    <tr className="">
      <td className=""><div className=""><a href="#co-d1e3611134B67F3-A975-4412-A030-B6DDC7E2BD35" className="">(1)</a></div></td>
      <td className=""><div className="">The start date of the time range for the labor reporting data, in <code className="">YYYYMMDD</code> format.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><a href="#co-d1e3613134B67F3-A975-4412-A030-B6DDC7E2BD35" className="">(2)</a></div></td>
      <td className=""><div className="">The end date of the time range for the labor reporting data, in <code className="">YYYYMMDD</code> format. The <code className="">endBusinessDate</code> value is optional for requests using the <code className="">day</code> time range.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><a href="#co-d1e3615134B67F3-A975-4412-A030-B6DDC7E2BD35" className="">(3)</a></div></td>
      <td className=""><div className="">The list of restaurant GUIDs from the management group to include in the labor reporting data. Restaurant GUIDs not listed are excluded.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><a href="#co-d1e3617134B67F3-A975-4412-A030-B6DDC7E2BD35" className="">(4)</a></div></td>
      <td className=""><div className="">The list of restaurant GUIDs from the management group to exclude from the labor reporting data. For this example, no restaurants are listed, so all other restaurants are included.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><a href="#co-d1e3619134B67F3-A975-4412-A030-B6DDC7E2BD35" className="">(5)</a></div></td>
      <td className=""><div className="">This request is for labor reporting data grouped by employee.</div></td>
    </tr>


> **Important**
> 
> Adding restaurant GUIDs to both `restaurantIds`and `excludedRestaurantIds` results in an error.


### Response to the labor reporting data request

The following example shows the response from the `/era/v1/labor/day` endpoint.


```
"97adf06d-60c3-4224-8062-003c9157702e"
```



    <tr className="">
      <td className=""><div className=""><a href="#co-d1e3693134B67F3-A975-4412-A030-B6DDC7E2BD35" className="">(1)</a></div></td>
      <td className=""><div className="">The GUID for the labor reporting data request, also called the <code className="">reportRequestGuid</code>. For more information about how to retrieve data using the analytics API, see <a href="apiDevGuide-apiAnalyticsUnderstandingProcess" className="">Understanding the analytics API process</a>.</div></td>
    </tr>
### Request to retrieve the labor reporting data

The following example **curl** command sends a `GET` request to the `/era/v1/labor/&#123;reportRequestGuid&#125;` endpoint.


```
curl -X GET \ 'https://[toast-api-hostname]/era/v1/labor/
97adf06d-60c3-4224-8062-003c9157702e/' \
  -H 'Authorization: Bearer [token]'
```



    <tr className="">
      <td className=""><div className=""><a href="#co-d1e3730134B67F3-A975-4412-A030-B6DDC7E2BD35" className="">(1)</a></div></td>
      <td className=""><div className="">Send a <code className="">GET</code> request to the <code className="">/era/v1/labor</code> endpoint of the analytics API.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><a href="#co-d1e3732134B67F3-A975-4412-A030-B6DDC7E2BD35" className="">(2)</a></div></td>
      <td className=""><div className="">Include the GUID for the labor reporting data request, also called the <code className="">reportRequestGuid</code>. For more information about how to retrieve data using the analytics API, see <a href="apiDevGuide-apiAnalyticsUnderstandingProcess" className="">Understanding the analytics API process</a>.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><a href="#co-d1e3734134B67F3-A975-4412-A030-B6DDC7E2BD35" className="">(3)</a></div></td>
      <td className=""><div className="">Include an authentication token. For more information, see <a href="apiDevGuide-authentication" className="">Authentication and restaurant access</a>.</div></td>
    </tr>
### Response to the retrieval request for labor reporting data

The following example shows the response from the `/era/v1/labor/&#123;reportRequestGuid&#125;` endpoint.


```
[
   {
       "restaurantGuid": "95a96d7b-dbf5-46d3-98c5-c65c8ad18021",
       "businessDate": 20230204,
       [content omitted]
       "jobGuid": null,
       "jobTitle": null,
       "jobCode": null,
       "employeeGuid": "68001176-111e-403f-9157-3459f8c5c284",
       "employeeFirstName": "Elizabeth",
       "employeeLastName": "Bennet",
       "employeeChosenName": "Lizzie",
       "restaurantName": "Grove Place Cafe",
       "restaurantLocationName": null,
       "restaurantLocationCode": ""
   },
   {
       "restaurantGuid": "95a96d7b-dbf5-46d3-98c5-c65c8ad18021",
       "businessDate": 20230204,
       [content omitted]
       "jobGuid": null,
       "jobTitle": null,
       "jobCode": null,
       "employeeGuid": "daf8623e-3e5b-4ee6-955e-6cf485cb4d23",
       "employeeFirstName": "Esther",
       "employeeLastName": "Summerson",
       "employeeChosenName": null,
       "restaurantName": "Grove Place Cafe",
       "restaurantLocationName": null,
       "restaurantLocationCode": ""
   },
   [content omitted]
   {
       "restaurantGuid": "95a96d7b-dbf5-46d3-98c5-c65c8ad18021",
       "businessDate": 20230203,
       [content omitted]
       "jobGuid": null,
       "jobTitle": null,
       "jobCode": null,
       "employeeGuid": "e509a2dd-9e66-11ed-9c8b-0284a90dacf9",
       "employeeFirstName": "Anne",
       "employeeLastName": "Shirley",
       "employeeChosenName": null,
       "restaurantName": "Grove Place Cafe",
       "restaurantLocationName": null,
       "restaurantLocationCode": ""
   },
   {
       "restaurantGuid": "95a96d7b-dbf5-46d3-98c5-c65c8ad18021",
       "businessDate": 20230203,
       [content omitted]
       "jobGuid": null,
       "jobTitle": null,
       "jobCode": null,
       "employeeGuid": "68001176-111e-403f-9157-3459f8c5c284",
       "employeeFirstName": "Elizabeth",
       "employeeLastName": "Bennet",
       "employeeChosenName": "Lizzie",
       "restaurantName": "Grove Place Cafe",
       "restaurantLocationName": null,
       "restaurantLocationCode": ""
   },
   [content omitted]   
   {
       "restaurantGuid": "b6bae410-1316-4d3b-b01f-47a758811db2",
       "businessDate": 20230203,
       [content omitted]
       "jobGuid": null,
       "jobTitle": null,
       "jobCode": null,
       "employeeGuid": null,
       "employeeFirstName": "James",
       "employeeLastName": "Hawkins",
       "employeeChosenName": "Jim",
       "restaurantName": "Summer Street Cafe",
       "restaurantLocationName": null,
       "restaurantLocationCode": ""
   },
   {
       "restaurantGuid": "b6bae410-1316-4d3b-b01f-47a758811db2",
       "businessDate": 20230203,
       [content omitted]
       "jobGuid": null,
       "jobTitle": null,
       "jobCode": null,
       "employeeGuid": "840a313f-8bc2-11ed-9c8b-0284a90dacf9",
       "employeeFirstName": "Nicholas",
       "employeeLastName": "Carraway",
       "employeeChosenName": "Nick",
       "restaurantName": "Summer Street Cafe",
       "restaurantLocationName": null,
       "restaurantLocationCode": ""
   },
   [content omitted]
   {
       "restaurantGuid": "b6bae410-1316-4d3b-b01f-47a758811db2",
       "businessDate": 20230204,
       [content omitted]
       "jobGuid": null,
       "jobTitle": null,
       "jobCode": null,
       "employeeGuid": "daf8623e-3e5b-4ee6-955e-6cf485cb4d23",
       "employeeFirstName": "Esther",
       "employeeLastName": "Summerson",
       "employeeChosenName": null,
       "restaurantName": "Summer Street Cafe",
       "restaurantLocationName": null,
       "restaurantLocationCode": ""
   }
   {
       "restaurantGuid": "b6bae410-1316-4d3b-b01f-47a758811db2",
       "businessDate": 20230204,
       [content omitted]
       "jobGuid": null,
       "jobTitle": null,
       "jobCode": null,
       "employeeGuid": "e509a2dd-9e66-11ed-9c8b-0284a90dacf9",
       "employeeFirstName": "Anne",
       "employeeLastName": "Shirley",
       "employeeChosenName": null,
       "restaurantName": "Summer Street Cafe",
       "restaurantLocationName": null,
       "restaurantLocationCode": ""
   },
   [content omitted]
]

```

