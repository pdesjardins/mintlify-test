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
      <td><code>restaurantGuid</code></td>
      <td>The unique identifier assigned to the restaurant by the Toast platform.</td>
    </tr>
    <tr>
      <td><code>businessDate</code></td>
      <td>The calendar date of the associated order data, in <code>YYYYMMDD</code> format.</td>
    </tr>
    <tr>
      <td><code>regularHours</code></td>
      <td>The total regular hours logged between clock-in and clock-out for employees with hourly jobs. This does not include overtime hours.</td>
    </tr>
    <tr>
      <td><code>overtimeHours</code></td>
      <td>The total overtime hours logged between clock-in and clock-out for employees with hourly jobs. This only includes overtime hours.</td>
    </tr>
    <tr>
      <td><code>totalHours</code></td>
      <td>The total hours logged between clock-in and clock-out for employees with hourly jobs. This includes regular and overtime hours.</td>
    </tr>
    <tr>
      <td><code>regularCost</code></td>
      <td>The operation costs related to employees with hourly jobs from all regular hours, including all shifts.</td>
    </tr>
    <tr>
      <td><code>overtimeCost</code></td>
      <td>The operation costs related to employees with hourly jobs from all overtime hours, including all shifts.</td>
    </tr>
    <tr>
      <td><code>totalCost</code></td>
      <td>The operation costs related to employees with hourly jobs from all work hours, including all shifts.</td>
    </tr>
    <tr>
      <td><code>netSalesAmount</code></td>
      <td>The total sales, excluding tax, gratuity, tips, discounts, refunds, and deferred amounts. This property is only included when no <code>groupBy</code> value is specified.</td>
    </tr>
    <tr>
      <td><code>grossSalesAmount</code></td>
      <td>The total sales, including discounts and refunds. This property is only included when no <code>groupBy</code> value is specified.</td>
    </tr>
    <tr>
      <td><code>netSalesPerEmployeeHour</code></td>
      <td>The average of the location's total net sales for each hour clocked by an employee. This property is only included when no <code>groupBy</code> value is specified.</td>
    </tr>
    <tr>
      <td><code>grossSalesPerEmployeeHour</code></td>
      <td>The average of the location's total gross sales for each hour clocked by an employee. This property is only included when no <code>groupBy</code> value is specified.</td>
    </tr>
    <tr>
      <td><code>totalCostPerNetSales</code></td>
      <td>The ratio of employee operational costs compared to total net sales, expressed as a percentage.</td>
    </tr>
    <tr>
      <td><code>totalCostPerGrossSales</code></td>
      <td>The ratio of employee operational costs compared to gross sales, expressed as a percentage.</td>
    </tr>
    <tr>
      <td><code>jobGuid</code></td>
      <td>The identifier assigned by the Toast platform used to identify a job. This property is only included when the <code>groupBy</code> property uses the <code>JOB</code> value. If not aggregated by <code>JOB</code>, the value is <code>null</code>.</td>
    </tr>
    <tr>
      <td><code>jobTitle</code></td>
      <td>The job name. This property only appears when the request for labor data includes the <code>groupBy</code> property with value <code>JOB</code>. If not aggregated by <code>JOB</code>, the value is <code>null</code>.</td>
    </tr>
    <tr>
      <td><code>jobCode</code></td>
      <td>A reference identifier for the job. This is an optional field entered when the job is created. For example, it can be used to match Toast platform jobs to jobs configured in external labor management systems. This property only appears when the request for labor data includes the <code>groupBy</code> property with value <code>JOB</code>. If not aggregated by <code>JOB</code>, the value is <code>null</code>.</td>
    </tr>
    <tr>
      <td><code>employeeGuid</code></td>
      <td>The identifier assigned by the Toast platform used to identify an employee. This property only appears when the request for labor data includes the <code>groupBy</code> property with value <code>EMPLOYEE</code>. If not aggregated by <code>EMPLOYEE</code>, the value is <code>null</code>.</td>
    </tr>
    <tr>
      <td><code>employeeFirstName</code></td>
      <td>The employee's first name. This property is populated when the request for labor data includes the <code>groupBy</code> property with value <code>EMPLOYEE</code>. If not aggregated by <code>EMPLOYEE</code>, the value is <code>null</code>.</td>
    </tr>
    <tr>
      <td><code>employeeLastName</code></td>
      <td>The employee's last name. This property is populated when the request for labor data includes the <code>groupBy</code> property with value <code>EMPLOYEE</code>. If not aggregated by <code>EMPLOYEE</code>, the value is <code>null</code>.</td>
    </tr>
    <tr>
      <td><code>employeeChosenName</code></td>
      <td>The employee's chosen name. This property is populated when the request for labor data includes the <code>groupBy</code> property with value <code>EMPLOYEE</code>. If not aggregated by <code>EMPLOYEE</code>, the value is <code>null</code>.</td>
    </tr>
    <tr>
      <td><code>restaurantName</code></td>
      <td>The restaurant’s name.</td>
    </tr>
    <tr>
      <td><code>restaurantLocationName</code></td>
      <td>The restaurant’s location name.</td>
    </tr>
    <tr>
      <td><code>restaurantLocationCode</code></td>
      <td>The restaurant’s location code.</td>
    </tr>
  </tbody>
</table>

