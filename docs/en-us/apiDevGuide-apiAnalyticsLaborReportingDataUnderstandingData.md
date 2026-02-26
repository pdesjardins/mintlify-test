---
title: "Understanding the labor reporting data"
id: apiAnalyticsLaborReportingDataUnderstandingData
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiAnalyticsLaborReportingDataOmitChunkFromSearchIndex.md
parentSectionTitle: "Labor reporting data"
previousSectionFile: apiDevGuide-apiAnalyticsLaborReportingDataAggregation.md
previousSectionTitle: "Aggregating the labor reporting data"
nextSectionFile: apiDevGuide-apiAnalyticsMenuReportingDataOmitChunkFromSearchIndex.md
nextSectionTitle: "Menu reporting data"
excerpt: "Labor reporting data contains consistent values that appear for each active restaurant and by business date. Optionally, you can choose to aggregate the labor reporting data by either employee or..."
keywords: ["understanding", "labor", "reporting", "data", "restaurantGuid", "businessDate", "YYYYMMDD", "regularHours", "overtimeHours", "totalHours"]
procedures: 0
codeExamples: 0
---

Labor reporting data contains consistent values that appear for each active restaurant and by business date. Optionally, you can choose to aggregate the labor reporting data by either employee or job. For more information, see [Aggregating the labor reporting data](apiDevGuide-apiAnalyticsLaborReportingDataAggregation). For information about retrieving inactive restaurant data, see [Viewing inactive restaurant data](apiDevGuide-apiAnalyticsInactiveRestaurantData).

The restaurants included in the labor reporting data can be limited by adding the GUIDs of restaurants to either include only or exclude only. For an example that chooses specific restaurants, see [Creating a request for labor reporting data](apiDevGuide-apiAnalyticsLaborReportingDataCreateRequest).

The following table specifies the returned set of values in the labor reporting data. The values are listed in the order they appear.


<table>
  <thead>
    <tr>
      <th>Value name</th>
      <th>Definition</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>`restaurantGuid`</td>
      <td>The unique identifier assigned to the restaurant by the Toast platform.</td>
    </tr>
    <tr>
      <td>`businessDate`</td>
      <td>The calendar date of the associated order data, in `YYYYMMDD` format.</td>
    </tr>
    <tr>
      <td>`regularHours`</td>
      <td>The total regular hours logged between clock-in and clock-out for employees with hourly jobs. This does not include overtime hours.</td>
    </tr>
    <tr>
      <td>`overtimeHours`</td>
      <td>The total overtime hours logged between clock-in and clock-out for employees with hourly jobs. This only includes overtime hours.</td>
    </tr>
    <tr>
      <td>`totalHours`</td>
      <td>The total hours logged between clock-in and clock-out for employees with hourly jobs. This includes regular and overtime hours.</td>
    </tr>
    <tr>
      <td>`regularCost`</td>
      <td>The operation costs related to employees with hourly jobs from all regular hours, including all shifts.</td>
    </tr>
    <tr>
      <td>`overtimeCost`</td>
      <td>The operation costs related to employees with hourly jobs from all overtime hours, including all shifts.</td>
    </tr>
    <tr>
      <td>`totalCost`</td>
      <td>The operation costs related to employees with hourly jobs from all work hours, including all shifts.</td>
    </tr>
    <tr>
      <td>`netSalesAmount`</td>
      <td>The total sales, excluding tax, gratuity, tips, discounts, refunds, and deferred amounts. This property is only included when no `groupBy` value is specified.</td>
    </tr>
    <tr>
      <td>`grossSalesAmount`</td>
      <td>The total sales, including discounts and refunds. This property is only included when no `groupBy`value is specified.</td>
    </tr>
    <tr>
      <td>`netSalesPerEmployeeHour`</td>
      <td>The average of the location's total net sales for each hour clocked by an employee. This property is only included when no `groupBy` value is specified.</td>
    </tr>
    <tr>
      <td>`grossSalesPerEmployeeHour`</td>
      <td>The average of the location's total gross sales for each hour clocked by an employee. This property is only included when no `groupBy` value is specified.</td>
    </tr>
    <tr>
      <td>`totalCostPerNetSales`</td>
      <td>The ratio of employee operational costs compared to total net sales, expressed as a percentage.</td>
    </tr>
    <tr>
      <td>`totalCostPerGrossSales`</td>
      <td>The ratio of employee operational costs compared to gross sales, expressed as a percentage.</td>
    </tr>
    <tr>
      <td>`jobGuid`</td>
      <td>The identifier assigned by the Toast platform used to identify a job. This property is only included when the `groupBy` property uses the `JOB` value. If not aggregated by `JOB`, the value is `null`.</td>
    </tr>
    <tr>
      <td>`jobTitle`</td>
      <td>The job name. This property only appears when the request for labor data includes the `groupBy`property with value `JOB`. If not aggregated by `JOB`, the value is `null`.</td>
    </tr>
    <tr>
      <td>`jobCode`</td>
      <td>A reference identifier for the job. This is an optional field entered when the job is created. For example, it can be used to match Toast platform jobs to jobs configured in external labor management systems. This property only appears when the request for labor data includes the `groupBy` property with value `JOB`. If not aggregated by `JOB`, the value is `null`.</td>
    </tr>
    <tr>
      <td>`employeeGuid`</td>
      <td>The identifier assigned by the Toast platform used to identify an employee. This property only appears when the request for labor data includes the `groupBy`property with value `EMPLOYEE`. If not aggregated by `EMPLOYEE`, the value is `null`.</td>
    </tr>
    <tr>
      <td>`employeeFirstName`</td>
      <td>The employee's first name. This property is populated when the request for labor data includes the `groupBy` property with value `EMPLOYEE`. If not aggregated by `EMPLOYEE`, the value is `null`.</td>
    </tr>
    <tr>
      <td>`employeeLastName`</td>
      <td>The employee's last name. This property is populated when the request for labor data includes the `groupBy` property with value `EMPLOYEE`. If not aggregated by `EMPLOYEE`, the value is `null`.</td>
    </tr>
    <tr>
      <td>`employeeChosenName`</td>
      <td>The employee's chosen name. This property is populated when the request for labor data includes the `groupBy` property with value `EMPLOYEE`. If not aggregated by `EMPLOYEE`, the value is `null`.</td>
    </tr>
    <tr>
      <td>`restaurantName`</td>
      <td>The restaurant’s name.</td>
    </tr>
    <tr>
      <td>`restaurantLocationName`</td>
      <td>The restaurant’s location name.</td>
    </tr>
    <tr>
      <td>`restaurantLocationCode`</td>
      <td>The restaurant’s location code.</td>
    </tr>
  </tbody>
</table>

