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


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className="">Value name</th>
      <th className="">Definition</th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className=""><code className="">restaurantGuid</code></td>
      <td className="">The unique identifier assigned to the restaurant by the Toast platform.</td>
    </tr>
    <tr className="">
      <td className=""><code className="">businessDate</code></td>
      <td className="">The calendar date of the associated order data, in <code className="">YYYYMMDD</code> format.</td>
    </tr>
    <tr className="">
      <td className=""><code className="">regularHours</code></td>
      <td className="">The total regular hours logged between clock-in and clock-out for employees with hourly jobs. This does not include overtime hours.</td>
    </tr>
    <tr className="">
      <td className=""><code className="">overtimeHours</code></td>
      <td className="">The total overtime hours logged between clock-in and clock-out for employees with hourly jobs. This only includes overtime hours.</td>
    </tr>
    <tr className="">
      <td className=""><code className="">totalHours</code></td>
      <td className="">The total hours logged between clock-in and clock-out for employees with hourly jobs. This includes regular and overtime hours.</td>
    </tr>
    <tr className="">
      <td className=""><code className="">regularCost</code></td>
      <td className="">The operation costs related to employees with hourly jobs from all regular hours, including all shifts.</td>
    </tr>
    <tr className="">
      <td className=""><code className="">overtimeCost</code></td>
      <td className="">The operation costs related to employees with hourly jobs from all overtime hours, including all shifts.</td>
    </tr>
    <tr className="">
      <td className=""><code className="">totalCost</code></td>
      <td className="">The operation costs related to employees with hourly jobs from all work hours, including all shifts.</td>
    </tr>
    <tr className="">
      <td className=""><code className="">netSalesAmount</code></td>
      <td className="">The total sales, excluding tax, gratuity, tips, discounts, refunds, and deferred amounts. This property is only included when no <code className="">groupBy</code> value is specified.</td>
    </tr>
    <tr className="">
      <td className=""><code className="">grossSalesAmount</code></td>
      <td className="">The total sales, including discounts and refunds. This property is only included when no <code className="">groupBy</code> value is specified.</td>
    </tr>
    <tr className="">
      <td className=""><code className="">netSalesPerEmployeeHour</code></td>
      <td className="">The average of the location's total net sales for each hour clocked by an employee. This property is only included when no <code className="">groupBy</code> value is specified.</td>
    </tr>
    <tr className="">
      <td className=""><code className="">grossSalesPerEmployeeHour</code></td>
      <td className="">The average of the location's total gross sales for each hour clocked by an employee. This property is only included when no <code className="">groupBy</code> value is specified.</td>
    </tr>
    <tr className="">
      <td className=""><code className="">totalCostPerNetSales</code></td>
      <td className="">The ratio of employee operational costs compared to total net sales, expressed as a percentage.</td>
    </tr>
    <tr className="">
      <td className=""><code className="">totalCostPerGrossSales</code></td>
      <td className="">The ratio of employee operational costs compared to gross sales, expressed as a percentage.</td>
    </tr>
    <tr className="">
      <td className=""><code className="">jobGuid</code></td>
      <td className="">The identifier assigned by the Toast platform used to identify a job. This property is only included when the <code className="">groupBy</code> property uses the <code className="">JOB</code> value. If not aggregated by <code className="">JOB</code>, the value is <code className="">null</code>.</td>
    </tr>
    <tr className="">
      <td className=""><code className="">jobTitle</code></td>
      <td className="">The job name. This property only appears when the request for labor data includes the <code className="">groupBy</code> property with value <code className="">JOB</code>. If not aggregated by <code className="">JOB</code>, the value is <code className="">null</code>.</td>
    </tr>
    <tr className="">
      <td className=""><code className="">jobCode</code></td>
      <td className="">A reference identifier for the job. This is an optional field entered when the job is created. For example, it can be used to match Toast platform jobs to jobs configured in external labor management systems. This property only appears when the request for labor data includes the <code className="">groupBy</code> property with value <code className="">JOB</code>. If not aggregated by <code className="">JOB</code>, the value is <code className="">null</code>.</td>
    </tr>
    <tr className="">
      <td className=""><code className="">employeeGuid</code></td>
      <td className="">The identifier assigned by the Toast platform used to identify an employee. This property only appears when the request for labor data includes the <code className="">groupBy</code> property with value <code className="">EMPLOYEE</code>. If not aggregated by <code className="">EMPLOYEE</code>, the value is <code className="">null</code>.</td>
    </tr>
    <tr className="">
      <td className=""><code className="">employeeFirstName</code></td>
      <td className="">The employee's first name. This property is populated when the request for labor data includes the <code className="">groupBy</code> property with value <code className="">EMPLOYEE</code>. If not aggregated by <code className="">EMPLOYEE</code>, the value is <code className="">null</code>.</td>
    </tr>
    <tr className="">
      <td className=""><code className="">employeeLastName</code></td>
      <td className="">The employee's last name. This property is populated when the request for labor data includes the <code className="">groupBy</code> property with value <code className="">EMPLOYEE</code>. If not aggregated by <code className="">EMPLOYEE</code>, the value is <code className="">null</code>.</td>
    </tr>
    <tr className="">
      <td className=""><code className="">employeeChosenName</code></td>
      <td className="">The employee's chosen name. This property is populated when the request for labor data includes the <code className="">groupBy</code> property with value <code className="">EMPLOYEE</code>. If not aggregated by <code className="">EMPLOYEE</code>, the value is <code className="">null</code>.</td>
    </tr>
    <tr className="">
      <td className=""><code className="">restaurantName</code></td>
      <td className="">The restaurant’s name.</td>
    </tr>
    <tr className="">
      <td className=""><code className="">restaurantLocationName</code></td>
      <td className="">The restaurant’s location name.</td>
    </tr>
    <tr className="">
      <td className=""><code className="">restaurantLocationCode</code></td>
      <td className="">The restaurant’s location code.</td>
    </tr>
  </tbody>
</table>
</div>

