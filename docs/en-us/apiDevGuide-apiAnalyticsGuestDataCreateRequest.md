---
title: "Creating a request for guest reporting data"
id: apiAnalyticsGuestDataCreateRequest
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiAnalyticsGuestDataOmitChunkFromSearchIndex.md
parentSectionTitle: "Guest reporting data"
previousSectionFile: apiDevGuide-apiAnalyticsGuestDataOverview.md
previousSectionTitle: "Guest reporting data overview"
nextSectionFile: apiDevGuide-apiAnalyticsGuestDataRetrieveData.md
nextSectionTitle: "Retrieving the guest reporting data"
excerpt: "Send..."
keywords: ["creating", "request", "guest", "reporting", "data", "/era/v1/guest/payments/{timeRange}", "onlyInactiveRestaurants", "startDate", "YYYYMMDD", "endDate"]
procedures: 0
codeExamples: 0
---

Send a `POST` request to the `/era/v1/guest/payments/&#123;timeRange&#125;` endpoint to request guest reporting data organized by payment for a specific time range of `day` or `week`. The rate limit for this endpoint and method type is five requests per minute and 60 requests per day. For more information about API rate limits for the analytics API, see [Analytics API rate limits](apiDevGuide-apiAnalyticsRateLimiting).

You can limit the reporting data to inactive restaurants only using the `onlyInactiveRestaurants` query parameter. For more information, see [Viewing inactive restaurant data](apiDevGuide-apiAnalyticsInactiveRestaurantData).

To create a request for guest reporting data organized by payment, include the following:

- The `startDate` value in the message body, in `YYYYMMDD` format. This identifies the start date for the range of guest payment dates. This value must match the `endDate` value if using the `day` time range.


- The `endDate` value in the message body, in `YYYYMMDD` format. This identifies the end date for the range of guest payment dates. This value must match the `startDate` value if using the `day` time range.


- The `restaurantIds` value in the message body. This identifies the restaurants to include in the returned data using the restaurant GUID. All restaurants not listed are excluded from the returned data. Leave the `restaurantIds` value and the `excludedRestaurantIds` value empty to include all restaurants.


- The `excludedRestaurantIds` value in the message body. This identifies the restaurants to exclude in the returned data using the restaurant GUID. All restaurants not listed are included in the returned data. Leave the `excludedRestaurantIds` value and the `restaurantIds` value empty to include all restaurants.





> **Important**
> 
> You can include restaurant GUIDs for either `restaurantIds` or `excludedRestaurantIds` but not for both. Listing restaurant GUIDs for both results in a 400 error or blank guest reporting data. `restaurantIds` and `excludedRestaurantIds` are contradictory values that cannot be used together.


## Request for guest reporting data

The following example **curl** command sends a `POST` request to the `/era/v1/guest/payments/&#123;timeRange&#125;` endpoint. This example uses the `week` time range.


```
curl -i -X POST \ 'https://[toast-api-hostname]/era/v1/guest/payments/week' \
-H ‘Authorization: Bearer [token]‘ \
  -H 'Content-Type: application/json' \
  -d @[request-info].json \
```



    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e9261AAAFB51B-562D-4033-B77B-6C18243DEDD8" className="">(1)</a> </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Send a <code className="font-mono text-sm">POST</code> request to the <code className="font-mono text-sm">/era/v1/guest/payments/&#123;timeRange&#125;</code> endpoint of the analytics API. The <code className="font-mono text-sm">&#123;timeRange&#125;</code> in this example is <code className="font-mono text-sm">week</code>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e9263AAAFB51B-562D-4033-B77B-6C18243DEDD8" className="">(2)</a> </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Include an authentication token. For more information, see <a href="apiDevGuide-authentication" className="">Authentication and restaurant access</a>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e9265AAAFB51B-562D-4033-B77B-6C18243DEDD8" className="">(3)</a> </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Set the data type of the message body to <code className="font-mono text-sm">application/json</code>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e9267AAAFB51B-562D-4033-B77B-6C18243DEDD8" className="">(4)</a> </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Include details about the requested guest reporting data in the message body. The following example is the message body for this <strong className="font-semibold">curl</strong>  command example.</p></div></td>
    </tr>
## Message body for guest reporting data

The following example shows the message body for creating a guest reporting data request for a specific time range. This example is for the `week` time range.


```
{
  "restaurantIds": [
    "95a96d7b-dbf5-46d3-98c5-c65c8ad18021",
    "6b853fa7-b3dc-4db7-a528-c3599823ccd1"
  ],
  "excludedRestaurantIds": [],
  "startDate": "20240924",
  "endDate": "20240926"
}

```



    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e9279AAAFB51B-562D-4033-B77B-6C18243DEDD8" className="">(1)</a> </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The list of restaurant GUIDs from the management group to include in the guest reporting data. Restaurant GUIDs not listed are excluded.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e9281AAAFB51B-562D-4033-B77B-6C18243DEDD8" className="">(2)</a> </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The list of restaurant GUIDs from the management group to exclude from the guest reporting data. In this example, restaurants are included with the <code className="font-mono text-sm">restaurantIds</code> value, so all other restaurants are excluded automatically.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e9283AAAFB51B-562D-4033-B77B-6C18243DEDD8" className="">(3)</a> </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The start date of the time range for the guest reporting data, in <code className="font-mono text-sm">YYYYMMDD</code> format.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e9285AAAFB51B-562D-4033-B77B-6C18243DEDD8" className="">(4)</a> </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The end date of the time range for the guest reporting data, in <code className="font-mono text-sm">YYYYMMDD</code> format.</p></div></td>
    </tr>
## Response to request for guest reporting data

The following example shows the response from the `/era/v1/guest/payments/&#123;timeRange&#125;` endpoint.


```
"fb23cfaa-56d7-4cb9-829d-531a8d02274a"
```



    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e9298AAAFB51B-562D-4033-B77B-6C18243DEDD8" className="">(1)</a> </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The GUID for the guest reporting data request, also called the <code className="font-mono text-sm">reportRequestGuid</code>. For more information about how to retrieve data using the analytics API, see <a href="apiDevGuide-apiAnalyticsUnderstandingProcess" className="">Understanding the analytics API process</a>.</p></div></td>
    </tr>
For an example about how to retrieve the guest reporting data, see [Retrieving the guest reporting data](apiDevGuide-apiAnalyticsGuestDataRetrieveData).

