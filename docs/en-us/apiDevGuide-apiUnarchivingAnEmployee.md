---
title: "Unarchiving an employee"
id: apiUnarchivingAnEmployee
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiWorkingWithEmployeesOmitChunkFromSearchIndex.md
parentSectionTitle: "Updating employee information"
previousSectionFile: apiDevGuide-apiArchivingAnEmployee.md
previousSectionTitle: "Archiving an employee"
nextSectionFile: apiDevGuide-portalApiGettingCashManagementEntriesOmitChunkFromSearchIndex.md
nextSectionTitle: "Chapter 8. Cash management"
excerpt: "To unarchive an employee, send a PUT request to the /labor/v1/employees/{employeeGuid}/unarchive endpoint of the labor API. Include the Toast platform identifier of the employee as a path parameter..."
keywords: ["/labor/v1/employees/{employeeGuid}/unarchive"]
procedures: 0
codeExamples: 0
---

To unarchive an employee, send a `PUT`request to the `/labor/v1/employees/{employeeGuid}/unarchive`endpoint of the labor API. Include the Toast platform identifier of the employee as a path parameter in the request.

When you unarchive an employee, that employee can sign into the Toast POS and also sign into Toast Web. The employee will have all the [jobs assigned](adminGuide-platformEmployeeJobs) to them before they were archived.

If an employee had a swipe card for signing into the Toast POS, the swipe card *is not* re-associated with the employee when you unarchive them.



> **Important**
> 
> If an employee has a different role when you unarchive them than they had when they were archived, you must evaluate the jobs that are assigned to the employee and whether that employee should continue to be able to sign into Toast Web. When you unarchive an employee, that employee keeps all jobs that were previously assigned and will be able to sign into Toast Web.


## Example request to unarchive an employee

The following example **curl** command sends a `PUT` request to unarchive an employee.

**Example 7.16. Example request to unarchive an employee**


```
curl -v -X PUT \
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
"https://`[toast-api-hostname]`/labor/v1/employees/`0a7ced2c-b782-4585-8f41-4bb1656c3f67`/unarchive"
```



    <tr>
      <td>[(1)](#co-d1e141338BF6586-9DC9-4F2D-B959-8942F3A9B4B3)</td>
      <td>Include the Toast platform identifier for the employee in the path parameter of the request.</td>
    </tr>
  
## Example response

The following example shows the response for a `PUT` request to unarchive an employee.

**Example 7.17. Example response from a request to unarchive an employee**


```
{
    "guid": "82965aae-7b53-448a-b7e5-e32039f01ff4",
    "entityType": "RestaurantUser",
    "externalId": null,
    "v2EmployeeGuid": "717ae0a8-7f01-43f6-9356-6ef955d81c19",
    "lastName": "Lajoie",
    "wageOverrides": [],
    "phoneNumberCountryCode": "+1",
    "firstName": "Jean-Baptiste",
    "chosenName": null,
    "createdDate": "2025-06-13T14:33:48.930+0000",
    "phoneNumber": null,
    "deleted": false,
    "deletedDate": null,
    "jobReferences": [],
    "modifiedDate": "2025-06-13T14:35:12.598+0000",
    "externalEmployeeId": null,
    "email": "jblajoie8650087951@example.com"
}
```



    <tr>
      <td>[(1)](#co-d1e1426B9ABC104-B7F3-4146-920F-E773D7BDABD9)</td>
      <td>When you unarchive an employee, the `deleted`value is set to `false`.</td>
    </tr>
    <tr>
      <td>[(2)](#co-d1e1428B9ABC104-B7F3-4146-920F-E773D7BDABD9)</td>
      <td>When you unarchive an employee, the `deletedDate` value is set to `null`.</td>
    </tr>
  
