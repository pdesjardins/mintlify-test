---
title: "Viewing inactive restaurant data"
id: apiAnalyticsInactiveRestaurantData
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiAboutAnalyticsOmitChunkFromSearchIndex.md
parentSectionTitle: "About the analytics API"
previousSectionFile: apiDevGuide-apiAnalyticsDataDiscrepancies.md
previousSectionTitle: "Understanding data discrepancies"
nextSectionFile: apiDevGuide-apiAnalyticsMetricsReportingDataOmitChunkFromSearchIndex.md
nextSectionTitle: "Aggregated sales reporting data"
excerpt: "By default, the analytics data only..."
keywords: ["viewing", "inactive", "restaurant", "data", "onlyInactiveRestaurants", "/era/v1/metrics/{timeRange}", "TRUE", "FALSE"]
procedures: 0
codeExamples: 1
---

By default, the analytics data only includes data from restaurants that are considered active at the time and date you make the analytics data request. To view inactive restaurant data, you can include the `onlyInactiveRestaurants` query parameter in the `POST` request to the `/era/v1/metrics` or `/era/v1/metrics/&#123;timeRange&#125;`endpoints.

The `onlyInactiveRestaurants` query parameter returns the analytics data for all restaurants in a management group currently considered inactive at the time you send the analytics data request.

For example, if you use the `onlyInactiveRestaurants`query parameter, a restaurant that is *currently*active, but was inactive during the requested time range, is *not* included. A restaurant that is *currently* inactive, but was active during the requested time range, *is* included.

Setting `onlyInactiveRestaurants` to `TRUE`includes inactive restaurant data and excludes active restaurant data while setting to `FALSE` excludes inactive restaurant data and includes active restaurant data. The data is treated as if `onlyInactiveRestaurants` is set to `FALSE` by default.

The following example **curl** command sends a `POST` request to the `/era/v1/metrics` endpoint using the `onlyInactiveRestaurants` query parameter.


```
curl -i -X POST \ 'https://`[toast-api-hostname]`/era/v1/metrics
?onlyInactiveRestaurants=TRUE' \
  -H ‘Authorization: Bearer `[token]`‘ \
  -H 'Content-Type: application/json' \
  -d @`[request-info]`.json \

```



    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e2941F37ED50-563A-4DC2-A142-7FD5B7B554A5" className="">(1)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Include the <code className="font-mono text-sm">onlyInactiveRestaurants</code> query parameter set to <code className="font-mono text-sm">TRUE</code> to request analytics data from inactive restaurants only.</p></div></td>
    </tr>
If there are no inactive restaurants in a management group, the response to the `POST` request for the analytics data is a "No inactive restaurants found" message. For more information about creating a request for aggregated sales reporting data, see [Creating a request for aggregated sales reporting data](apiDevGuide-apiAnalyticsMetricsReportingDataCreateRequest).

If there are inactive restaurants in a management group, but no sales from those restaurants during the requested time range, the response to the `GET` request for the analytics data is a closing and opening bracket. For more information about retrieving aggregated sales reporting data, see [Retrieving the aggregated sales reporting data](apiDevGuide-apiAnalyticsMetricsReportingDataRetrieveData).

