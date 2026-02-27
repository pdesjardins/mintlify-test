---
title: "Understanding aggregated sales reporting data"
id: apiAnalyticsMetricsReportingDataUnderstandingData
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiAnalyticsMetricsReportingDataOmitChunkFromSearchIndex.md
parentSectionTitle: "Aggregated sales reporting data"
previousSectionFile: apiDevGuide-apiAnalyticsMetricsReportingDataAggregation.md
previousSectionTitle: "Aggregating the aggregated sales reporting data"
nextSectionFile: apiDevGuide-apiAnalyticsCheckReportingDataOmitChunkFromSearchIndex.md
nextSectionTitle: "Check reporting data"
excerpt: "Aggregated sales reporting data contains..."
keywords: ["understanding", "aggregated", "sales", "reporting", "data", "restaurantGuid", "businessDate", "YYYYMMDD", "guestCount", "voidOrdersCount"]
procedures: 0
codeExamples: 0
---

Aggregated sales reporting data contains a constant set of values. These values appear for each active restaurant, and are grouped into sections either by day or hour, depending on how you choose to aggregate the data. Optionally, you can create subsections of the data by grouping by dining option, order source, revenue center, or a combination of two of these values. For more information, see [Aggregating the aggregated sales reporting data](apiDevGuide-apiAnalyticsMetricsReportingDataAggregation). You can also choose to include the restaurant name in the aggregated sales reporting data. For more information, see [Retrieving the aggregated sales reporting data](apiDevGuide-apiAnalyticsMetricsReportingDataRetrieveData). For more information about inactive restaurant data, see [Viewing inactive restaurant data](apiDevGuide-apiAnalyticsInactiveRestaurantData).

The restaurants included in the aggregated sales reporting data can be limited by adding the GUIDs of restaurants to either include only or exclude only. For more information about choosing specific restaurants, see [Creating a request for aggregated sales reporting data](apiDevGuide-apiAnalyticsMetricsReportingDataCreateRequest).

The following table specifies the returned set of values in the aggregated sales reporting data. The values are listed in the order that they appear.


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
      <td className=""><code className="">guestCount</code></td>
      <td className="">The total number of guests recorded across all orders.</td>
    </tr>
    <tr className="">
      <td className=""><code className="">voidOrdersCount</code></td>
      <td className="">The total number of orders with at least one voided item.</td>
    </tr>
    <tr className="">
      <td className=""><code className="">discountOrderCount</code></td>
      <td className="">The total number of orders that used a discount.</td>
    </tr>
    <tr className="">
      <td className=""><code className="">ordersCount</code></td>
      <td className="">The total number of orders, excluding voided orders.</td>
    </tr>
    <tr className="">
      <td className=""><code className="">openOrdersCount</code></td>
      <td className="">The total number of open orders.</td>
    </tr>
    <tr className="">
      <td className=""><code className="">closedOrdersCount</code></td>
      <td className="">The total number of closed orders.</td>
    </tr>
    <tr className="">
      <td className=""><code className="">netSalesAmount</code></td>
      <td className="">The total sales, excluding tax, gratuity, tips, discounts, and deferred amounts.</td>
    </tr>
    <tr className="">
      <td className=""><code className="">grossSalesAmount</code></td>
      <td className="">The total sales, including applied discounts and refunds.</td>
    </tr>
    <tr className="">
      <td className=""><code className="">discountAmount</code></td>
      <td className="">The total amount of discounts for orders.</td>
    </tr>
    <tr className="">
      <td className=""><code className="">voidOrdersAmount</code></td>
      <td className="">The total amount of voided orders.</td>
    </tr>
    <tr className="">
      <td className=""><code className="">refundAmount</code></td>
      <td className="">The total amount of refunded sales.</td>
    </tr>
    <tr className="">
      <td className=""><code className="">avgOrderValue</code></td>
      <td className="">The average amount for an order.</td>
    </tr>
    <tr className="">
      <td className=""><code className="">revenueCenter</code></td>
      <td className="">The revenue center for the order data. This appears when the <code className="">POST</code> request message body includes <code className="">groupBy</code> with <code className="">REVENUE_CENTER</code>. For more information, see <a href="apiDevGuide-apiAnalyticsMetricsReportingDataAggregation#apiAnalyticsMetricsReportingDataGroupBy" className="">Using the <code className="">groupBy</code> value</a>.</td>
    </tr>
    <tr className="">
      <td className=""><code className="">diningOption</code></td>
      <td className="">The dining option for the order data. This appears when the <code className="">POST</code> request message body includes <code className="">groupBy</code> with <code className="">DINING_OPTION</code>. For more information, see <a href="apiDevGuide-apiAnalyticsMetricsReportingDataAggregation#apiAnalyticsMetricsReportingDataGroupBy" className="">Using the <code className="">groupBy</code> value</a>.</td>
    </tr>
    <tr className="">
      <td className=""><code className="">orderSource</code></td>
      <td className="">The method used to place an order, also known as the order source. This appears when the <code className="">POST</code> request message body includes <code className="">groupBy</code> with <code className="">ORDER_SOURCE</code>. For more information, see <a href="apiDevGuide-apiAnalyticsMetricsReportingDataAggregation#apiAnalyticsMetricsReportingDataGroupBy" className="">Using the <code className="">groupBy</code> value</a>.</td>
    </tr>
    <tr className="">
      <td className=""><code className="">businessHour</code></td>
      <td className="">The hour the data represents. This appears when the <code className="">aggregateBy</code> query parameter is set to <code className="">HOUR</code> in the <code className="">/era/v1/metrics/day</code> request. For more information, see <a href="apiDevGuide-apiAnalyticsMetricsReportingDataAggregation#apiAnalyticsMetricsReportingDataAggregateBy" className="">Using the <code className="">aggregateBy</code> query parameter</a>.</td>
    </tr>
    <tr className="">
      <td className=""><code className="">hourlyJobTotalHours</code></td>
      <td className="">The total hours worked by employees with hourly jobs. This does not include breaks.</td>
    </tr>
    <tr className="">
      <td className=""><code className="">hourlyJobTotalPay</code></td>
      <td className="">The total wages earned by employees with hourly jobs, including overtime pay. This does not include tips.</td>
    </tr>
    <tr className="">
      <td className=""><code className="">hourlyJobSalesPerLaborHour</code></td>
      <td className="">The average net sales per each hour worked by employees with hourly jobs. </td>
    </tr>
    <tr className="">
      <td className=""><code className="">restaurantName</code></td>
      <td className="">The restaurant’s name. This is included when you set the <code className="">fetchRestaurantNames</code> parameter to <code className="">true</code> in the <code className="">GET</code> request.</td>
    </tr>
  </tbody>
</table>
</div>

