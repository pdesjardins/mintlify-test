---
title: "Building labor reports"
id: apiIntegrationChecklistPayroll
type: section
documentId: devCookbook
parentSectionFile: devCookbook-cookbookAnalyticsOmitChunkFromSearchIndex.md
parentSectionTitle: "Reports"
previousSectionFile: devCookbook-apiIntegrationChecklistTemplate.md
previousSectionTitle: "Building an Analytics integration"
nextSectionFile: devCookbook-apiIntegrationChecklistAccounting.md
nextSectionTitle: "Building a sales report"
externalReferences: [https://central.toasttab.com/s/article/Enforcing-Scheduling-Time-Clock-Rules-with-Integration-Partners-1492745815961, https://doc.toasttab.com/openapi/labor/overview/, https://central.toasttab.com/s/article/Tip-Withholding]
excerpt: "Use the instructions below to build labor reports using information from the Toast platform. This information will help when creating a payroll integration, predicting future staffing needs,..."
procedures: 0
codeExamples: 0
---

Use the instructions below to build labor reports using information from the Toast platform. This information will help when creating a payroll integration, predicting future staffing needs, identifying the most efficient employees, and more.

You are now ready to provide customers with detailed information related to labor costs and efficiency, providing restaurants with useful information to run their business.

## Required scopes

To follow these instructions, you must have the following [scopes](docs/en-us/apiDevGuide-apiScopes):

- `config:read`


- `labor.employees:read`


- `labor:read`


- `restaurants:read`


- `orders:read`



## Setup and planning

### Complete initial integration setup

Review and implement the instructions in [How to build a Toast integration](docs/en-us/devCookbook-apiIntegrationChecklistGeneral).

### Decide what information your reports will provide

Before you begin development, decide what reports you will build.

The steps below describe how to extract the following labor data:

- Hours worked per employee


- Overtime hours worked per employee


- Breaks taken


- Shift clock-in timeliness - Requires that the restaurant uses [clock-in enforcement](https://central.toasttab.com/s/article/Enforcing-Scheduling-Time-Clock-Rules-with-Integration-Partners-1492745815961) functionality


- Sales per employee


- Wages earned per employee - Does not include overtime wages


- Tips earned per employee



## Retrieving restaurant information

### Build initial employee and job load

If a restaurant begins to use your integration after they are already live on the Toast platform, you must map the existing employees and jobs in the Toast platform to employees and jobs in your service.

Consider doing an [initial employee load](docs/en-us/apiDevGuide-api_get_all_employees) when a restaurant first connects to your platform. You can match employees based on identifying information such as names and email addresses. If you will use the `externalEmployeeId` field, you can also use this field to map employees in the Toast platform to employees in your service.

Use the `/jobs` endpoint of the labor API to load initial job information. See [the labor API](https://doc.toasttab.com/openapi/labor/overview/) for the jobs endpoint specification. If your integration allows restaurants to create employees in your platform and submit this information to the Toast platform, see [Building an employee management integration](docs/en-us/devCookbook-apiIntegrationChecklistEmployee).

### Set up recurring retrieval of employees, jobs, and configuration information

Query the following endpoints at least once per location per day to ensure you maintain accurate labor information over time:

- The `/employees` and `/jobs` endpoints of the labor API


- The `/tipWithholding` endpoint of the configuration API if you report on tips earned per employee


- The `/breakTypes` endpoint of the configuration API if you report on breaks taken



### Set up recurring retrieval of transactional information

To report on labor information, you need to retrieve transactional information from restaurants at least once per day.

Use the following endpoints to retrieve transactional information:

- If you report on hours worked or breaks taken, retrieve yesterday's time entries using the `modifiedStartDate`and `modifiedEndDate` parameters of the `/timeEntries` endpoint of the labor API. See [Getting time entries for employees](docs/en-us/apiDevGuide-apiGettingTimeEntriesForEmployees) for more information.


- If you report on shift clock-in timeliness, retrieve yesterday's shifts using the `startDate` and `endDate` parameters of the `/shifts` endpoint of the labor API. See [Getting shift assignments for employees](docs/en-us/apiDevGuide-apiGettingShiftAssignmentsForEmployees) for more information.


- If you report on sales or tips per employee, retrieve yesterday's orders using the `startDate` and `endDate` parameters of the `/ordersBulk`endpoint of the orders API. See [Getting detailed information about multiple orders](docs/en-us/apiDevGuide-apiOrdersGetDetailedInfoAboutMultipleOrders) for more information.



### Determine closeout hour

The `closeoutHour` value in the `General`object returned by the [restaurants API](docs/en-us/apiDevGuide-apiRestaurantInformation) contains the restaurant's closeout hour.

The default closeout hour is 4:00 a.m. local time unless a Toast employee changes this setting. The `businessDate` value on time entries changes after the `closeoutHour`.

Consider [daylight savings time](docs/en-us/apiDevGuide-api_dates_and_timestamps#apiDaylightSavingsTime) when interacting with the closeout hour.

## Building report functionality

### Reporting on hours worked and wages earned

Use the `regularHours` and `overtimeHours`values on `TimeEntry` objects to determine how many regular and overtime hours an employee worked while they were clocked in.

To determine an hourly employee’s wages earned, multiply the `regularHours` and `hourlyWage` values from the `TimeEntry` object.

The labor API does not expose the overtime factor to determine overtime wages earned.

If `hourlyWage` is null, the time entry is associated with a salaried job.

### Reporting on breaks taken

Use the `breaks` value on `TimeEntry`objects to determine how much paid and unpaid break time an employee took while clocked in.

The `breakType` value on the time entry corresponds to a `BreakType` object in the configuration API.

### Reporting on shift clock-in timeliness

If the restaurant uses clock-in enforcement functionality, then the `shiftReference` on a `TimeEntry` object is populated with the GUID of the employee's scheduled shift.

If the employee clocked in outside of the restaurant's allowed clock-in window or the restaurant does not use clock-in enforcement functionality, the `shiftReference` on the time entry is null.

To compare the employee's scheduled shift time with their actual clock-in and clock-out times, compare the `inDate` and `outDate` values on the corresponding `TimeEntry`and `Shift` objects.

### Reporting on sales and tips per employee

The employee associated with an order is listed in the `server` value on an `Order` object in the orders API. To calculate an employee's sales and tips, sum the `amount` (for total sales) and `tipAmount` (for tips) on the payments associated with their orders.

If the `/tipWithholding` endpoint of the configuration API indicates that the restaurant uses [tip withholding](https://central.toasttab.com/s/article/Tip-Withholding) functionality, your reports should reflect the tip values that were withheld from the employee.

Toast support recommends using the orders API rather than the `cashSales`, `nonCashSales`, `declaredCashTips`, and `nonCashTips` values on the `TimeEntry` object to calculate an employee's sales and tips. The sales values on time entries may not reflect orders an employee handled outside of their shift, and time entry values will not update if a manager administratively adjusts the beginning or end time of a time entry.

To determine if a payment or tip was cash, credit, or another payment type, use the `type` value on the `Payment` object in the orders API.

### Additional reporting ideas

Consider using the labor information you retrieve from Toast APIs in the following ways:

- Predict how restaurants should plan future staffing. For example, if a particular day of the week or time of day tends to have a higher order volume, restaurants may want more team members to work during that time.


- Identify efficient employees as measured by sales or tips per hour worked and shift clock-in timeliness.


- Use sales, tips, hours worked, and breaks taken when building a payroll product.



