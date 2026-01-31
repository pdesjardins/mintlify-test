---
title: "Chapter 11. Analytics"
id: apiAnalyticsOmitChunkFromSearchIndex
type: chapter
documentId: apiDevGuide
parentSectionFile: apiDevGuide-index.md
parentSectionTitle: "Developer guide"
previousSectionFile: apiDevGuide-apiTenderScanToPay.md
previousSectionTitle: "Scan-to-pay"
nextSectionFile: apiDevGuide-apiAnalyticsMetricsReportingDataOmitChunkFromSearchIndex.md
nextSectionTitle: "Aggregated sales reporting data"
externalReferences: [https://www.toasttab.com/customers/shop/software-services/restaurant-management-suite?tier=Pro]
procedures: 0
codeExamples: 0
---

# Chapter 11. Analytics

## About the analytics API

### Analytics API overview



> **Important**
> 
> All metric data supported in the analytics API does not adhere to accounting standards such as GAAP rules. This information is solely for informational purposes. Toast, Inc. does not offer accounting or tax advice.


You can use the analytics API to request and view analytics data for restaurants in a [management group](adminManagementGroup.html).



> **Note**
> 
> Access to the analytics API requires an active subscription to [Toast Restaurant Management Suite Pro](https://www.toasttab.com/customers/shop/software-services/restaurant-management-suite?tier=Pro) or higher.


You can use the analytics API to:

- Retrieve aggregated sales reporting data, which provides a high-level view of orders data for a restaurant. This includes sales and labor information. For more information, see [Aggregated sales reporting data overview](apiAnalyticsMetricsReportingDataOmitChunkFromSearchIndex.html#apiAnalyticsMetricsReportingDataOverview).


- Retrieve check reporting data, which provides a detailed look at checks for a restaurant for a single day. For more information, see [Check reporting data overview](apiAnalyticsCheckReportingDataOmitChunkFromSearchIndex.html#apiAnalyticsCheckReportingDataOverview).


- Retrieve labor reporting data, which provides a detailed look at employee and job information. For more information, see [Labor reporting data overview](apiAnalyticsLaborReportingDataOmitChunkFromSearchIndex.html#apiAnalyticsLaborReportingDataOverview).


- Retrieve menu reporting information, which provides a detailed look at menu and menu entity information. For more information, see [Menu reporting data overview](apiAnalyticsMenuReportingDataOmitChunkFromSearchIndex.html#apiAnalyticsMenuReportingDataOverview).


- Retrieve payout reporting data, which provides a detailed look at all deposits made to an account. For more information, see [Payout reporting data overview](apiAnalyticsPayoutReportingDataOmitChunkFromSearchIndex.html#apiAnalyticsPayoutReportingDataOverview).


- Retrieve guest reporting information, which provides a look at payment details associated with a guest's payment card. For more information, see [Guest reporting data overview](apiAnalyticsGuestDataOmitChunkFromSearchIndex.html#apiAnalyticsGuestDataOverview).


- Retrieve restaurant information, which provides the names and GUIDs for restaurants in a management group. For more information, see [Restaurant information overview](apiAnalyticsRestaurantInfoOmitChunkFromSearchIndex.html#apiAnalyticsRestaurantInfoOverview).



Toast APIs, including the analytics API, control access to integration functionality using client authentication. When you authenticate your API client you use client credentials that you get from the Toast integrations team. The Toast platform includes different API integration types and uses separate API client credentials for each integration type. For information about using client credentials to authenticate and access Toast APIs, see [Authentication and restaurant access](authenticationOmitChunkFromSearchIndex.html#authentication).

**Important information about analytics API client authentication credentials**

- Analytics API authentication credentials are different from other Toast API authentication credentials.


- If your organization has access to other Toast APIs, you cannot use the authentication credentials for other Toast APIs to access the analytics API. You must use separate client authentication credentials for the analytics API.



### Understanding the analytics API process

Retrieving the analytics data involves two steps:

1. Creating a request for the analytics data and receiving a request identifier


2. Retrieving the analytics data using the request identifier





> **Note**
> 
> The `reportRequestGuid` expires seven days after you create it. Using an expired or invalid `reportRequestGuid`results in a 404 error. The `message` of the response body contains additional information about the cause of the error.


To create a request, you send a `POST`request to the endpoint corresponding to the type and time range of the analytics data you want. When creating the request, you specify what to include in the analytics data and how you want it to be organized in query parameters and the message body. The analytics API then returns the `reportRequestGuid`, the unique identifier used to identify this request.

To retrieve the analytics data, you send a `GET` request to the endpoint corresponding to the type and time range of the initial request for analytics data. You include the `reportRequestGuid` in the request to retrieve the analytics data you defined when creating the request. The API then returns the analytics data.

### Required scope for the analytics API

All analytics API endpoints require the `enterprise-metrics:read` scope. This includes creating a analytics data request, retrieving the analytics data, and retrieving restaurant information for the management group.

### Analytics API rate limits

The rate limit used by an endpoint depends on the endpoint and its time range. The following table lists the endpoints of the analytics API, organized by endpoint, method type, and rate limit. Notes are included when applicable.



> **Note**
> 
> As a Toast API, the analytics API adheres to the global rate limits. For more information, see [Rate limiting](apiRateLimiting.html).


| Method and endpoint | Rate limits | Notes | 
| --- | --- | --- |
| `POST``/era/v1/metrics` | 10 requests per hour | This endpoint uses a custom time range. | 
| `POST``/era/v1/metrics/{timeRange}` | If `{timeRange`} is:- `month` or `year`: 10 requests per hour
- `day` or `week`: 10 requests per minute, 60 requests per hour

 |  | 
| `GET``/era/v1/metrics/{reportRequestGuid}` | 5 requests per second30 requests per minute |   | 
| `POST``/era/v1/check/{timeRange}` | 5 requests per minute60 requests per day | This endpoint uses `day` as the `{timeRange}`. | 
| `GET``/era/v1/check/{reportRequestGuid}` | 5 requests per second30 requests per minute |  | 
| `POST``/era/v1/labor/{timeRange}` | If `{timeRange`} is:- `month`: 10 requests per hour
- `day` or `week`: 10 requests per minute, 60 requests per hour

 |  | 
| `GET``/era/v1/labor/{reportRequestGuid}` | 5 requests per second30 requests per minute |  | 
| `POST``/era/v1/menu` | 10 requests per hour | This endpoint uses a custom time range. | 
| `POST``/era/v1/menu/{timeRange}` | If `{timeRange`} is:- `month` or `year`: 10 requests per hour
- `day` or `week`: 10 requests per minute, 60 requests per hour

 |  | 
| `GET``/era/v1/menu/{reportRequestGuid}` | 5 requests per second30 requests per minute |  | 
| `POST``/era/v1/payout/{timeRange}` | If `{timeRange`} is:- `month`: 10 requests per hour
- `day` or `week`: 10 requests per minute and 60 requests per hour

 |  | 
| `GET``/era/v1/payout/{reportRequestGuid}` | 5 requests per second30 requests per minute |  | 
| `POST``/era/v1/payout/payments/{timeRange}` | 5 requests per minute60 requests per day | This endpoint uses `day` as the `{timeRange}`. | 
| `GET``/era/v1/payout/payments/{reportRequestGuid}` | 5 requests per second30 requests per minute |  | 
| `POST``/era/v1/payout/sales-date/{timeRange}` | If `{timeRange`} is:- `month`: 10 requests per hour
- `day` or `week`: 10 requests per minute and 60 requests per hour

 |  | 
| `GET``/era/v1/payout/sales-date/{reportRequestGuid}` | 5 requests per second30 requests per minute |  | 
| `POST``/era/v1/guest/payments/{timeRange}` | 5 requests per second60 requests per minute | This endpoint uses `day` or `week` as the `{timeRange}`. | 
| `GET``/era/v1/guest/payments/{reportRequestGuid}` | 5 requests per second30 requests per minute |   | 
| `GET``/era/v1/restaurant-info` | 5 requests per second30 requests per minute |  | 

### Understanding data discrepancies

Data discrepancies can occur when orders are modified. When an order is modified, the changes are updated in the analytics data. The time until the analytics data reflects this update depends on the when the order is modified and when the order was originally scheduled for fulfillment:



> **Note**
> 
> The date an order was originally scheduled for fulfillment is considered the *initial order open date*.


- If an order is modified within the range of 11 days before or two days after the *initial order open date*, the analytics data is updated within two and four hours of when the order was modified.


- If an order is modified outside that range of 11 days before or two days after the *initial order open date*, the analytics data is updated within six days of when the order was modified.



For example, an order is created on September 8 and scheduled for fulfillment on September 10. September 10 is the *initial order open date*, while September 8 is the day the order was created. If the guest calls and changes the order to be scheduled for September 12 instead, September 10 remains the *initial order open date*, but the new date for scheduled fulfillment becomes September 12.

For example, an order is scheduled for August 15, which is the *initial order open date*. If the order is modified between August 4 and August 17, the modification is reflected in the analytics data within two to four hours. If the order is modified before August 4 or after August 17, the modification is reflected in the analytics data within six days. If the order is modified on August 18, then the data is updated by August 24, six days after the order is modified.

### Viewing inactive restaurant data

By default, the analytics data only includes data from restaurants that are considered active at the time and date you make the analytics data request. To view inactive restaurant data, you can include the `onlyInactiveRestaurants` query parameter in the `POST` request to the `/era/v1/metrics` or `/era/v1/metrics/{timeRange}`endpoints.

The `onlyInactiveRestaurants` query parameter returns the analytics data for all restaurants in a management group currently considered inactive at the time you send the analytics data request.

For example, if you use the `onlyInactiveRestaurants`query parameter, a restaurant that is *currently*active, but was inactive during the requested time range, is *not* included. A restaurant that is *currently* inactive, but was active during the requested time range, *is* included.

Setting `onlyInactiveRestaurants` to `TRUE`includes inactive restaurant data and excludes active restaurant data while setting to `FALSE` excludes inactive restaurant data and includes active restaurant data. The data is treated as if `onlyInactiveRestaurants` is set to `FALSE` by default.

The following example **curl** command sends a `POST` request to the `/era/v1/metrics` endpoint using the `onlyInactiveRestaurants` query parameter.

```
curl -i -X POST \ 'https://`[toast-api-hostname]`/era/v1/metrics
?onlyInactiveRestaurants=TRUE' \[(1)](apiDevGuide-apiAnalyticsOmitChunkFromSearchIndex.html#d1e2941F37ED50-563A-4DC2-A142-7FD5B7B554A5-co)
  -H ‘Authorization: Bearer `[token]`‘ \
  -H 'Content-Type: application/json' \
  -d @`[request-info]`.json \

```



(1) Include the onlyInactiveRestaurants query parameter set to TRUE to request analytics data from inactive restaurants only.

If there are no inactive restaurants in a management group, the response to the `POST` request for the analytics data is a "No inactive restaurants found" message. For more information about creating a request for aggregated sales reporting data, see [Creating a request for aggregated sales reporting data](apiAnalyticsMetricsReportingDataCreateRequest.html).

If there are inactive restaurants in a management group, but no sales from those restaurants during the requested time range, the response to the `GET` request for the analytics data is a closing and opening bracket. For more information about retrieving aggregated sales reporting data, see [Retrieving the aggregated sales reporting data](apiAnalyticsMetricsReportingDataRetrieveData.html).

