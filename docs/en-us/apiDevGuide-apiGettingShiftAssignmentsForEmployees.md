---
title: "Getting shift assignments for employees"
id: apiGettingShiftAssignmentsForEmployees
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-portalApiGettingEmployeeInformationOmitChunkFromSearchIndex.md
parentSectionTitle: "Getting employee information"
previousSectionFile: apiDevGuide-apiGettingTimeEntriesForEmployees.md
previousSectionTitle: "Getting time entries for employees"
nextSectionFile: apiDevGuide-apiWorkingWithEmployeesOmitChunkFromSearchIndex.md
nextSectionTitle: "Updating employee information"
externalReferences: [https://stedolan.github.io/jq/]
excerpt: "To get information about the shifts that are scheduled for employees of a restaurant, send a GET request to the /labor/v1/shifts endpoint of the labor API."
procedures: 0
codeExamples: 0
---

To get information about the shifts that are scheduled for employees of a restaurant, send a `GET` request to the `/labor/v1/shifts` endpoint of the labor API.

The response contains an array of shift objects that contain the configuration information for each shift.

## Example request to GET scheduled shifts

The following example **curl** command sends a `GET` request to the `/labor/v1/shifts` endpoint.

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
-H "Toast-Restaurant-External-ID: 4622e7a9-b4be-3fef-9220-b3dad273e0b4" \
-o my-shifts-get-request-response-data.json \
"https://`[toast-api-hostname]`/labor/v1/shifts?startDate=
2016-12-01T01:00:00.000-0000&endDate=2016-12-30T01:00:00.000-0000"
```



(1) Specify the GUID of the restaurant that you want to get shifts for. This must be an individual restaurant, not the GUID for a restaurant group.

(2) This example uses a JSON parsing utility to select the shifts for one employee. The utility reads the JSON response data for this request from the output file specified here.

(3) Specify the start and end dates of the time period you want to GET shifts for. You can select up to 30 days.

  
## Example response

The following example shows the response for a `GET`request to the `/labor/v1/shifts` resource.

**Example 7.6. Example response to a request to GET restaurant shifts**


```
[
  {
    "guid": "dbace5cb-390a-4242-a536-ca8a87393873",
    "entityType": "Shift",
    "externalId": null,
    "outDate": "2016-12-13T13:00:00.000+0000",
    "createdDate": "2016-12-22T01:56:34.004+0000",
    "deleted": false,
    "deletedDate": null,
    "employeeReference": {
      "guid": "c2ecd57f-fc91-47ee-a30d-622c7726bf54",
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
      "guid": "c2ecd57f-fc91-47ee-a30d-622c7726bf54",
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
      "guid": "f438e387-660a-4a43-8478-947414ab08af",
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



(1) The GET request returns an array of shift objects. Each object contains information about a shift.

(2) The employeeReference value identifies the employee who is assigned to the shift.

(3) This shift is assigned to the same employee as the first shift in the array.

(4) This shift is assigned to a different employee.

  
## Example jq utility command to select shifts for a specific employee

The following example **jq** command selects the shift objects for a specific employee from the array of shift objects in the response from `/labor/v1/shifts` .

For more information about the **jq** utility, see the [jq web site](https://stedolan.github.io/jq/).

**Example 7.7. jq utility command to select shifts for one employee**


```
jq \
'.[] | select(.employeeReference.guid=="c2ecd57f-fc91-47ee-a30d-622c7726bf54")' \
my-shifts-get-request-response-data.json
```



(1) This jq command syntax selects the JSON array members that have a specific employee GUID in the employeeReference.guid value for the shift.

(2) In this example, the jq utility is reading JSON from the output file of the curlcommand that made the initial GET request to the shifts resource. See Example 7.5, “Example request to GET all scheduled shifts for a restaurant”.

  
