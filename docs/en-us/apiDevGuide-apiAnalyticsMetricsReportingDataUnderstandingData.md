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
      <td><code>guestCount</code></td>
      <td>The total number of guests recorded across all orders.</td>
    </tr>
    <tr>
      <td><code>voidOrdersCount</code></td>
      <td>The total number of orders with at least one voided item.</td>
    </tr>
    <tr>
      <td><code>discountOrderCount</code></td>
      <td>The total number of orders that used a discount.</td>
    </tr>
    <tr>
      <td><code>ordersCount</code></td>
      <td>The total number of orders, excluding voided orders.</td>
    </tr>
    <tr>
      <td><code>openOrdersCount</code></td>
      <td>The total number of open orders.</td>
    </tr>
    <tr>
      <td><code>closedOrdersCount</code></td>
      <td>The total number of closed orders.</td>
    </tr>
    <tr>
      <td><code>netSalesAmount</code></td>
      <td>The total sales, excluding tax, gratuity, tips, discounts, and deferred amounts.</td>
    </tr>
    <tr>
      <td><code>grossSalesAmount</code></td>
      <td>The total sales, including applied discounts and refunds.</td>
    </tr>
    <tr>
      <td><code>discountAmount</code></td>
      <td>The total amount of discounts for orders.</td>
    </tr>
    <tr>
      <td><code>voidOrdersAmount</code></td>
      <td>The total amount of voided orders.</td>
    </tr>
    <tr>
      <td><code>refundAmount</code></td>
      <td>The total amount of refunded sales.</td>
    </tr>
    <tr>
      <td><code>avgOrderValue</code></td>
      <td>The average amount for an order.</td>
    </tr>
    <tr>
      <td><code>revenueCenter</code></td>
      <td>The revenue center for the order data. This appears when the <code>POST</code> request message body includes <code>groupBy</code> with <code>REVENUE_CENTER</code>. For more information, see <a href="apiDevGuide-apiAnalyticsMetricsReportingDataAggregation#apiAnalyticsMetricsReportingDataGroupBy">Using the <code>groupBy</code> value</a>.</td>
    </tr>
    <tr>
      <td><code>diningOption</code></td>
      <td>The dining option for the order data. This appears when the <code>POST</code> request message body includes <code>groupBy</code> with <code>DINING_OPTION</code>. For more information, see <a href="apiDevGuide-apiAnalyticsMetricsReportingDataAggregation#apiAnalyticsMetricsReportingDataGroupBy">Using the <code>groupBy</code> value</a>.</td>
    </tr>
    <tr>
      <td><code>orderSource</code></td>
      <td>The method used to place an order, also known as the order source. This appears when the <code>POST</code> request message body includes <code>groupBy</code> with <code>ORDER_SOURCE</code>. For more information, see <a href="apiDevGuide-apiAnalyticsMetricsReportingDataAggregation#apiAnalyticsMetricsReportingDataGroupBy">Using the <code>groupBy</code> value</a>.</td>
    </tr>
    <tr>
      <td><code>businessHour</code></td>
      <td>The hour the data represents. This appears when the <code>aggregateBy</code> query parameter is set to <code>HOUR</code> in the <code>/era/v1/metrics/day</code> request. For more information, see <a href="apiDevGuide-apiAnalyticsMetricsReportingDataAggregation#apiAnalyticsMetricsReportingDataAggregateBy">Using the <code>aggregateBy</code> query parameter</a>.</td>
    </tr>
    <tr>
      <td><code>hourlyJobTotalHours</code></td>
      <td>The total hours worked by employees with hourly jobs. This does not include breaks.</td>
    </tr>
    <tr>
      <td><code>hourlyJobTotalPay</code></td>
      <td>The total wages earned by employees with hourly jobs, including overtime pay. This does not include tips.</td>
    </tr>
    <tr>
      <td><code>hourlyJobSalesPerLaborHour</code></td>
      <td>The average net sales per each hour worked by employees with hourly jobs. </td>
    </tr>
    <tr>
      <td><code>restaurantName</code></td>
      <td>The restaurant’s name. This is included when you set the <code>fetchRestaurantNames</code> parameter to <code>true</code> in the <code>GET</code> request.</td>
    </tr>
  </tbody>
</table>

