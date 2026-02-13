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

Aggregated sales reporting data contains a constant set of values.
      These values appear for each active restaurant, and are grouped into
      sections either by day or hour, depending on how you choose to aggregate
      the data. Optionally, you can create subsections of the data by grouping
      by dining option, order source, revenue center, or a combination of two
      of these values. For more information, see [Aggregating the aggregated sales reporting data](apiDevGuide-apiAnalyticsMetricsReportingDataAggregation). You can also
      choose to include the restaurant name in the aggregated sales reporting
      data. For more information, see [Retrieving the aggregated sales reporting data](apiDevGuide-apiAnalyticsMetricsReportingDataRetrieveData). For more
      information about inactive restaurant data, see [Viewing inactive restaurant data](apiDevGuide-apiAnalyticsInactiveRestaurantData).

The restaurants included in the aggregated sales reporting data
      can be limited by adding the GUIDs of restaurants to either include only
      or exclude only. For more information about choosing specific
      restaurants, see [Creating a request for aggregated sales reporting data](apiDevGuide-apiAnalyticsMetricsReportingDataCreateRequest).

The following table specifies the returned set of values in the
      aggregated sales reporting data. The values are listed in the order that
      they appear.

| Value name | Definition | 
| --- | --- |
| `restaurantGuid` | The unique identifier assigned to the restaurant by
              the Toast platform. | 
| `businessDate` | The calendar date of the associated order data, in
              `YYYYMMDD` format. | 
| `guestCount` | The total number of guests recorded across all
              orders. | 
| `voidOrdersCount` | The total number of orders with at least one voided
              item. | 
| `discountOrderCount` | The total number of orders that used a
              discount. | 
| `ordersCount` | The total number of orders, excluding voided
              orders. | 
| `openOrdersCount` | The total number of open orders. | 
| `closedOrdersCount` | The total number of closed orders. | 
| `netSalesAmount` | The total sales, excluding tax, gratuity, tips,
              discounts, and deferred amounts. | 
| `grossSalesAmount` | The total sales, including applied discounts and
              refunds. | 
| `discountAmount` | The total amount of discounts for
              orders. | 
| `voidOrdersAmount` | The total amount of voided orders. | 
| `refundAmount` | The total amount of refunded sales. | 
| `avgOrderValue` | The average amount for an order. | 
| `revenueCenter` | The revenue center for the order data. This appears
              when the `POST` request message body
              includes `groupBy` with `REVENUE_CENTER`.
              For more information, see [Using the `groupBy` value](apiDevGuide-apiAnalyticsMetricsReportingDataAggregation#apiAnalyticsMetricsReportingDataGroupBy). | 
| `diningOption` | The dining option for the order data. This appears
              when the `POST` request message body
              includes `groupBy` with `DINING_OPTION`.
              For more information, see [Using the `groupBy` value](apiDevGuide-apiAnalyticsMetricsReportingDataAggregation#apiAnalyticsMetricsReportingDataGroupBy). | 
| `orderSource` | The method used to place an order, also known as
              the order source. This appears when the
              `POST` request message body includes
              `groupBy` with `ORDER_SOURCE`. For more
              information, see [Using the `groupBy` value](apiDevGuide-apiAnalyticsMetricsReportingDataAggregation#apiAnalyticsMetricsReportingDataGroupBy). | 
| `businessHour` | The hour the data represents. This appears when the
              `aggregateBy` query parameter is set to
              `HOUR` in the `/era/v1/metrics/day`
              request. For more information, see [Using the `aggregateBy` query parameter](apiDevGuide-apiAnalyticsMetricsReportingDataAggregation#apiAnalyticsMetricsReportingDataAggregateBy). | 
| `hourlyJobTotalHours` | The total hours worked by employees with hourly
              jobs. This does not include breaks. | 
| `hourlyJobTotalPay` | The total wages earned by employees with hourly
              jobs, including overtime pay. This does not include
              tips. | 
| `hourlyJobSalesPerLaborHour` | The average net sales per each hour worked by
              employees with hourly jobs.  | 
| `restaurantName` | The restaurant’s name. This is included when you
              set the `fetchRestaurantNames` parameter to
              `true` in the `GET`
              request. | 

