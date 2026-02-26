---
title: "Retrieving the check reporting data"
id: apiAnalyticsCheckReportingDataRetrieveData
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiAnalyticsCheckReportingDataOmitChunkFromSearchIndex.md
parentSectionTitle: "Check reporting data"
previousSectionFile: apiDevGuide-apiAnalyticsCheckReportingDataCreateRequest.md
previousSectionTitle: "Creating a request for check reporting data"
nextSectionFile: apiDevGuide-apiAnalyticsCheckReportingDataUnderstandingData.md
nextSectionTitle: "Understanding the check reporting data"
excerpt: "Send..."
keywords: ["retrieving", "check", "reporting", "data", "/era/v1/check/{reportRequestGuid}", "reportRequestGuid", "fetchRestaurantNames"]
procedures: 0
codeExamples: 0
---

Send a `GET` request to the `/era/v1/check/&#123;reportRequestGuid&#125;` endpoint to retrieve check reporting data. The rate limit for this endpoint and method type is five requests per second and 30 requests per minute. For information about API rate limits for the analytics API, see [Analytics API rate limits](apiDevGuide-apiAnalyticsRateLimiting).

To request the check reporting data, you must include the check reporting data request GUID, or `reportRequestGuid`, as a path variable.

Optionally, you can choose to include a `fetchRestaurantNames` query parameter. If the `fetchRestaurantNames` query parameter is set to `true`, it adds the restaurant name to the check reporting data. If the `fetchRestaurantNames` query parameter is set to `false` or not included, it does not add the restaurant name.

## Request to retrieve check reporting data

The following example **curl** command sends a `GET` request to the `/era/v1/check/&#123;reportRequestGuid&#125;` endpoint.


```
curl -X GET \ 'https://`[toast-api-hostname]`/era/v1/check/
83c93717-02ba-4b7c-9891-dfe090274d2d/
&fetchRestaurantNames=true’ \
  -H 'Authorization: Bearer `[token]`'
```



    <tr>
      <td><a href="#co-d1e2947DE10C5BE-C9CE-4C55-87A6-C813632B28B5">(1)</a></td>
      <td>Send a <code>GET</code> request to the <code>/era/v1/check</code> endpoint of the analytics API.</td>
    </tr>
    <tr>
      <td><a href="#co-d1e2949DE10C5BE-C9CE-4C55-87A6-C813632B28B5">(2)</a></td>
      <td>The GUID for the check reporting data request, also called the <code>reportRequestGuid</code>. For more information about the analytics API process, see <a href="apiDevGuide-apiAnalyticsUnderstandingProcess">Understanding the analytics API process</a>.</td>
    </tr>
    <tr>
      <td><a href="#co-d1e2951DE10C5BE-C9CE-4C55-87A6-C813632B28B5">(3)</a></td>
      <td>Set the <code>fetchRestaurantNames</code> query parameter to <code>true</code> to include the restaurant name in the response.</td>
    </tr>
    <tr>
      <td><a href="#co-d1e2953DE10C5BE-C9CE-4C55-87A6-C813632B28B5">(4)</a></td>
      <td>Include an authentication token. For more information, see <a href="apiDevGuide-authentication">Authentication and restaurant access</a>.</td>
    </tr>
## Response to the retrieval request for check reporting data

The following example shows the response from the `/era/v1/check/&#123;reportRequestGuid&#125;` endpoint.


```
[
  {
    "restaurantGuid": "95a96d7b-dbf5-46d3-98c5-c65c8ad18021",
    "orderNumber": "5018",
    "orderGuid": "f8e4ae5e-ccbd-49e5-81e8-947d673c30ad",
    "checkNumber": "5018",
    "checkGuid": "98bca966-4969-4314-9a8a-8486340164d2",
    "orderOpenedDate": "20230201",
    "checkPaidDateTime": "2023-02-02T00:37:20.089Z",
    "checkModifiedDateTime": "2023-02-02T19:04:46.340Z",
    "checkStatus": "CLOSED",
    "checkVoidedStatus": false,
    "diningOption": "Dine In",
    "revenueCenter": "Dining Room",
    "serverName": "Lydia Bennet",
    "checkTotalAmount": 35.59,
    "checkDiscountAmount": 0.0,
    "checkTaxAmount": 2.06,
    "checkTipAmount": 5.59,
    "checkGratuityAmount": 0.0,
    "checkRefundAmount": 0.0,
    "restaurantName": "Grove Place Cafe"
  },
  [content omitted]
  {
    "restaurantGuid": "95a96d7b-dbf5-46d3-98c5-c65c8ad18021",
    "orderNumber": "5010",
    "orderGuid": "98bca966-4969-4314-9a8a-8486340164d2",
    "checkNumber": "5010",
    "checkGuid": "e3dd31e1-78bb-47e4-a1a3-7c14c9f8c8ff",
    "orderOpenedDate": "20230201",
    "checkPaidDateTime": "2023-02-01T23:48:56.896Z",
    "checkModifiedDateTime": "2023-02-02T19:04:39.186Z",
    "checkStatus": "CLOSED",
    "checkVoidedStatus": false,
    "diningOption": "Take Out",
    "revenueCenter": "Dining Room",
    "serverName": "Lydia Bennet",
    "checkTotalAmount": 23.24,
    "checkDiscountAmount": 0.0,
    "checkTaxAmount": 1.32,
    "checkTipAmount": 3.95,
    "checkGratuityAmount": 0.0,
    "checkRefundAmount": 0.0,
    "restaurantName": "Grove Place Cafe"
  }
]

```



    <tr>
      <td><a href="#co-d1e3178EFD2B73E-74F6-4B53-908A-CFB01123F156">(1)</a></td>
      <td>The <code>restaurantName</code> value appears because the <code>fetchRestaurantName</code> query parameter was set to <code>true</code> in the request.</td>
    </tr>
For more information about the values in the response, see [Understanding the check reporting data](apiDevGuide-apiAnalyticsCheckReportingDataUnderstandingData).

