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
      <th className=""><div className=""><p className="text-base leading-relaxed">Value name</p></div></th>
      <th className=""><div className=""><p className="text-base leading-relaxed">Definition</p></div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">restaurantGuid</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The unique identifier assigned to the restaurant by the Toast platform.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">businessDate</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The calendar date of the associated order data, in <code className="font-mono text-sm">YYYYMMDD</code> format.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">regularHours</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The total regular hours logged between clock-in and clock-out for employees with hourly jobs. This does not include overtime hours.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">overtimeHours</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The total overtime hours logged between clock-in and clock-out for employees with hourly jobs. This only includes overtime hours.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">totalHours</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The total hours logged between clock-in and clock-out for employees with hourly jobs. This includes regular and overtime hours.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">regularCost</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The operation costs related to employees with hourly jobs from all regular hours, including all shifts.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">overtimeCost</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The operation costs related to employees with hourly jobs from all overtime hours, including all shifts.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">totalCost</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The operation costs related to employees with hourly jobs from all work hours, including all shifts.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">netSalesAmount</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The total sales, excluding tax, gratuity, tips, discounts, refunds, and deferred amounts. This property is only included when no <code className="font-mono text-sm">groupBy</code> value is specified.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">grossSalesAmount</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The total sales, including discounts and refunds. This property is only included when no <code className="font-mono text-sm">groupBy</code> value is specified.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">netSalesPerEmployeeHour</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The average of the location's total net sales for each hour clocked by an employee. This property is only included when no <code className="font-mono text-sm">groupBy</code> value is specified.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">grossSalesPerEmployeeHour</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The average of the location's total gross sales for each hour clocked by an employee. This property is only included when no <code className="font-mono text-sm">groupBy</code> value is specified.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">totalCostPerNetSales</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The ratio of employee operational costs compared to total net sales, expressed as a percentage.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">totalCostPerGrossSales</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The ratio of employee operational costs compared to gross sales, expressed as a percentage.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">jobGuid</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The identifier assigned by the Toast platform used to identify a job. This property is only included when the <code className="font-mono text-sm">groupBy</code> property uses the <code className="font-mono text-sm">JOB</code> value. If not aggregated by <code className="font-mono text-sm">JOB</code>, the value is <code className="font-mono text-sm">null</code>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">jobTitle</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The job name. This property only appears when the request for labor data includes the <code className="font-mono text-sm">groupBy</code> property with value <code className="font-mono text-sm">JOB</code>. If not aggregated by <code className="font-mono text-sm">JOB</code>, the value is <code className="font-mono text-sm">null</code>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">jobCode</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">A reference identifier for the job. This is an optional field entered when the job is created. For example, it can be used to match Toast platform jobs to jobs configured in external labor management systems. This property only appears when the request for labor data includes the <code className="font-mono text-sm">groupBy</code> property with value <code className="font-mono text-sm">JOB</code>. If not aggregated by <code className="font-mono text-sm">JOB</code>, the value is <code className="font-mono text-sm">null</code>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">employeeGuid</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The identifier assigned by the Toast platform used to identify an employee. This property only appears when the request for labor data includes the <code className="font-mono text-sm">groupBy</code> property with value <code className="font-mono text-sm">EMPLOYEE</code>. If not aggregated by <code className="font-mono text-sm">EMPLOYEE</code>, the value is <code className="font-mono text-sm">null</code>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">employeeFirstName</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The employee's first name. This property is populated when the request for labor data includes the <code className="font-mono text-sm">groupBy</code> property with value <code className="font-mono text-sm">EMPLOYEE</code>. If not aggregated by <code className="font-mono text-sm">EMPLOYEE</code>, the value is <code className="font-mono text-sm">null</code>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">employeeLastName</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The employee's last name. This property is populated when the request for labor data includes the <code className="font-mono text-sm">groupBy</code> property with value <code className="font-mono text-sm">EMPLOYEE</code>. If not aggregated by <code className="font-mono text-sm">EMPLOYEE</code>, the value is <code className="font-mono text-sm">null</code>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">employeeChosenName</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The employee's chosen name. This property is populated when the request for labor data includes the <code className="font-mono text-sm">groupBy</code> property with value <code className="font-mono text-sm">EMPLOYEE</code>. If not aggregated by <code className="font-mono text-sm">EMPLOYEE</code>, the value is <code className="font-mono text-sm">null</code>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">restaurantName</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The restaurant’s name.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">restaurantLocationName</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The restaurant’s location name.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">restaurantLocationCode</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The restaurant’s location code.</p></div></td>
    </tr>
  </tbody>
</table>
</div>

