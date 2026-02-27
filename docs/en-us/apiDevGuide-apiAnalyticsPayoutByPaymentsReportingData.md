---
title: "Payout reporting data by payments"
id: apiAnalyticsPayoutByPaymentsReportingData
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiAnalyticsPayoutReportingDataOmitChunkFromSearchIndex.md
parentSectionTitle: "Payout reporting data"
previousSectionFile: apiDevGuide-apiAnalyticsPayoutBySettledDateReportingData.md
previousSectionTitle: "Payout reporting data by settled date"
nextSectionFile: apiDevGuide-apiAnalyticsPayoutBySalesDateReportingData.md
nextSectionTitle: "Payout reporting data by sales date"
excerpt: "Retrieving the payout reporting data by payment is a two-step process. You must:"
keywords: ["payout", "reporting", "data", "payments", "reportRequestGuid", "/era/v1/payout/payments/{requestReportGuid}"]
procedures: 0
codeExamples: 0
---

Retrieving the payout reporting data by payment is a two-step process. You must:

1. Send a `POST` request to the `/era/v1/payout/payments/day` endpoint to create a request for payout reporting data organized by payment for the restaurants in a management group. The response is the `reportRequestGuid`, the unique request identifier.



> **Note**
> 
> The analytics API currently only supports retrieving payout by payments reporting data for the `day` time range.


