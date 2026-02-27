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
      <th className=""><div className="">Value name</div></th>
      <th className=""><div className="">Definition</div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className=""><div className=""><code className="">restaurantGuid</code></div></td>
      <td className=""><div className="">The unique identifier assigned to the restaurant by the Toast platform.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><code className="">businessDate</code></div></td>
      <td className=""><div className="">The calendar date of the associated order data, in <code className="">YYYYMMDD</code> format.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><code className="">guestCount</code></div></td>
      <td className=""><div className="">The total number of guests recorded across all orders.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><code className="">voidOrdersCount</code></div></td>
      <td className=""><div className="">The total number of orders with at least one voided item.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><code className="">discountOrderCount</code></div></td>
      <td className=""><div className="">The total number of orders that used a discount.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><code className="">ordersCount</code></div></td>
      <td className=""><div className="">The total number of orders, excluding voided orders.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><code className="">openOrdersCount</code></div></td>
      <td className=""><div className="">The total number of open orders.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><code className="">closedOrdersCount</code></div></td>
      <td className=""><div className="">The total number of closed orders.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><code className="">netSalesAmount</code></div></td>
      <td className=""><div className="">The total sales, excluding tax, gratuity, tips, discounts, and deferred amounts.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><code className="">grossSalesAmount</code></div></td>
      <td className=""><div className="">The total sales, including applied discounts and refunds.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><code className="">discountAmount</code></div></td>
      <td className=""><div className="">The total amount of discounts for orders.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><code className="">voidOrdersAmount</code></div></td>
      <td className=""><div className="">The total amount of voided orders.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><code className="">refundAmount</code></div></td>
      <td className=""><div className="">The total amount of refunded sales.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><code className="">avgOrderValue</code></div></td>
      <td className=""><div className="">The average amount for an order.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><code className="">revenueCenter</code></div></td>
      <td className=""><div className="">The revenue center for the order data. This appears when the <code className="">POST</code> request message body includes <code className="">groupBy</code> with <code className="">REVENUE_CENTER</code>. For more information, see <a href="apiDevGuide-apiAnalyticsMetricsReportingDataAggregation#apiAnalyticsMetricsReportingDataGroupBy" className="">Using the <code className="">groupBy</code> value</a>.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><code className="">diningOption</code></div></td>
      <td className=""><div className="">The dining option for the order data. This appears when the <code className="">POST</code> request message body includes <code className="">groupBy</code> with <code className="">DINING_OPTION</code>. For more information, see <a href="apiDevGuide-apiAnalyticsMetricsReportingDataAggregation#apiAnalyticsMetricsReportingDataGroupBy" className="">Using the <code className="">groupBy</code> value</a>.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><code className="">orderSource</code></div></td>
      <td className=""><div className="">The method used to place an order, also known as the order source. This appears when the <code className="">POST</code> request message body includes <code className="">groupBy</code> with <code className="">ORDER_SOURCE</code>. For more information, see <a href="apiDevGuide-apiAnalyticsMetricsReportingDataAggregation#apiAnalyticsMetricsReportingDataGroupBy" className="">Using the <code className="">groupBy</code> value</a>.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><code className="">businessHour</code></div></td>
      <td className=""><div className="">The hour the data represents. This appears when the <code className="">aggregateBy</code> query parameter is set to <code className="">HOUR</code> in the <code className="">/era/v1/metrics/day</code> request. For more information, see <a href="apiDevGuide-apiAnalyticsMetricsReportingDataAggregation#apiAnalyticsMetricsReportingDataAggregateBy" className="">Using the <code className="">aggregateBy</code> query parameter</a>.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><code className="">hourlyJobTotalHours</code></div></td>
      <td className=""><div className="">The total hours worked by employees with hourly jobs. This does not include breaks.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><code className="">hourlyJobTotalPay</code></div></td>
      <td className=""><div className="">The total wages earned by employees with hourly jobs, including overtime pay. This does not include tips.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><code className="">hourlyJobSalesPerLaborHour</code></div></td>
      <td className=""><div className="">The average net sales per each hour worked by employees with hourly jobs. </div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><code className="">restaurantName</code></div></td>
      <td className=""><div className="">The restaurant’s name. This is included when you set the <code className="">fetchRestaurantNames</code> parameter to <code className="">true</code> in the <code className="">GET</code> request.</div></td>
    </tr>
  </tbody>
</table>
</div>

