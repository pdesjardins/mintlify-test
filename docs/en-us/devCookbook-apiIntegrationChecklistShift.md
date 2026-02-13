---
title: "Building a shift scheduling integration"
id: apiIntegrationChecklistShift
type: section
documentId: devCookbook
parentSectionFile: devCookbook-cookbookEmployeesOmitChunkFromSearchIndex.md
parentSectionTitle: "Employees"
previousSectionFile: devCookbook-apiIntegrationChecklistEmployee.md
previousSectionTitle: "Building an employee management integration"
nextSectionFile: devCookbook-cookbookGiftCardsOmitChunkFromSearchIndex.md
nextSectionTitle: "Gift cards"
externalReferences: [https://central.toasttab.com/s/article/Enforcing-Scheduling-Time-Clock-Rules-with-Integration-Partners-1492745815961, https://central.toasttab.com/s/article/Adding-and-Editing-Employees-and-Wages, https://doc.toasttab.com/openapi/labor/overview/]
excerpt: "Follow the steps below to build a shift scheduling integration with the Toast platform."
procedures: 0
codeExamples: 0
---

Follow the steps below to build a shift scheduling integration with
  the Toast platform.

This type of integration allows restaurants to use [clock-in
  enforcement](https://central.toasttab.com/s/article/Enforcing-Scheduling-Time-Clock-Rules-with-Integration-Partners-1492745815961) functionality to ensure adequate staffing each day. If
  you want to build additional labor reporting functionality, see [Building labor reports](devCookbook-apiIntegrationChecklistPayroll).

## Required scopes

To follow these instructions, you must have the following [scopes](apiDevGuide-apiScopes):

- `labor.employees:read`


- `labor:read`


- `labor.shifts:write`


- `restaurants:read`



## Setup

### Complete initial integration setup

Review and implement the instructions in [How to build a Toast integration](devCookbook-apiIntegrationChecklistGeneral).

## Restaurant information management

### Review employee and job structure

Employees have permissions based on their assigned job(s).
      Scheduled shifts must specify an employee and a job. See [this
      Toast Central article](https://central.toasttab.com/s/article/Adding-and-Editing-Employees-and-Wages) for more information about employee
      setup.

If you plan to maintain employee information in your platform and
      submit this information to Toast, see [Building an employee management integration](devCookbook-apiIntegrationChecklistEmployee).

### Build initial employee and job load

If a restaurant begins using your integration after they are
      already live on the Toast platform, you will need to map the existing
      employees and jobs in the Toast platform to employees and jobs in your
      service.

Consider doing an [initial employee load](apiDevGuide-api_get_all_employees) when a
      restaurant first connects to your platform. You can match employees
      based on identifying information such as names and email addresses. If
      you will use the `externalEmployeeId` field, you can also use
      this field for mapping employees in the Toast platform to employees in
      your service.

Use the `/jobs` endpoint of the labor API to load
      initial job information. See [the Labor
      API](https://doc.toasttab.com/openapi/labor/overview/) for the jobs endpoint specification.

### Sync employee and job updates over time

If you attempt to submit a shift that contains an archived
      employee or job, or that contains an incorrect combination of an
      employee and job, the Toast API rejects the submission with a 400 HTTP
      response status code.

It is critical that you retrieve employee and shift information
      from the Toast platform on a recurring basis, for example once per day,
      to ensure that users are able to submit shifts that contain correct and
      current information.

### Retrieve restaurant hours

Use the `Schedule` object in the [restaurants
      API](apiDevGuide-apiRestaurantInformation) to retrieve a restaurant location's opening and closing
      hours. Use these hours when determining when a day's shifts should begin
      and end.

Consider adding configuration in your service that allows
      restaurant administrators to decide how long before opening the first
      shift must begin and how long after close the last shift must
      end.

## Development

### Build shift submission functionality

Build functionality that lets restaurant administrators create a
      scheduled shift in your service and submit this shift to the Toast
      platform.

See [Adding a shift and assigning it to an employee](apiDevGuide-apiAddingAShiftAndAssigningIt) for more information.

### Build shift update and cancellation functionality

After building functionality for initial shift submission, build
      and test functionality in which users can update and cancel existing
      shifts.

When a user wants to update an existing shift, submit a
      `PUT` request to the `/shifts` endpoint of the
      labor API. When a user wants to cancel their shift, use the
      `DELETE` method.

## Preventing errors

### Prevent concurrent updates

If you attempt to make two updates to the same shift at the same
      time (such as updating the start time through one `PUT`
      request and the end time in a different `PUT` request), one
      of the requests may receive a 400 HTTP response status code, and the
      update will not be reflected in the Toast platform.

To avoid this problem, either batch the changes to the shift into
      a single request, or wait for a response from the Toast API between
      changes to a single shift.

### Prevent creating duplicate shifts

If you attempt to create a shift that has the same start time, end
      time, employee, and job as an existing shift, you will receive a 400
      HTTP response status code.

Your service should track the shifts you have already created so
      you do not receive errors by attempting to create duplicate
      shifts.

### Prevent deleting shifts after the employee has clocked in

If an employee is clocked into a shift, you will receive a 400
      HTTP response status code if you attempt to delete the shift.

To evaluate whether an employee has clocked into their shift,
      retrieve [time entries](apiDevGuide-apiGettingTimeEntriesForEmployees) at
      this location and look for the shift's GUID in the
      `shiftReference` value. If there is a time entry that
      contains this shift in the `shiftReference`, the employee has
      clocked in.

Your integration should prevent users from attempting to delete
      shifts that employees have clocked into or display a user-friendly error
      message when somebody makes this shift deletion attempt.

