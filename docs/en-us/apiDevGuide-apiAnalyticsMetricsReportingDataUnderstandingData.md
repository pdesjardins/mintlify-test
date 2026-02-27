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
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">guestCount</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The total number of guests recorded across all orders.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">voidOrdersCount</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The total number of orders with at least one voided item.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">discountOrderCount</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The total number of orders that used a discount.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">ordersCount</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The total number of orders, excluding voided orders.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">openOrdersCount</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The total number of open orders.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">closedOrdersCount</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The total number of closed orders.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">netSalesAmount</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The total sales, excluding tax, gratuity, tips, discounts, and deferred amounts.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">grossSalesAmount</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The total sales, including applied discounts and refunds.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">discountAmount</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The total amount of discounts for orders.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">voidOrdersAmount</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The total amount of voided orders.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">refundAmount</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The total amount of refunded sales.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">avgOrderValue</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The average amount for an order.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">revenueCenter</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The revenue center for the order data. This appears when the <code className="font-mono text-sm">POST</code> request message body includes <code className="font-mono text-sm">groupBy</code> with <code className="font-mono text-sm">REVENUE_CENTER</code>. For more information, see <a href="apiDevGuide-apiAnalyticsMetricsReportingDataAggregation#apiAnalyticsMetricsReportingDataGroupBy" className="">Using the <code className="font-mono text-sm">groupBy</code> value</a>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">diningOption</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The dining option for the order data. This appears when the <code className="font-mono text-sm">POST</code> request message body includes <code className="font-mono text-sm">groupBy</code> with <code className="font-mono text-sm">DINING_OPTION</code>. For more information, see <a href="apiDevGuide-apiAnalyticsMetricsReportingDataAggregation#apiAnalyticsMetricsReportingDataGroupBy" className="">Using the <code className="font-mono text-sm">groupBy</code> value</a>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">orderSource</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The method used to place an order, also known as the order source. This appears when the <code className="font-mono text-sm">POST</code> request message body includes <code className="font-mono text-sm">groupBy</code> with <code className="font-mono text-sm">ORDER_SOURCE</code>. For more information, see <a href="apiDevGuide-apiAnalyticsMetricsReportingDataAggregation#apiAnalyticsMetricsReportingDataGroupBy" className="">Using the <code className="font-mono text-sm">groupBy</code> value</a>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">businessHour</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The hour the data represents. This appears when the <code className="font-mono text-sm">aggregateBy</code> query parameter is set to <code className="font-mono text-sm">HOUR</code> in the <code className="font-mono text-sm">/era/v1/metrics/day</code> request. For more information, see <a href="apiDevGuide-apiAnalyticsMetricsReportingDataAggregation#apiAnalyticsMetricsReportingDataAggregateBy" className="">Using the <code className="font-mono text-sm">aggregateBy</code> query parameter</a>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">hourlyJobTotalHours</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The total hours worked by employees with hourly jobs. This does not include breaks.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">hourlyJobTotalPay</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The total wages earned by employees with hourly jobs, including overtime pay. This does not include tips.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">hourlyJobSalesPerLaborHour</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The average net sales per each hour worked by employees with hourly jobs. </p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">restaurantName</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The restaurant’s name. This is included when you set the <code className="font-mono text-sm">fetchRestaurantNames</code> parameter to <code className="font-mono text-sm">true</code> in the <code className="font-mono text-sm">GET</code> request.</p></div></td>
    </tr>
  </tbody>
</table>
</div>