For more information, see [Creating a request for payout reporting data by payments](apiDevGuide-apiAnalyticsPayoutByPaymentsReportingData#apiAnalyticsPayoutByPaymentsReportingDataCreateRequest).


2. Send a `GET` request to the `/era/v1/payout/payments/&#123;requestReportGuid&#125;` endpoint to retrieve the payout reporting data organized by payments. For more information, see [Retrieving the payout reporting data by payments](apiDevGuide-apiAnalyticsPayoutByPaymentsReportingData#apiAnalyticsPayoutByPaymentsReportingDataRetrieveData).



## Creating a request for payout reporting data by payments

Send a `POST` request to the `/era/v1/payout/payments/&#123;timeRange&#125;` endpoint to request payout reporting data organized by payments for a single day. The rate limit for this endpoint and method type is five requests per minute and 60 requests per day. For more information about API rate limits for the analytics API, see [Analytics API rate limits](apiDevGuide-apiAnalyticsRateLimiting).

You can limit the reporting data to inactive restaurants only using the `onlyInactiveRestaurants` query parameter. For more information, see [Viewing inactive restaurant data](apiDevGuide-apiAnalyticsInactiveRestaurantData).

To create a request for payout reporting data organized by payments, include the following:

- The `startDate` value in the message body, in `YYYYMMDD` format. This identifies the start date for the range of included payments. This value must match the `endDate` value.


- The `endDate` value in the message body, in `YYYYMMDD` format. This identifies the end date for the range of payment sales dates. This value must match the `startDate` value.


- The `restaurantIds` value in the message body. This identifies the only restaurants to include in the returned data using the restaurant GUID. All restaurants not listed are excluded from the returned data. Leave the `restaurantIds` value and the `excludedRestaurantIds` value empty to include all restaurants.


- The `excludedRestaurantIds` value in the message body. This identifies the only restaurants to exclude in the returned data using the restaurant GUID. All restaurants not listed are included in the returned data. Leave the `excludedRestaurantIds` value and the `restaurantIds` value empty to include all restaurants.





> **Important**
> 
> You can include restaurant GUIDs for either `restaurantIds` or `excludedRestaurantIds`but not for both. Listing restaurant GUIDs for both results in a 400 error or blank payout reporting data. They are contradictory values that cannot be used together.


### Request for payout reporting data by payments

The following example **curl** command sends a `POST` request to the `/era/v1/payout/payments/day` endpoint.


```
curl -i -X POST \ 'https://[toast-api-hostname]/era/v1/payout/payments/day' \
  -H 'Authorization: Bearer [token]' \
  -H 'Content-Type: application/json' \
  -d @[request-info].json \
```



    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e7575E4B1B8E9-CCDA-450F-BFEC-913D3B74A9DC" className="">(1)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Send a <code className="font-mono text-sm">POST</code> request to the <code className="font-mono text-sm">/era/v1/payout/payments/day</code> endpoint of the analytics API.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e7577E4B1B8E9-CCDA-450F-BFEC-913D3B74A9DC" className="">(2)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Include an authentication token. For more information, see <a href="apiDevGuide-authentication" className="">Authentication and restaurant access</a>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e7579E4B1B8E9-CCDA-450F-BFEC-913D3B74A9DC" className="">(3)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Set the data type of the message body to <code className="font-mono text-sm">application/json</code>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e7581E4B1B8E9-CCDA-450F-BFEC-913D3B74A9DC" className="">(4)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Include details about the requested payout reporting data organized by payments in the message body. The following example is the message body for this <strong className="font-semibold">curl</strong>  command example.</p></div></td>
    </tr>
### Message body for payout reporting data by payments

The following example shows the message body for creating a payout reporting data by payments request.


```
{
    "startDate": "20240710",
    "endDate": "20240710",
    "restaurantIds": ["95a96d7b-dbf5-46d3-98c5-c65c8ad18021"],
    "excludedRestaurantIds": []
}
```



    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e7623E4B1B8E9-CCDA-450F-BFEC-913D3B74A9DC" className="">(1)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The start date of the time range for the payout reporting data, in <code className="font-mono text-sm">YYYYMMDD</code> format.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e7625E4B1B8E9-CCDA-450F-BFEC-913D3B74A9DC" className="">(2)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The end date of the time range for the payout reporting data, in <code className="font-mono text-sm">YYYYMMDD</code> format. This is the same value as the start date.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e7627E4B1B8E9-CCDA-450F-BFEC-913D3B74A9DC" className="">(3)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The list of restaurant GUIDs from the management group to include in the payout reporting data. Restaurant GUIDs not listed are excluded.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e7629E4B1B8E9-CCDA-450F-BFEC-913D3B74A9DC" className="">(4)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The list of restaurant GUIDs from the management group to exclude from the payout reporting data by settled date. In this example, restaurants are included with the <code className="font-mono text-sm">restaurantIds</code> value, so all other restaurants are excluded automatically.</p></div></td>
    </tr>
### Response to request for payout reporting data by payments

The following example shows the response from the `/era/v1/payout/payments/day` endpoint.


```
"62bd5cf3-26c5-4fa8-8f51-15b3dd4d2e09"
```



    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e7670E4B1B8E9-CCDA-450F-BFEC-913D3B74A9DC" className="">(1)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The GUID for the payout reporting data by payments request, also called the <code className="font-mono text-sm">reportRequestGuid</code>. For more information about how to retrieve data using the analytics API, see <a href="apiDevGuide-apiAnalyticsUnderstandingProcess" className="">Understanding the analytics API process</a>.</p></div></td>
    </tr>
For an example that shows how to retrieve the payout reporting data by payments, see [Retrieving the payout reporting data by payments](apiDevGuide-apiAnalyticsPayoutByPaymentsReportingData#apiAnalyticsPayoutByPaymentsReportingDataRetrieveData).

## Retrieving the payout reporting data by payments

Send a `GET` request to the `/era/v1/payout/payments/&#123;reportRequestGuid&#125;` endpoint to retrieve payout reporting data organized by payments. The rate limit for this endpoint and method type is five requests per second and 30 requests per minute. For more information about API rate limits for the analytics API, see [Analytics API rate limits](apiDevGuide-apiAnalyticsRateLimiting).

### Request to retrieve payout reporting data by payments

The following example **curl** command sends a `GET` request to the `/era/v1/payout/payments/&#123;reportRequestGuid&#125;`endpoint.


```
curl -X GET \ 'https://[toast-api-hostname]/era/v1/payout/payments/
bc5279b0-a46d-4707-94e6-614edd31f2b3' \
  -H 'Authorization: Bearer [token]'
```



    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e7731E4B1B8E9-CCDA-450F-BFEC-913D3B74A9DC" className="">(1)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Send a <code className="font-mono text-sm">GET</code> request to the <code className="font-mono text-sm">/era/v1/payout/payments</code> endpoint of the analytics API.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e7733E4B1B8E9-CCDA-450F-BFEC-913D3B74A9DC" className="">(2)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Include the GUID for the payout reporting data organized by payments request, also called the <code className="font-mono text-sm">reportRequestGuid</code>. For more information about how to retrieve data using the analytics API, see <a href="apiDevGuide-apiAnalyticsUnderstandingProcess" className="">Understanding the analytics API process</a>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e7735E4B1B8E9-CCDA-450F-BFEC-913D3B74A9DC" className="">(3)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Include an authentication token. For more information, see <a href="apiDevGuide-authentication" className="">Authentication and restaurant access</a>.</p></div></td>
    </tr>
### Response to retrieval request for payout reporting data by payments

The following example shows the response from the `/era/v1/payout/payments/&#123;reportRequestGuid&#125;`endpoint.


```
[
    {
        "restaurantGuid": "95a96d7b-dbf5-46d3-98c5-c65c8ad18021",
        "restaurantName": "Grove Place Cafe",
        "restaurantLocationName": null,
        "restaurantLocationCode": "",
        "orderGuid": "e9b858ca-0694-4948-b97b-f80e0d2e72a1",
        "checkGuid": "05c8b87f-abb7-4c30-9b74-b936ee02162d",
        "paymentGuid": "36fdb0b7-5b66-49e3-b360-e0c10a497612",
        "settledDate": 20240702,
        "orderOpenDateTime": null,
        "paidDateTime": "2024-07-01 08:14:06",
        "paymentCardBrand": "Visa",
        "paymentCardType": "Credit",
        "tipAmount": 0.0,
        "gratuityAmount": 0.0,
        "paymentSubtotal": 1.39,
        "paymentTotal": 1.39
    },
    {
        "restaurantGuid": "95a96d7b-dbf5-46d3-98c5-c65c8ad18021",
        "restaurantName": "Grove Place Cafe",
        "restaurantLocationName": null,
        "restaurantLocationCode": "",
        "orderGuid": "7f0d83dc-04cc-4c0f-98ab-fb3fe34dae77",
        "checkGuid": "01f7500c-add4-42f6-96c0-ad6f2c9832cf",
        "paymentGuid": "01f7500c-add4-42f6-96c0-ad6f2c9832cf",
        "settledDate": 20240702,
        "orderOpenDateTime": null,
        "paidDateTime": "2024-07-01 22:57:44",
        "paymentCardBrand": "AMEX",
        "paymentCardType": "Credit",
        "tipAmount": 0.01,
        "gratuityAmount": 0.0,
        "paymentSubtotal": 1.39,
        "paymentTotal": 1.4
    },
    {
        "restaurantGuid": "95a96d7b-dbf5-46d3-98c5-c65c8ad18021",
        "restaurantName": "Grove Place Cafe",
        "restaurantLocationName": null,
        "restaurantLocationCode": "",
        "orderGuid": "7ddda484-72e6-4c6b-bdf2-10ab4f4bf66c",
        "checkGuid": "415fc617-9a52-43a2-b9d0-938f0d4ae2c7",
        "paymentGuid": "eb2f462a-d442-4707-94a3-38b2d93146e1",
        "settledDate": 20240702,
        "orderOpenDateTime": null,
        "paidDateTime": "2024-07-01 21:45:41",
        "paymentCardBrand": "Discover",
        "paymentCardType": "Credit",
        "tipAmount": 0.01,
        "gratuityAmount": 0.0,
        "paymentSubtotal": 1.39,
        "paymentTotal": 1.4
    }
]
```

## Understanding the payout reporting data by payments

Payout reporting data by payment contains objects that correspond to each available restaurant and payment combination. You can also choose to retrieve data for currently inactive restaurants. For more information, see [Viewing inactive restaurant data](apiDevGuide-apiAnalyticsInactiveRestaurantData).

The restaurants included in the payout reporting data organized by payments can be limited using either the `restaurantIds`or `excludedRestaurantIds` value in the message body. You can include restaurant GUIDs for only one of these values. Any restaurants listed with the `restaurantIds` value are included in the payout reporting data, with any restaurants not listed excluded. Any restaurants listed with the `excludedRestaurantIds` value are excluded from the payout reporting data, with any restaurants not listed included. When both are left blank, all restaurants are included automatically.

The following table specifies the returned set of values in the payout reporting data organized by payments. The values are listed in the order they appear in the response.


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
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">orderGuid</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4">The identifier assigned by the Toast platform used to identify an order. This is the order associated with the payment.</div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">checkGuid</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4">The identifier assigned by the Toast platform used to identify a check. This is the check associated with the payment.</div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">paymentGuid</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4">The identifier assigned by the Toast platform used to identify the payment.</div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">settledDate</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The date when the payouts associated with the payment were either processed or settled.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">orderOpenDateTime</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The date and time when the order associated with the payment was opened.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">paidDateTime</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The date and time when the order associated with the payment was paid.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">paymentCardBrand</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The brand or card provider of the card used to complete the payment. </p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">paymentCardType</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The payment type used by the card completing the payment. The type can be one of the following values:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">Credit</code>: A credit card was used to complete the payment.</p></li><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">Debit</code>: A debit card was used to complete the payment.</p></li><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">UNSPECIFIED CARD</code>: The card type is neither credit or debit, or cannot be identified.</p></li></ul></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">tipAmount</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The tip amount added to the payment.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">gratuityAmount</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The gratuity amount added to the payment.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">paymentSubtotal</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The total payment amount before tip and gratuity.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">paymentTotal</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The total payment amount, including tip, and gratuity.</p></div></td>
    </tr>
  </tbody>
</table>
</div>

