---
title: "Adding an employee"
id: apiAddingAnEmployee
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiWorkingWithEmployeesOmitChunkFromSearchIndex.md
parentSectionTitle: "Updating employee information"
previousSectionFile: apiDevGuide-apiWorkingWithEmployeesOmitChunkFromSearchIndex.md
previousSectionTitle: "Updating employee information"
nextSectionFile: apiDevGuide-apiAddingAShiftAndAssigningIt.md
nextSectionTitle: "Adding a shift and assigning it to an employee"
excerpt: "To add an employee to the restaurant, send a POST request to the /labor/v1/employees endpoint of the labor API ."
keywords: [firstName,lastName,externalEmployeeId]
procedures: 0
codeExamples: 0
---

### Adding an employee

To add an employee to the restaurant, send a `POST` request to the `/labor/v1/employees` endpoint of the labor API .

The response contains an object containing information about the employee, including the Toast platform GUID for the new employee.



> **Note**
> 
> The labor API rejects new or updated values for `firstName`, `lastName`, and `externalEmployeeId` that include the following special characters: `{}\<\>$=\;%`


#### Example request to add an employee

The following example **curl** command sends a `POST` request to the `/labor/v1/employees` resource.

**Example 7.8. Example request to add an employee to a restaurant**

```
curl -X POST \
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
-H "Content-Type: application/json" \
-d @my-new-employee-data.json \
https://`[toast-api-hostname]`/labor/v1/employees
```



(1) Specify the GUID of the restaurant that you want to add an employee to. This must be an individual restaurant, not the GUID for a restaurant group.

(2) Specify the data type of the message body in the Content-Type header field. The value must be application/json.

(3) Include information about the new employee in the message body of the POST request. This example curl command sends message body data from the contents of a file.

  
#### Example employee details for the request to add an employee

The following example shows the message body data that provides information about the new employee.

**Example 7.9. Example message content with information about a new employee**

```
{
  "entityType": "RestaurantUser", 
  "email": "jgauthier@example.com", 
  "firstName": "Josephine", 
  "chosenName": "Jo",
  "lastName": "Gauthier", 
  "externalId": "TPC-PARTNER:12345", 
  "externalEmployeeId": "1234567890", 
  "passcode": "12345",
  "jobReferences": [ 
    {
      "guid": "8d3bba92-10e4-4345-9ae6-ed94c09dc332",
      "entityType": "RestaurantJob"
    }
  ] 
}
```



(1) Specify the data type of the Toast platform input object. The value must be RestaurantUser.

(2) Specify an email address for the employee. Email addresses for employees must be unique. If you specify an email address that is in use by an employee, the request fails with an HTTP 400 (bad request) response.

(3) Specify the first name of the employee.

(4) Specify the last name of the employee.

(5) External identifier string that is prefixed by the naming authority. The externalId must be unique. If you specify an externalId that is not unique, the request fails with an HTTP 400 (bad request) response. For more information, see External identifiers.

(6) You can specify the initial Toast platform passcode number for the employee. This value is optional.

(7) You can specify the job for the new employee. This value is optional. To assign a job, you need the Toast platform GUID or the external identifier for the job.

  
#### Example response

The following example shows the response for a `POST` request to the `/labor/v1/employees` endpoint.

**Example 7.10. Example response for the add employee request**

```
{
  "guid": "e5c3a2f3-8aa2-4a66-b379-6c80b7277dc3",
  "entityType": "RestaurantUser",
  "externalId": null,
  "lastName": "Gauthier",
  "wageOverrides": [],
  "firstName": "Josephine",
  "chosenName": "Jo",
  "createdDate": "2019-10-02T13:11:22.824+0000",
  "deleted": false,
  "deletedDate": null,
  "jobReferences": [
    {
      "guid": "8d3bba92-10e4-4345-9ae6-ed94c09dc332",
      "entityType": "RestaurantJob",
      "externalId": null
    }
  ],
  "modifiedDate": "2019-10-02T13:11:22.824+0000",
  "disabled": null,
  "externalEmployeeId": null,
  "email": "jgauthier@example.com",
  "passcode": "12345"
}
```



(1) The guid value contains the GUID value that the Toast platform assigns to the new employee.

(2) If you assign a job to the new employee, the response will return the job. This is optional.

(3) If you assign an initial pass code to the new employee, the employee is able to log in to the Toast platform. This is optional.

  
