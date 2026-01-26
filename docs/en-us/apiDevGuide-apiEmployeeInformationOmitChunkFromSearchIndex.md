---
title: "Chapter 7. Employees"
id: apiEmployeeInformationOmitChunkFromSearchIndex
type: chapter
documentId: apiDevGuide
parentSectionFile: apiDevGuide-index.md
parentSectionTitle: "Developer guide"
previousSectionFile: apiDevGuide-apiGettingRxOnlineOrderingAvailability.md
previousSectionTitle: "Getting a restaurant's online ordering availability"
nextSectionFile: apiDevGuide-apiWorkingWithEmployeesOmitChunkFromSearchIndex.md
nextSectionTitle: "Updating employee information"
externalReferences: [https://central.toasttab.com/s/article/Enforcing-Scheduling-Time-Clock-Rules-with-Integration-Partners-1492745815961, https://stedolan.github.io/jq/]
procedures: 0
codeExamples: 0
---

# Chapter 7. Employees

## Getting employee information

### Getting all employees of a restaurant

To get information about the employees of a restaurant, send a `GET`request to the `/labor/v1/employees`endpoint of the labor API.

The request returns an array of `Employee`objects that contain the configuration information for each employee.

#### Example request for information about all employees

The following example **curl**command sends a `GET`request to the `/labor/v1/employees`endpoint.

**Example 7.1. Example request to GET all employees of a restaurant**

```
curl -X GET \
-H "Authorization: Bearer eyJzI1NiJ9hbGciOiJSU.eyJhd9yaXR5Ij
oiQ1JVTkNIVElNRSIsInJzR3VpZCI6IjE4YzQ5YWJlLWFlODItNGFlYy04ND
M1LWJhYTRjMjVlYTY2MiIsInNjb3BlIjpbImxWQiOlsidG9hc3QiXSwibmFt
aW5nQXV0aGhYm9yIiwib3JkZXJzIiwidXNlcm1nbXQiXSwiZXhwIjoxNDg0M
zg5ODUwLCJqdGkiOiJlMDYzZjJkMy1jNGYyLTRiZjItODJmNi01MTg1NWMzZ
DAxM2YiLCJjbGllbnRfaWQiOiJjcnVuY2h0aW1lIn0.X1_0y9Hzj5F9gdOw2
o6VSYTyZwooAJiFMDmNakbZrtiUdYwLzuLwLpCMQzX5pKYtOqDUz_cetGJL3
txKL1L-K2j1Enoq8An8hEM6e8J0KdAiwrYFO3W3CmWedaoz95K9ghNZVCs28
Td2Sp3Ix3fObxbrvanocx9_OT8S9uM8hdSXmBI_ykTWvOVgK4hO24V3DJy4b
9bz1FtgOvrClhELxCe8dJy7jiwAR60xczlCF5rna98RMLN6zY4ffjmljKFZ6
QV0KkVppWjEiJn7oFHiIylCX1sSg7sddrGatj0xJzts3GJ8u8_lryUNHaEvJ
dWq4Yzwo007AMgxjH9d241Y-g" \
-H "Toast-Restaurant-External-ID: 4622e7a9-b4be-3fef-9220-b3dad273e0b4" \[(1)](apiDevGuide-apiEmployeeInformationOmitChunkFromSearchIndex.html#co-get-employees)
https://*`[toast-api-hostname]`*/labor/v1/employees
```



 Specify the GUID of the restaurant that you want to GETemployees for. This must be an individual restaurant, not the GUID for a restaurant group.

  
#### Example response

The following example shows the response for a `GET`request to the `/labor/v1/employees`resource.

**Example 7.2. Example response to a request to GET restaurant employees**

```
[
  {[(1)](apiDevGuide-apiEmployeeInformationOmitChunkFromSearchIndex.html#d1e68BDD1A7D6-D479-4A5F-A4A1-975B60C265DD-co)
    "guid": "b7946411-7d45-4beb-9bfc-0ec731da7b45",[(2)](apiDevGuide-apiEmployeeInformationOmitChunkFromSearchIndex.html#d1e70BDD1A7D6-D479-4A5F-A4A1-975B60C265DD-co)
    "entityType": "RestaurantUser",
    "externalId": null,
    "lastName": "Mercier",
    "wageOverrides": [],
    "firstName": "Jean-Guy",
    "chosenName": "Jean",
    "createdDate": "2016-12-21T16:11:18.994+0000",
    "deleted": false,
    "deletedDate": "1970-01-01T00:00:00.000+0000",
    "jobReferences": [
      {
        "guid": "34ff8f6e-15e6-4ec1-b496-f57fc18fa0c6",
        "entityType": "RestaurantJob",
        "externalId": null
      }
    ],
    "modifiedDate": "2016-12-21T16:19:06.195+0000",
    "disabled": false,
    "externalEmployeeId": "1234567890",
    "email": "jmercier@arestaurant.com"
  },
  {[(3)](apiDevGuide-apiEmployeeInformationOmitChunkFromSearchIndex.html#d1e72BDD1A7D6-D479-4A5F-A4A1-975B60C265DD-co)
    "guid": "abbafa20-0cbe-47e3-93e4-b69309e1bc33",
    "entityType": "RestaurantUser",
    "externalId": null,
    "lastName": "Ouellet",
    "wageOverrides": [],
    "firstName": "Clement",
    "chosenName": "Clem",
    "createdDate": "2016-08-31T20:19:02.666+0000",
    "deleted": true,
    "deletedDate": "2016-11-23T15:54:23.634+0000",
    "jobReferences": [
      {
        "guid": "a5eec1c0-1143-4408-bb6b-3d4b28a594a3",
        "entityType": "RestaurantJob",
        "externalId": null
      }
    ],
    "modifiedDate": "2016-11-23T15:54:23.635+0000",
    "disabled": false,
    "externalEmployeeId": "",
    "email": "couellet@arestaurant.com"
  }
]

```



(1) The GETrequest returns an array of employee objects. Each object contains information about an employee.

(2) The guidvalue contains the unique Toast platform identifier for the employee.

(3) Each object contains information for a different employee.

  
### Getting time entries for employees

To get the time entry records for the employees at your restaurant, send a `GET`request to the `/labor/v1/timeEntries`resource of the labor API. Time entries record information about the shifts that employees complete. The response contains an array of time entry objects that contain information about the time entries.

If an employee has not clocked out of the work shift, the `outDate`value for the time entry is `null`. The time entry period is not yet complete. Time entry values can change as the server takes new orders and payments during an active work shift.

When the employee clocks out, the `outDate`value is set to the date and time that the employee closed the work shift. The time entry is then complete. At this point, the monetary values in the time entry are static and are not updated by other activities in the restaurant. For example, if an employee has $100 of non-cash sales in their time entry when they clock out, and then an order of $10 non-cash sales is later transferred to the employee, the `nonCashSales`value of the time entry is still $100, not $110. The same applies to tips.

#### Example request for employee time entries

The following example **curl**command sends a `GET`request to the `/labor/v1/timeEntries`endpoint.

**Example 7.3. Example request to GET the time entries for restaurant employees**

```
curl -v -X GET \
-H "Authorization: Bearer eyJzI1NiJ9hbGciOiJSU.eyJhd9yaXR5Ij
oiQ1JVTkNIVElNRSIsInJzR3VpZCI6IjE4YzQ5YWJlLWFlODItNGFlYy04ND
M1LWJhYTRjMjVlYTY2MiIsInNjb3BlIjpbImxWQiOlsidG9hc3QiXSwibmFt
aW5nQXV0aGhYm9yIiwib3JkZXJzIiwidXNlcm1nbXQiXSwiZXhwIjoxNDg0M
zg5ODUwLCJqdGkiOiJlMDYzZjJkMy1jNGYyLTRiZjItODJmNi01MTg1NWMzZ
DAxM2YiLCJjbGllbnRfaWQiOiJjcnVuY2h0aW1lIn0.X1_0y9Hzj5F9gdOw2
o6VSYTyZwooAJiFMDmNakbZrtiUdYwLzuLwLpCMQzX5pKYtOqDUz_cetGJL3
txKL1L-K2j1Enoq8An8hEM6e8J0KdAiwrYFO3W3CmWedaoz95K9ghNZVCs28
Td2Sp3Ix3fObxbrvanocx9_OT8S9uM8hdSXmBI_ykTWvOVgK4hO24V3DJy4b
9bz1FtgOvrClhELxCe8dJy7jiwAR60xczlCF5rna98RMLN6zY4ffjmljKFZ6
QV0KkVppWjEiJn7oFHiIylCX1sSg7sddrGatj0xJzts3GJ8u8_lryUNHaEvJ
dWq4Yzwo007AMgxjH9d241Y-g" \
-H "Toast-Restaurant-External-ID: 4622e7a9-b4be-3fef-9220-b3dad273e0b4" \[(1)](apiDevGuide-apiEmployeeInformationOmitChunkFromSearchIndex.html#d1e15283A590EF-007A-48DE-8B8A-FE6BF2FE2ADA-co)
"https://*`[toast-api-hostname]`*/labor/v1/timeEntries?startDate=[(2)](apiDevGuide-apiEmployeeInformationOmitChunkFromSearchIndex.html#d1e15783A590EF-007A-48DE-8B8A-FE6BF2FE2ADA-co)
2018-11-14T01:00:00.000-0000&endDate=2018-11-16T01:00:00.000-0000
&includeMissedBreaks=true"[(3)](apiDevGuide-apiEmployeeInformationOmitChunkFromSearchIndex.html#d1e15983A590EF-007A-48DE-8B8A-FE6BF2FE2ADA-co)
```



(1) Specify the GUID of the restaurant that you want to GETtime entries for. This must be an individual restaurant, not the GUID for a restaurant group.

(2) Specify the start and end dates of the time period you want to GETtime entries for. You can select a period of up to 30 days.

(3) The timeEntriesendpoint accepts the includeMissedBreaksquery parameter. If you set the value of includeMissedBreaksto true, the timeEntriesendpoint returns TimeEntryBreakobjects for scheduled break periods even if an employee did not take them. The includeMissedBreaksparameter is optional. If you do not include the parameter, the endpoint returns only breaks that were taken, not breaks that were missed.

  
#### Example response

The following example shows a time entry for an employee.

**Example 7.4. Example response containing an employee time entry**

```
[
  {[(1)](apiDevGuide-apiEmployeeInformationOmitChunkFromSearchIndex.html#d1e21739786C5B-846E-4DDA-823C-AF858E53331A-co)
    "guid": "26ac616b-b0d2-4d4e-b89b-62291be33d80",
    "entityType": null,
    "externalId": null,
    "nonCashSales": 0,[(2)](apiDevGuide-apiEmployeeInformationOmitChunkFromSearchIndex.html#d1e21939786C5B-846E-4DDA-823C-AF858E53331A-co)
    "outDate": "2018-11-15T19:17:34.653+0000",[(3)](apiDevGuide-apiEmployeeInformationOmitChunkFromSearchIndex.html#d1e22139786C5B-846E-4DDA-823C-AF858E53331A-co)
    "overtimeHours": 0,
    "breaks": [[(4)](apiDevGuide-apiEmployeeInformationOmitChunkFromSearchIndex.html#d1e22339786C5B-846E-4DDA-823C-AF858E53331A-co)
      {
        "breakType": {
          "guid": "8ed442b0-ca52-416d-8976-f941184eba15",
          "entityType": "BreakType"
        },
        "paid": true,
        "inDate": "2018-11-15T14:19:27.043+0000",
        "outDate": "2018-11-15T14:30:35.490+0000",
        "missed": false,
        "auditResponse": true
      },
      {
        "breakType": {
          "guid": "8ed442b0-ca52-416d-8976-f941184eba15",
          "entityType": "BreakType"
        },
        "paid": true,
        "inDate": "2018-11-15T18:13:46.894+0000",
        "outDate": null,
        "missed": true,
        "auditResponse": true
      }
    ],
    "employeeReference": {[(5)](apiDevGuide-apiEmployeeInformationOmitChunkFromSearchIndex.html#d1e22539786C5B-846E-4DDA-823C-AF858E53331A-co)
      "guid": "a0c9070e-fffd-4e97-b3ea-fc356fbf9224",
      "entityType": "RestaurantUser",
      "externalId": null
    },
    "shiftReference": "56387b8e-78df-47a4-9395-e5e1cb3f04d1",[(6)](apiDevGuide-apiEmployeeInformationOmitChunkFromSearchIndex.html#shiftReferenceDescription)
    "nonCashGratuityServiceCharges": 0,[(7)](apiDevGuide-apiEmployeeInformationOmitChunkFromSearchIndex.html#d1e22839786C5B-846E-4DDA-823C-AF858E53331A-co)
    "inDate": "2018-11-15T14:14:46.894+0000",
    "regularHours": 5.046599722222222,
    "jobReference": {[(8)](apiDevGuide-apiEmployeeInformationOmitChunkFromSearchIndex.html#d1e23039786C5B-846E-4DDA-823C-AF858E53331A-co)
      "guid": "8b623183-7d6f-4f7c-babb-e74fe722ad30",
      "entityType": "RestaurantJob",
      "externalId": null
    },
    "tipsWithheld": 0,[(9)](apiDevGuide-apiEmployeeInformationOmitChunkFromSearchIndex.html#d1e23239786C5B-846E-4DDA-823C-AF858E53331A-co)
    "businessDate": "20181115",
    "cashGratuityServiceCharges": 12.95,[(10)](apiDevGuide-apiEmployeeInformationOmitChunkFromSearchIndex.html#d1e23439786C5B-846E-4DDA-823C-AF858E53331A-co)
    "createdDate": "2018-11-15T14:14:47.503+0000",
    "deleted": false,
    "deletedDate": null,
    "cashSales": 139.02,[(11)](apiDevGuide-apiEmployeeInformationOmitChunkFromSearchIndex.html#d1e23639786C5B-846E-4DDA-823C-AF858E53331A-co)
    "hourlyWage": 7.5,
    "nonCashTips": 0,[(12)](apiDevGuide-apiEmployeeInformationOmitChunkFromSearchIndex.html#d1e23839786C5B-846E-4DDA-823C-AF858E53331A-co)
    "modifiedDate": "2018-11-15T19:17:35.801+0000",
    "declaredCashTips": 30[(13)](apiDevGuide-apiEmployeeInformationOmitChunkFromSearchIndex.html#d1e24139786C5B-846E-4DDA-823C-AF858E53331A-co)
  }
]
```



(1) The GETrequest returns an array of time entry objects. Each object contains information about an employee's shift.

(2) The nonCashSalesvalue shows the total non-cash sales in the orders opened by the employee during the time entry period. The value includes tax amounts, but does not include tip or gratuity amounts. For example, nonCashSalesincludes credit card payments, gift card payments, and payments using options that you configure in the Other Payment Options screen of Toast Web. If the outDatevalue for the time entry is null, then the time entry period is not complete, and the sales totals are 0. If the outDatevalue for the time entry is set, the sales totals are final and will not change. If you make changes to an order after the time entry is complete, the sales totals for the time entry do not change.

(3) The time entry object contains information about the shift worked. For example, this outDatevalue specifies the date and time that the employee clocked out (the value is nullif the employee has not clocked out).

(4) The breaksarray contains break type objects that contain information about breaks taken by the employee: breakTypeis the Toast platform GUID of the type of employee break period. You configure types of employee break periods for your restaurant. inDatespecifies when the employee started the break and outDateis when the employee ended the break. The datetime values are in UTC (Universal Time Coordinated). paidis a Boolean value that indicates whether the employee was paid for the break. If the value is true, the employee was paid for the break. If the value is false, the employee was not paid for the break. missedis a Boolean value that indicates whether the employee took the break. If the value is true, the employee did not take the break. If the value is false, the employee did take the break. auditResponseis a Boolean value that indicates whether the employee was asked to take the break. If the value is true, the employee was asked to take the break. If the value is false, the employee was not asked to take the break. If the value is null, either the break type is not configured to use break acknowledgement, or the employee did not respond to the break acknowledgement prompt on the Toast POS device. For information on configuring missed breaks and break acknowledgements, see Tracking missed breaks and acknowledging breaks in the Toast Platform Guide .

(5) The employeeReferencevalue specifies the employee who worked the shift.

 The GUID of the Shiftobject associated with this time entry. The shiftReferencevalue on a TimeEntryobject is only populated if the restaurant uses Toast's clock-in enforcement feature , and the employee clocked into their shift within the restaurant's allowed window. Otherwise, the shiftReferencevalue is null.

(7) The nonCashGratuityServiceChargesvalue is the amount of gratuity service charges paid to the employee in non-cash tender (such as credit cards).

(8) The jobReferencevalue specifies the job that the employee performed.

(9) The tipsWithheldvalue specifies the amount withheld from the employee's credit card tips.

(10) The cashGratuityServiceChargesvalue is the amount of gratuity service charges paid in cash to the employee.

(11) The cashSalesvalue shows the total cash sales in the orders opened by the employee during the time entry period. The cash sales amount includes tax amounts, but does not include tip or gratuity amounts. If the outDatevalue for the time entry is null(the time entry period is not complete), the sales totals are 0. If the outDatevalue for the time entry is set, the sales totals are final and will not change. If you make changes to an order after the time entry is complete, the sales totals for the time entry do not change.

(12) The nonCashTipsvalue lists the total amount of tips paid to the employee in non-cash tender.

(13) The declaredCashTipsvalue is the amount of tips paid to the employee in cash.

  
### Getting shift assignments for employees

To get information about the shifts that are scheduled for employees of a restaurant, send a `GET`request to the `/labor/v1/shifts`endpoint of the labor API.

The response contains an array of shift objects that contain the configuration information for each shift.

#### Example request to GET scheduled shifts

The following example **curl**command sends a `GET`request to the `/labor/v1/shifts`endpoint.

**Example 7.5. Example request to GET all scheduled shifts for a restaurant**

```
curl -X GET \
-H "Authorization: Bearer eyJzI1NiJ9hbGciOiJSU.eyJhd9yaXR5Ij
oiQ1JVTkNIVElNRSIsInJzR3VpZCI6IjE4YzQ5YWJlLWFlODItNGFlYy04ND
M1LWJhYTRjMjVlYTY2MiIsInNjb3BlIjpbImxWQiOlsidG9hc3QiXSwibmFt
aW5nQXV0aGhYm9yIiwib3JkZXJzIiwidXNlcm1nbXQiXSwiZXhwIjoxNDg0M
zg5ODUwLCJqdGkiOiJlMDYzZjJkMy1jNGYyLTRiZjItODJmNi01MTg1NWMzZ
DAxM2YiLCJjbGllbnRfaWQiOiJjcnVuY2h0aW1lIn0.X1_0y9Hzj5F9gdOw2
o6VSYTyZwooAJiFMDmNakbZrtiUdYwLzuLwLpCMQzX5pKYtOqDUz_cetGJL3
txKL1L-K2j1Enoq8An8hEM6e8J0KdAiwrYFO3W3CmWedaoz95K9ghNZVCs28
Td2Sp3Ix3fObxbrvanocx9_OT8S9uM8hdSXmBI_ykTWvOVgK4hO24V3DJy4b
9bz1FtgOvrClhELxCe8dJy7jiwAR60xczlCF5rna98RMLN6zY4ffjmljKFZ6
QV0KkVppWjEiJn7oFHiIylCX1sSg7sddrGatj0xJzts3GJ8u8_lryUNHaEvJ
dWq4Yzwo007AMgxjH9d241Y-g" \
-H "Toast-Restaurant-External-ID: 4622e7a9-b4be-3fef-9220-b3dad273e0b4" \[(1)](apiDevGuide-apiEmployeeInformationOmitChunkFromSearchIndex.html#d1e18370A00B97-C8C8-4406-B6D6-20C7B9566878-co)
-o my-shifts-get-request-response-data.json \[(2)](apiDevGuide-apiEmployeeInformationOmitChunkFromSearchIndex.html#d1e18570A00B97-C8C8-4406-B6D6-20C7B9566878-co)
"https://*`[toast-api-hostname]`*/labor/v1/shifts?startDate=[(3)](apiDevGuide-apiEmployeeInformationOmitChunkFromSearchIndex.html#d1e18770A00B97-C8C8-4406-B6D6-20C7B9566878-co)
2016-12-01T01:00:00.000-0000&endDate=2016-12-30T01:00:00.000-0000"
```



(1) Specify the GUID of the restaurant that you want to getshifts for. This must be an individual restaurant, not the GUID for a restaurant group.

(2) This example uses a JSON parsing utility to select the shifts for one employee. The utility reads the JSON response data for this request from the output file specified here.

(3) Specify the start and end dates of the time period you want to GETshifts for. You can select up to 30 days.

  
#### Example response

The following example shows the response for a `GET`request to the `/labor/v1/shifts`resource.

**Example 7.6. Example response to a request to GET restaurant shifts**

```
[
  {[(1)](apiDevGuide-apiEmployeeInformationOmitChunkFromSearchIndex.html#d1e20570A00B97-C8C8-4406-B6D6-20C7B9566878-co)
    "guid": "dbace5cb-390a-4242-a536-ca8a87393873",
    "entityType": "Shift",
    "externalId": null,
    "outDate": "2016-12-13T13:00:00.000+0000",
    "createdDate": "2016-12-22T01:56:34.004+0000",
    "deleted": false,
    "deletedDate": null,
    "employeeReference": {
      "guid": "c2ecd57f-fc91-47ee-a30d-622c7726bf54",[(2)](apiDevGuide-apiEmployeeInformationOmitChunkFromSearchIndex.html#d1e20770A00B97-C8C8-4406-B6D6-20C7B9566878-co)
      "entityType": "RestaurantUser",
      "externalId": null
    },
    "modifiedDate": "2016-12-22T01:56:34.004+0000",
    "inDate": "2016-12-13T06:00:00.000+0000",
    "jobReference": {
      "guid": "b9a91677-b948-4860-989c-4107b8c31ab3",
      "entityType": "RestaurantJob",
      "externalId": null
    }
  },
  {
    "guid": "76830753-0837-4388-ae45-89a1e8055d28",
    "entityType": "Shift",
    "externalId": null,
    "outDate": "2016-12-12T13:00:00.000+0000",
    "createdDate": "2016-12-22T01:56:11.721+0000",
    "deleted": false,
    "deletedDate": null,
    "employeeReference": {
      "guid": "c2ecd57f-fc91-47ee-a30d-622c7726bf54",[(3)](apiDevGuide-apiEmployeeInformationOmitChunkFromSearchIndex.html#d1e20970A00B97-C8C8-4406-B6D6-20C7B9566878-co)
      "entityType": "RestaurantUser",
      "externalId": null
    },
    "modifiedDate": "2016-12-22T01:56:11.721+0000",
    "inDate": "2016-12-12T06:00:00.000+0000",
    "jobReference": {
      "guid": "b9a91677-b948-4860-989c-4107b8c31ab3",
      "entityType": "RestaurantJob",
      "externalId": null
    }
  },
  {
    "guid": "a7b61a4c-dd48-497c-8f52-2a6a7db89c88",
    "entityType": "Shift",
    "externalId": null,
    "outDate": "2016-12-11T13:00:00.000+0000",
    "createdDate": "2016-12-22T01:25:04.135+0000",
    "deleted": false,
    "deletedDate": null,
    "employeeReference": {
      "guid": "f438e387-660a-4a43-8478-947414ab08af",[(4)](apiDevGuide-apiEmployeeInformationOmitChunkFromSearchIndex.html#d1e21170A00B97-C8C8-4406-B6D6-20C7B9566878-co)
      "entityType": "RestaurantUser",
      "externalId": null
    },
    "modifiedDate": "2016-12-22T01:25:04.135+0000",
    "inDate": "2016-12-11T06:00:00.000+0000",
    "jobReference": {
      "guid": "a5eec1c0-1143-4408-bb6b-3d4b28a594a3",
      "entityType": "RestaurantJob",
      "externalId": null
    }
  }
]
```



(1) The GETrequest returns an array of shift objects. Each object contains information about a shift.

(2) The employeeReferencevalue identifies the employee who is assigned to the shift.

(3) This shift is assigned to the same employee as the first shift in the array.

(4) This shift is assigned to a different employee.

  
#### Example jq utility command to select shifts for a specific employee

The following example **jq**command selects the shift objects for a specific employee from the array of shift objects in the response from `/labor/v1/shifts`.

For more information about the **jq**utility, see the [jq web site](https://stedolan.github.io/jq/).

**Example 7.7. jq utility command to select shifts for one employee**

```
jq \
'.[] | select(.employeeReference.guid=="c2ecd57f-fc91-47ee-a30d-622c7726bf54")' \[(1)](apiDevGuide-apiEmployeeInformationOmitChunkFromSearchIndex.html#d1e272638D8AE5-CF5A-4163-8DD0-CE1013C011AD-co)
my-shifts-get-request-response-data.json[(2)](apiDevGuide-apiEmployeeInformationOmitChunkFromSearchIndex.html#d1e274638D8AE5-CF5A-4163-8DD0-CE1013C011AD-co)
```



(1) This jq command syntax selects the JSON array members that have a specific employee GUID in the employeeReference.guidvalue for the shift.

(2) In this example, the jq utility is reading JSON from the output file of the curl command that made the initial GET request to the shifts resource. See Example 7.5, “Example request to GET all scheduled shifts for a restaurant” .

  
