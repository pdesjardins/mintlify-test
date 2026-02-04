---
title: "Retrieving the labor reporting data"
id: apiAnalyticsLaborReportingDataRetrieveData
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiAnalyticsLaborReportingDataOmitChunkFromSearchIndex.md
parentSectionTitle: "Labor reporting data"
previousSectionFile: apiDevGuide-apiAnalyticsLaborReportingDataCreateRequest.md
previousSectionTitle: "Creating a request for labor reporting data"
nextSectionFile: apiDevGuide-apiAnalyticsLaborReportingDataAggregation.md
nextSectionTitle: "Aggregating the labor reporting data"
excerpt: "Send..."
keywords: ["retrieving", "labor", "reporting", "data", "/era/v1/labor/{reportRequestGuid}", "reportRequestGuid"]
procedures: 0
codeExamples: 0
---

Send a `GET` request to the `/era/v1/labor/\{reportRequestGuid\}` endpoint to retrieve labor reporting data. The rate limit for this endpoint and method type is five requests per second and 30 requests per minute. For more information about API rate limits for the analytics API, see [Analytics API rate limits](apiAnalyticsRateLimiting.html).

To request the labor reporting data, you must include the labor reporting data request GUID, or `reportRequestGuid`, as a path variable.

## Request to retrieve labor reporting data

The following example **curl** command sends a `GET` request to the `/era/v1/labor/\{reportRequestGuid\}` endpoint.

```
curl -X GET \ 'https://[toast-api-hostname]/era/v1/labor/
707d9f10-e0fe-4e6d-af49-3123a78cd2b3’ \
  -H 'Authorization: Bearer [token]'
```



(1) Send a GET request to the /era/v1/labor endpoint of the analytics API.

(2) The GUID for the labor reporting data request, also called the reportRequestGuid. For more information about how to retrieve data using the analytics API, see Understanding the analytics API process.

(3) Include an authentication token. For more information, see Authentication and restaurant access.

## Response to the retrieval request for labor reporting data

The following example shows the response from the `/era/v1/labor/\{reportRequestGuid\}` endpoint.

