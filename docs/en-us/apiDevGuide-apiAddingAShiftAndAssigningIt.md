---
title: "Adding a shift and assigning it to an employee"
id: apiAddingAShiftAndAssigningIt
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiWorkingWithEmployeesOmitChunkFromSearchIndex.md
parentSectionTitle: "Updating employee information"
previousSectionFile: apiDevGuide-apiWorkingWithEmployeesOmitChunkFromSearchIndex.md
previousSectionTitle: "Updating employee information"
nextSectionFile: apiDevGuide-apiArchivingAnEmployee.md
nextSectionTitle: "Archiving an employee"
excerpt: "To add a shift and assign it to a restaurant employee, send a POST request to the /labor/v1/shifts endpoint of the labor API."
procedures: 0
codeExamples: 0
---

### Adding a shift and assigning it to an employee

To add a shift and assign it to a restaurant employee, send a `POST` request to the `/labor/v1/shifts` endpoint of the labor API.

The response provides information about the shift, including the Toast platform GUID.

#### Example request to add a shift

The following example **curl** command sends a `POST` request to the `/labor/v1/shifts` endpoint.

**Example 7.11. Example request to add a shift and assign it to an employee**

```
curl -v -X POST \
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
-H "Toast-Restaurant-External-ID: 4622e7a9-b4be-3fef-9220-b3dad273e0b4" \[(1)](apiDevGuide-apiAddingAShiftAndAssigningIt.html#d1e4852BCF3ED8-080B-4C47-9C32-348D8EED99AD-co)
-H "Content-Type: application/json" \[(2)](apiDevGuide-apiAddingAShiftAndAssigningIt.html#d1e4872BCF3ED8-080B-4C47-9C32-348D8EED99AD-co)
-d @my-shift-information.json \[(3)](apiDevGuide-apiAddingAShiftAndAssigningIt.html#d1e4892BCF3ED8-080B-4C47-9C32-348D8EED99AD-co)
"https://`[toast-api-hostname]`/labor/v1/shifts"
```



(1) Specify the GUID of the restaurant to add the shift to. This must be an individual restaurant, not the GUID for a restaurant group.

(2) Specify the data type of the message body in the Content-Type header field. The value must be application/json.

(3) Include information about the new employee in the message body of the POST request. This example curl command sends message body data from the contents of a file.

  
#### Example shift details for the message body of the request to add a shift

The following example shows the message body data that provides information about the shift.

**Example 7.12. Example message body for a request to add a shift**

```
{
  "employeeReference": {
    "entityType": "RestaurantUser",
    "guid": "0a7ced2c-b782-4585-8f41-4bb1656c3f67"[(1)](apiDevGuide-apiAddingAShiftAndAssigningIt.html#d1e5042BCF3ED8-080B-4C47-9C32-348D8EED99AD-co)
  },
  "entityType": "Shift",[(2)](apiDevGuide-apiAddingAShiftAndAssigningIt.html#d1e5062BCF3ED8-080B-4C47-9C32-348D8EED99AD-co)
  "inDate": "2017-01-13T06:00:00.000+0000",[(3)](apiDevGuide-apiAddingAShiftAndAssigningIt.html#d1e5082BCF3ED8-080B-4C47-9C32-348D8EED99AD-co)
  "jobReference": {
    "entityType": "RestaurantJob",
    "guid": "a674499f-cddd-4b8b-a6b3-6d44147da330"[(4)](apiDevGuide-apiAddingAShiftAndAssigningIt.html#d1e5102BCF3ED8-080B-4C47-9C32-348D8EED99AD-co)
  },
  "outDate": "2017-01-13T13:00:00.000+0000"[(5)](apiDevGuide-apiAddingAShiftAndAssigningIt.html#d1e5122BCF3ED8-080B-4C47-9C32-348D8EED99AD-co)
}
```



(1) Specify the GUID of the employee who will work the shift.

(2) Specify the data type of the Toast platform input object. The value must be Shift.

(3) Specify the date and time that the shift begins.

(4) Specify the job for the shift in the jobReference value.

(5) Specify the date and time that the shift ends.

  
#### Example response

The following example shows the response for a `POST` request to the `/labor/v1/shifts` resource.

**Example 7.13. Example response from a request to add a shift**

```
{
  "guid": "08312056-c56f-4a10-a3c2-5660bf2b5143",[(1)](apiDevGuide-apiAddingAShiftAndAssigningIt.html#d1e5322BCF3ED8-080B-4C47-9C32-348D8EED99AD-co)
  "entityType": "Shift",
  "externalId": null,
  "outDate": "2017-01-13T13:00:00.000+0000",
  "createdDate": "2016-12-29T05:33:16.712+0000",
  "deleted": false,
  "deletedDate": null,
  "employeeReference": {
    "guid": "0a7ced2c-b782-4585-8f41-4bb1656c3f67",
    "entityType": "RestaurantUser",
    "externalId": null
  },
  "modifiedDate": "2016-12-29T05:33:16.712+0000",
  "inDate": "2017-01-13T06:00:00.000+0000",
  "jobReference": {
    "guid": "a674499f-cddd-4b8b-a6b3-6d44147da330",
    "entityType": "RestaurantJob",
    "externalId": null
  }
}
```



(1) The guid value contains the GUID that the Toast platform assigns to the shift.

  
