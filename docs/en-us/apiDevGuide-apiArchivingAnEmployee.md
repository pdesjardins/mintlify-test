---
title: "Archiving an employee"
id: apiArchivingAnEmployee
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiWorkingWithEmployeesOmitChunkFromSearchIndex.md
parentSectionTitle: "Updating employee information"
previousSectionFile: apiDevGuide-apiAddingAShiftAndAssigningIt.md
previousSectionTitle: "Adding a shift and assigning it to an employee"
nextSectionFile: apiDevGuide-apiUnarchivingAnEmployee.md
nextSectionTitle: "Unarchiving an employee"
externalReferences: [https://doc.toasttab.com/openapi/labor/tag/Data-definitions/schema/Employee/]
excerpt: "To archive an employee, send a DELETE..."
keywords: ["/labor/v1/employees/{employeeId}", "deletedDate", "Employee"]
procedures: 0
codeExamples: 0
---

To archive an employee, send a `DELETE`request to the `/labor/v1/employees/{employeeId}` endpoint of the labor API. Include the Toast platform identifier of the employee as a path parameter in the request.

This operation updates the employee in a way that indicates the employee is inactive and cannot access the Toast POS or other parts of the Toast platform. The Toast platform does not delete information about employees when you archive them, and you can [unarchive an employee later, if you need to](apiDevGuide-apiUnarchivingAnEmployee).



> **Note**
> 
> The internal representation of the archived state uses the term "deleted" and the labor API includes object value names such as `deleted` and `deletedDate`. The Toast platform *does not delete* employee information when you archive an employee.


When an employee is archived:

- The employee cannot sign into the Toast POS, sign into Toast Web, or open new time entries.


- The `deleted` value in the `Employee`object for the employee is set to `true`.


- The employee's information remains available in Toast platform reports.



## Example request to archive an employee

The following example **curl** command sends a `DELETE` request to archive an employee.

**Example 7.14. Example request to archive an employee**


```
curl -X DELETE \
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
https://`[toast-api-hostname]`/labor/v1/employees/`b7946411-7d45-4beb-9bfc-0ec731da7b45`
```



    <tr>
      <td>[(1)](#co-d1e132768FECD0D-59E6-4C90-91D2-B1AB1B54B400)</td>
      <td>Include the Toast platform identifier for the employee in the path parameter of the request.</td>
    </tr>
  
## Example response to archiving an employee

The following example shows the response for a `DELETE` request to archive an employee. For information about the values in this `Employee` object, see [the API reference documentation](https://doc.toasttab.com/openapi/labor/tag/Data-definitions/schema/Employee/).

**Example 7.15. Example response to a request to archive an employee**


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
    "deleted": true,
    "deletedDate": "2025-06-13T14:34:04.632+0000",
    "jobReferences": [],
    "modifiedDate": "2025-06-13T14:34:04.632+0000",
    "externalEmployeeId": null,
    "email": "jblajoie8650087951@example.com"
}
```



    <tr>
      <td>[(1)](#co-d1e1337B9ABC104-B7F3-4146-920F-E773D7BDABD9)</td>
      <td>When you archive an employee, the `deleted`value is set to `true`.</td>
    </tr>
    <tr>
      <td>[(2)](#co-d1e1339B9ABC104-B7F3-4146-920F-E773D7BDABD9)</td>
      <td>The `deletedDate` value indicates the date and time you archived the employee.</td>
    </tr>
  
