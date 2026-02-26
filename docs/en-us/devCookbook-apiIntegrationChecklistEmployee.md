---
title: "Building an employee management integration"
id: apiIntegrationChecklistEmployee
type: section
documentId: devCookbook
parentSectionFile: devCookbook-cookbookEmployeesOmitChunkFromSearchIndex.md
parentSectionTitle: "Employees"
previousSectionFile: devCookbook-cookbookEmployeesOmitChunkFromSearchIndex.md
previousSectionTitle: "Employees"
nextSectionFile: devCookbook-apiIntegrationChecklistShift.md
nextSectionTitle: "Building a shift scheduling integration"
externalReferences: [https://doc.toasttab.com/openapi/labor/overview/, https://central.toasttab.com/s/article/Adding-and-Editing-Employees-and-Wages]
excerpt: "Follow the steps below to build an employee management integration with the Toast platform."
procedures: 0
codeExamples: 0
---

Follow the steps below to build an employee management integration with the Toast platform.

This integration allows employee information to flow seamlessly between your system and the Toast platform. If you want to build additional labor reporting functionality, see [Building labor reports](docs/en-us/devCookbook-apiIntegrationChecklistPayroll).

## Required scopes

To follow these instructions, you must have the following [scopes](docs/en-us/apiDevGuide-apiScopes):

- `labor.employees:read`


- `labor:read`


- `labor.employees:write`



## Setup

### Complete initial integration setup

Review and implement the instructions in [How to build a Toast integration](docs/en-us/devCookbook-apiIntegrationChecklistGeneral).

## Functionality planning

### Decide how you will integrate with employees in the Toast platform

The labor API allows integration partners to create new employees, delete employees, and update existing employees in the Toast platform. Before you begin your integration development, decide which of these operations you will support.

Review the [labor API specification](https://doc.toasttab.com/openapi/labor/overview/) when considering which employee fields you will create and update. The labor API supports updating existing employees’ jobs, wage overrides, names, external IDs, and passcodes.

### Review employee and job structure

Employees in the Toast platform receive permissions based on their assigned jobs. Jobs have default wages, though a restaurant administrator can choose to override a particular employee's wage. Restaurant administrators can also modify employees’ permissions in the Toast platform after your integration submits the employee information. See [this Toast Central article](https://central.toasttab.com/s/article/Adding-and-Editing-Employees-and-Wages) for more information about editing employees in the Toast platform.

### Decide how you will use external employee identifiers

The `Employee` object contains an `externalEmployeeId` value that you can use to map employees in your system to employees in the Toast platform. Consider using this field to make it easier for restaurant administrators to understand this mapping of employees between the two systems.

You should not use the `externalEmployeeId` field for sensitive information such as Social Security numbers. This field is for general employee identification and mapping.

### Decide how you will map existing employees and jobs in Toast to employees in your system

If a restaurant begins to use your integration after they are already live on the Toast platform, you need to map the existing employees and jobs in the Toast platform to employees and jobs in your system.

Consider loading [initial employee information](docs/en-us/apiDevGuide-api_get_all_employees)when a restaurant first connects to your platform. You can match employees based on identifying information such as names and email addresses. If you will use the `externalEmployeeId` field, you can also use this field to map employees in the Toast platform to employees in your system.

Use the `/jobs` endpoint of the labor API to load initial job information. See [the labor API information](https://doc.toasttab.com/openapi/labor/overview/) for the jobs endpoint specification.

### Plan audit trail functionality

Given the sensitivity of employee information, it is important for restaurants to understand the employee updates that your system generated and why these employee updates occurred.

Before you build new functionality, consider the audit trail information you will expose to restaurants so that they understand how employee updates in your system affect employee information in the Toast platform.

## Development

### Build and test employee creation and updates

Build functionality in which restaurant administrators can create an employee in your system and your integration submits this employee's information to Toast. See [Adding an employee](docs/en-us/apiDevGuide-apiAddingAnEmployee) for more information. When applicable, assign jobs, wage overrides, and an `externalEmployeeId`.

If the employee will log into a point-of-sale device, include a `passcode` on the `Employee` object. If you do not include a `passcode`, the employee can log into Toast Web, but cannot log into a Toast POS device unless an administrator updates their permissions in the Toast platform.

After you build the initial employee creation functionality, build and test the employee update and deletion functionality if your integration supports those functions.

### Build initial employee and job load

Build an initial employee and job load based on the functionality you planned earlier.

Test that employees and jobs in the Toast platform match employees and jobs in your system in the way that you expect.

### Create audit trail report

Your integration should include an audit trail of the updates in your system that prompted employee updates in the Toast platform.

It is important for restaurant administrators to understand the updates in your system that triggered corresponding updates in the Toast platform, so that they do not need to contact your support team or Toast's support team to understand why an employee update occurred.

## Preventing errors

### Prevent concurrent updates

If you attempt to make multiple updates to the same employee at the same time, one of the requests may receive an error and the Toast platform will not reflect the update. For example, you cannot simultaneously update the first name of an employee through one `PUT` request and the last name of an employee in a different `PUT` request.

To avoid this error, it is best to either batch the changes to a single employee into a single request, or wait for a response from the Toast API between changes to a single employee.

### Prevent deleting employees who are clocked in

If an employee is clocked in, attempting to delete the employee returns a 400 HTTP response status code.

To prevent this problem, send a `GET` request to the `/timeEntries` endpoint of the labor API to see if there are any time entries for this employee that have a populated `inDate` and a null `outDate`.

In this situation, your integration should either prevent restaurant administrators from deleting employees who are clocked in or display a user-friendly error message.

### Prevent creating duplicate employees

Employee email addresses are the primary key that denote employee uniqueness.

If you attempt to create an employee whose email address matches that of another employee at the same restaurant location, you receive a 400 HTTP response status code.

You need to track the employee email addresses that already exist at a location in the Toast platform so that you do not create duplicate employees.

### Passcode management

Passcodes must be unique among all employees at a single restaurant location. They also must must also contain 1 to 8 numeric characters.

If you attempt to create or update an employee with the same passcode as another employee at the same location, or you submit a passcode that is anything other than 1-8 numeric characters, the labor API returns a 400 HTTP response status code.

### Employee names

Employee names and external identifiers cannot contain any of the following special characters: `({}\<\>$=\;%)`.

Ensure that your platform does not allow employee names to contain any of these characters, so that you do not submit these characters in the `firstName`, `lastName`, or `externalEmployeeId` values.

## Syncing updates

### Sync employee updates over time

Toast platform restaurant administrators may update employee information directly from Toast Web. You should periodically retrieve information from the `/employees`endpoint of the labor API to sync any updates made in the Toast platform.

If updates from the Toast platform differ from updates in your system, your system should ask restaurant administrators to determine whether the Toast platform or your system is correct.

