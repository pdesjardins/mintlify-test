---
title: "Getting all employees of a restaurant"
id: api-get-all-employees
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-portalApiGettingEmployeeInformationOmitChunkFromSearchIndex.md
parentSectionTitle: "Getting employee information"
previousSectionFile: apiDevGuide-portalApiGettingEmployeeInformationOmitChunkFromSearchIndex.md
previousSectionTitle: "Getting employee information"
nextSectionFile: apiDevGuide-apiGettingTimeEntriesForEmployees.md
nextSectionTitle: "Getting time entries for employees"
excerpt: "To get information about the employees of a restaurant, send a GET request to the /labor/v1/employees endpoint of the labor API."
keywords: [Employee]
procedures: 0
codeExamples: 0
---

### Getting all employees of a restaurant

To get information about the employees of a restaurant, send a `GET` request to the `/labor/v1/employees` endpoint of the labor API.

The request returns an array of `Employee` objects that contain the configuration information for each employee.

#### Example request for information about all employees

The following example **curl** command sends a `GET` request to the `/labor/v1/employees` endpoint.

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
-H "Toast-Restaurant-External-ID: 4622e7a9-b4be-3fef-9220-b3dad273e0b4" \
https://`[toast-api-hostname]`/labor/v1/employees
```



 Specify the GUID of the restaurant that you want to GET employees for. This must be an individual restaurant, not the GUID for a restaurant group.

  
#### Example response

The following example shows the response for a `GET`request to the `/labor/v1/employees` resource.

**Example 7.2. Example response to a request to GET restaurant employees**

```
[
  \{
    "guid": "b7946411-7d45-4beb-9bfc-0ec731da7b45",
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
      \{
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
  \{
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
      \{
        "guid": "a5eec1c0-1143-4408-bb6b-3d4b28a594a3",
        "entityType": "RestaurantJob",
        "externalId": null
      \}
    ],
    "modifiedDate": "2016-11-23T15:54:23.635+0000",
    "disabled": false,
    "externalEmployeeId": "",
    "email": "couellet@arestaurant.com"
  \}
]

```



(1) The GET request returns an array of employee objects. Each object contains information about an employee.

(2) The guid value contains the unique Toast platform identifier for the employee.

(3) Each object contains information for a different employee.

  