```
[
   \{
       "restaurantGuid": "95a96d7b-dbf5-46d3-98c5-c65c8ad18021",
       "businessDate": 20230203,
       "regularHours": 47.645,
       "overtimeHours": 0.0,
       "totalHours": 47.645,
       "regularCost": 823.86,
       "overtimeCost": 0.0,
       "totalCost": 823.86,
       "netSalesAmount": null,
       "grossSalesAmount": null,
       "netSalesPerEmployeeHour": null,
       "grossSalesPerEmployeeHour": null,
       "totalCostPerNetSales": 11.95,
       "totalCostPerGrossSales": 11.58,
       "jobGuid": "fcdc414a-06af-4e3f-97d3-6924a2189415",
       "jobTitle": "Line Cook",
       "jobCode": "",
       "employeeGuid": null,
       "employeeFirstName": null,
       "employeeLastName": null,
       "employeeChosenName": null,
       "restaurantName": "Grove Place Cafe",
       "restaurantLocationName": null,
       "restaurantLocationCode": ""
   },
   \{
       "restaurantGuid": "95a96d7b-dbf5-46d3-98c5-c65c8ad18021",
       "businessDate": 20230203,
       "regularHours": 5.8,
       "overtimeHours": 0.0,
       "totalHours": 5.8,
       "regularCost": 69.9,
       "overtimeCost": 0.0,
       "totalCost": 69.9,
       "netSalesAmount": null,
       "grossSalesAmount": null,
       "netSalesPerEmployeeHour": null,
       "grossSalesPerEmployeeHour": null,
       "totalCostPerNetSales": 1.01,
       "totalCostPerGrossSales": 0.98,
       "jobGuid": "2c9a9356-b29b-4095-a23e-064779dc8eb3",
       "jobTitle": "Host",
       "jobCode": "",
       "employeeGuid": null,
       "employeeFirstName": null,
       "employeeLastName": null,
       "employeeChosenName": null,
       "restaurantName": "Grove Place Cafe",
       "restaurantLocationName": null,
       "restaurantLocationCode": ""
   },
   \{
       "restaurantGuid": "95a96d7b-dbf5-46d3-98c5-c65c8ad18021",
       "businessDate": 20230203,
       "regularHours": 11.759,
       "overtimeHours": 0.0,
       "totalHours": 11.759,
       "regularCost": 79.37,
       "overtimeCost": 0.0,
       "totalCost": 79.37,
       "netSalesAmount": null,
       "grossSalesAmount": null,
       "netSalesPerEmployeeHour": null,
       "grossSalesPerEmployeeHour": null,
       "totalCostPerNetSales": 1.15,
       "totalCostPerGrossSales": 1.12,
       "jobGuid": "cc115ae8-f81c-42c7-b21e-4da19c396021",
       "jobTitle": "Server",
       "jobCode": "",
       "employeeGuid": null,
       "employeeFirstName": null,
       "employeeLastName": null,
       "employeeChosenName": null,
       "restaurantName": "Grove Place Cafe",
       "restaurantLocationName": null,
       "restaurantLocationCode": ""
   },
   \{
       "restaurantGuid": "95a96d7b-dbf5-46d3-98c5-c65c8ad18021",
       "businessDate": 20230203,
       "regularHours": 37.988,
       "overtimeHours": 0.0,
       "totalHours": 37.988,
       "regularCost": 256.42,
       "overtimeCost": 0.0,
       "totalCost": 256.42,
       "netSalesAmount": null,
       "grossSalesAmount": null,
       "netSalesPerEmployeeHour": null,
       "grossSalesPerEmployeeHour": null,
       "totalCostPerNetSales": 3.72,
       "totalCostPerGrossSales": 3.6,
       "jobGuid": "e2ab1fbd-c766-460d-8781-0d742d228e34",
       "jobTitle": "Service Prep",
       "jobCode": "",
       "employeeGuid": null,
       "employeeFirstName": null,
       "employeeLastName": null,
       "employeeChosenName": null,
       "restaurantName": "Grove Place Cafe",
       "restaurantLocationName": null,
       "restaurantLocationCode": ""
   },
   \{
       "restaurantGuid": "b6bae410-1316-4d3b-b01f-47a758811db2",
       "businessDate": 20230203,
       "regularHours": 9.333,
       "overtimeHours": 0.0,
       "totalHours": 9.333,
       "regularCost": 149.33,
       "overtimeCost": 0.0,
       "totalCost": 149.33,
       "netSalesAmount": null,
       "grossSalesAmount": null,
       "netSalesPerEmployeeHour": null,
       "grossSalesPerEmployeeHour": null,
       "totalCostPerNetSales": 2.17,
       "totalCostPerGrossSales": 2.1,
       "jobGuid": "e2ab1fbd-c766-460d-8781-0d742d228e34",
       "jobTitle": "Service Prep",
       "jobCode": "",
       "employeeGuid": null,
       "employeeFirstName": null,
       "employeeLastName": null,
       "employeeChosenName": null,
       "restaurantName": "Summer Street Cafe",
       "restaurantLocationName": null,
       "restaurantLocationCode": ""
   },
   \{
       "restaurantGuid": "b6bae410-1316-4d3b-b01f-47a758811db2",
       "businessDate": 20230203,
       "regularHours": 9.5,
       "overtimeHours": 0.0,
       "totalHours": 9.5,
       "regularCost": 114.0,
       "overtimeCost": 0.0,
       "totalCost": 114.0,
       "netSalesAmount": null,
       "grossSalesAmount": null,
       "netSalesPerEmployeeHour": null,
       "grossSalesPerEmployeeHour": null,
       "totalCostPerNetSales": 1.65,
       "totalCostPerGrossSales": 1.6,
       "jobGuid": "b33bc9ee-04e1-46b6-ab7d-f95dad362414",
       "jobTitle": "Bartender",
       "jobCode": "",
       "employeeGuid": null,
       "employeeFirstName": null,
       "employeeLastName": null,
       "employeeChosenName": null,
       "restaurantName": "Summer Street Cafe",
       "restaurantLocationName": null,
       "restaurantLocationCode": ""
   },
   \{
       "restaurantGuid": "95a96d7b-dbf5-46d3-98c5-c65c8ad18021",
       "businessDate": 20230203,
       "regularHours": 11.759,
       "overtimeHours": 0.0,
       "totalHours": 11.759,
       "regularCost": 79.37,
       "overtimeCost": 0.0,
       "totalCost": 79.37,
       "netSalesAmount": null,
       "grossSalesAmount": null,
       "netSalesPerEmployeeHour": null,
       "grossSalesPerEmployeeHour": null,
       "totalCostPerNetSales": 1.15,
       "totalCostPerGrossSales": 1.12,
       "jobGuid": "cc115ae8-f81c-42c7-b21e-4da19c396021",
       "jobTitle": "Server",
       "jobCode": "",
       "employeeGuid": null,
       "employeeFirstName": null,
       "employeeLastName": null,
       "employeeChosenName": null,
       "restaurantName": "Grove Place Cafe",
       "restaurantLocationName": null,
       "restaurantLocationCode": ""
   \}
]

```

For more information about the values in the response, see [Understanding the labor reporting data](apiAnalyticsLaborReportingDataUnderstandingData.html).

