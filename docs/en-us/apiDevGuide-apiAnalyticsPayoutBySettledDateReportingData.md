---
title: "Payout reporting data by settled date"
id: apiAnalyticsPayoutBySettledDateReportingData
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiAnalyticsPayoutReportingDataOmitChunkFromSearchIndex.md
parentSectionTitle: "Payout reporting data"
previousSectionFile: apiDevGuide-apiAnalyticsPayoutReportingDataOmitChunkFromSearchIndex.md
previousSectionTitle: "Payout reporting data"
nextSectionFile: apiDevGuide-apiAnalyticsPayoutByPaymentsReportingData.md
nextSectionTitle: "Payout reporting data by payments"
excerpt: "Retrieving the payout reporting data by settled date is a two-step process. You must:"
keywords: [payout,reporting,data,settled,date,/era/v1/payout/{timeRange},reportRequestGuid,/era/v1/payout/{requestReportGuid}]
procedures: 0
codeExamples: 0
---

### Payout reporting data by settled date

Retrieving the payout reporting data by settled date is a two-step process. You must:

1. Send a `POST` request to the `/era/v1/payout/{timeRange}` endpoint to create a request for payout reporting data organized by settled date for the restaurants in a management group. The response is the `reportRequestGuid`, the unique request identifier. The analytics API supports retrieving payout reporting data for the day, week, and month time ranges. For more information, see [Creating a request for payout reporting data by settled date](apiAnalyticsPayoutBySettledDateReportingData.html#apiAnalyticsPayoutBySettledDateReportingDataCreateRequest).


2. Send a `GET` request to the `/era/v1/payout/{requestReportGuid}` endpoint to retrieve the payout reporting data organized by settled date. For more information, see [Retrieving the payout reporting data by settled date](apiAnalyticsPayoutBySettledDateReportingData.html#apiAnalyticsPayoutBySettledDateReportingDataRetrieveData).



#### Creating a request for payout reporting data by settled date

Send a `POST` request to the `/era/v1/payout/{timeRange}` endpoint to request payout reporting data organized by settled date for that specific time range. The `timeRange` can be `day`, `week`, or `month`. The type of time range you use determines the rate limit for this endpoint and method type. The rate limit for `month` time ranges is 10 requests per hour. The rate limit for `day` and `week` time ranges is 10 requests per minute and 60 requests per hour. For more information about API rate limits for the analytics API, see [Analytics API rate limits](apiAnalyticsOmitChunkFromSearchIndex.html#apiAnalyticsRateLimiting).

You can limit the reporting data to inactive restaurants only using the `onlyInactiveRestaurants` query parameter. For more information, see [Viewing inactive restaurant data](apiAnalyticsOmitChunkFromSearchIndex.html#apiAnalyticsInactiveRestaurantData).

To create a request for payout reporting data organized by settled date, include the following:

- The `startDate` value in the message body, in `YYYYMMDD` format. This identifies the start date for the range of payout settled dates. This value must match the `endDate` value if using the `day` time range.


- The `endDate` value in the message body, in `YYYYMMDD` format. This identifies the end date for the range of payout settled dates. This value must match the `startDate` value if using the `day` time range.


- The `restaurantIds` value in the message body. This identifies the only restaurants to include in the returned data using the restaurant GUID. All restaurants not listed are excluded from the returned data. Leave the `restaurantIds` value and the `excludedRestaurantIds` value empty to include all restaurants.


- The `excludedRestaurantIds` value in the message body. This identifies the only restaurants to exclude in the returned data using the restaurant GUID. All restaurants not listed are included in the returned data. Leave the `excludedRestaurantIds` value and the `restaurantIds` value empty to include all restaurants.





> **Important**
> 
> You can include restaurant GUIDs for either `restaurantIds` or `excludedRestaurantIds` but not for both. Listing restaurant GUIDs for both results in a 400 error or blank payout reporting data. They are contradictory values that cannot be used together.


##### Request for payout reporting data by settled date

The following example **curl** command sends a `POST` request to the `/era/v1/payout/{timeRange}` endpoint. This example uses the `day` time range.

```
curl -i -X POST \ 'https://[toast-api-hostname]/era/v1/payout/day' \[(1)](apiDevGuide-apiAnalyticsPayoutBySettledDateReportingData.html#d1e6955E4B1B8E9-CCDA-450F-BFEC-913D3B74A9DC-co)
  -H 'Authorization: Bearer [token]' \[(2)](apiDevGuide-apiAnalyticsPayoutBySettledDateReportingData.html#d1e6957E4B1B8E9-CCDA-450F-BFEC-913D3B74A9DC-co)
  -H 'Content-Type: application/json' \[(3)](apiDevGuide-apiAnalyticsPayoutBySettledDateReportingData.html#d1e6959E4B1B8E9-CCDA-450F-BFEC-913D3B74A9DC-co)
  -d @[request-info].json \[(4)](apiDevGuide-apiAnalyticsPayoutBySettledDateReportingData.html#d1e6961E4B1B8E9-CCDA-450F-BFEC-913D3B74A9DC-co)
```



(1) Send a POST request to the /era/v1/payout/{timeRange} endpoint of the analytics API. The {timeRange} in this example is day.

(2) Include an authentication token. For more information, see Authentication and restaurant access.

(3) Set the data type of the message body to application/json.

(4) Include details about the requested payout reporting data, organized by settled date, in the message body. The following example is the message body for this curlcommand example.

##### Message body for payout reporting data by settled date

The following example shows the message body for creating a payout reporting data by settled date request.

```
{
    "startDate": "20240710",[(1)](apiDevGuide-apiAnalyticsPayoutBySettledDateReportingData.html#d1e7003E4B1B8E9-CCDA-450F-BFEC-913D3B74A9DC-co)
    "endDate": "20240710",[(2)](apiDevGuide-apiAnalyticsPayoutBySettledDateReportingData.html#d1e7005E4B1B8E9-CCDA-450F-BFEC-913D3B74A9DC-co)
    "restaurantIds": ["95a96d7b-dbf5-46d3-98c5-c65c8ad18021"],[(3)](apiDevGuide-apiAnalyticsPayoutBySettledDateReportingData.html#d1e7007E4B1B8E9-CCDA-450F-BFEC-913D3B74A9DC-co)
    "excludedRestaurantIds": [][(4)](apiDevGuide-apiAnalyticsPayoutBySettledDateReportingData.html#d1e7009E4B1B8E9-CCDA-450F-BFEC-913D3B74A9DC-co)
}
```



(1) The start date of the time range for the payout reporting data, in YYYYMMDD format.

(2) The end date of the time range for the payout reporting data, in YYYYMMDD format. This is the same value as the start date for the day time range.

(3) The list of restaurant GUIDs from the management group to include in the payout reporting data. Restaurant GUIDs not listed are excluded.

(4) The list of restaurant GUIDs from the management group to exclude from the payout reporting data by settled date. In this example, restaurants are included with the restaurantIds value, so all other restaurants are excluded automatically.

##### Response to request for payout reporting data by settled date

The following example shows the response from the `/era/v1/payout/day` endpoint.

```
"bc5279b0-a46d-4707-94e6-614edd31f2b3"[(1)](apiDevGuide-apiAnalyticsPayoutBySettledDateReportingData.html#d1e7053E4B1B8E9-CCDA-450F-BFEC-913D3B74A9DC-co)
```



(1) The GUID for the payout reporting data by settled date request, also called the reportRequestGuid. For more information about how to retrieve data using the analytics API, see Understanding the analytics API process.

For an example that shows how to retrieve the payout reporting data by settled date, see [Retrieving the payout reporting data by settled date](apiAnalyticsPayoutBySettledDateReportingData.html#apiAnalyticsPayoutBySettledDateReportingDataRetrieveData).

#### Retrieving the payout reporting data by settled date

Send a `GET` request to the `/era/v1/payout/{reportRequestGuid}` endpoint to retrieve payout reporting data organized by settled date. The rate limit for this endpoint and method type is five requests per second and 30 requests per minute. For more information about API rate limits for the analytics API, see [Analytics API rate limits](apiAnalyticsOmitChunkFromSearchIndex.html#apiAnalyticsRateLimiting).

##### Request to retrieve payout reporting data by settled date

The following example **curl** command sends a `GET` request to the `/era/v1/payout/{reportRequestGuid}` endpoint.

```
curl -X GET \ 'https://[toast-api-hostname]/era/v1/payout/[(1)](apiDevGuide-apiAnalyticsPayoutBySettledDateReportingData.html#d1e7114E4B1B8E9-CCDA-450F-BFEC-913D3B74A9DC-co)
bc5279b0-a46d-4707-94e6-614edd31f2b3' \[(2)](apiDevGuide-apiAnalyticsPayoutBySettledDateReportingData.html#d1e7116E4B1B8E9-CCDA-450F-BFEC-913D3B74A9DC-co)
  -H 'Authorization: Bearer [token]'[(3)](apiDevGuide-apiAnalyticsPayoutBySettledDateReportingData.html#d1e7118E4B1B8E9-CCDA-450F-BFEC-913D3B74A9DC-co)
```



(1) Send a GET request to the /era/v1/payout endpoint of the analytics API.

(2) Include the GUID for the payout reporting data organized by settled date request, also called the reportRequestGuid. For more information about how to retrieve data using the analytics API, see Understanding the analytics API process.

(3) Include an authentication token. For more information, see Authentication and restaurant access.

##### Response to retrieval request for payout reporting data by settled date

The following example shows the response from the `/era/v1/payout/{reportRequestGuid}` endpoint.

```
[
    {
        "restaurantGuid": "95a96d7b-dbf5-46d3-98c5-c65c8ad18021",
        "restaurantName": "Grove Place Cafe",
        "restaurantLocationName": null,
        "restaurantLocationCode": "",
        "settledDate": "20240710",
        "salesPeriodStartDateTime": "2024-07-09 12:53:55",
        "salesPeriodEndDateTime": "2024-07-09 22:47:59",
        "transactionCount": 19,
        "paymentAmount": 26.54,
        "refundAmount": 23.74,
        "totalFeeAmount": 2.85,
        "withholdingAmount": 0.0,
        "payoutAmount": -0.05,
        "payoutStatus": "CAPTURED"
    }
]
```

#### Understanding the payout reporting data by settled date

Payout reporting data by settled date contains objects that correspond to each available restaurant and settled payout date combination. You can also choose to retrieve data for currently inactive restaurants. For more information, see [Viewing inactive restaurant data](apiAnalyticsOmitChunkFromSearchIndex.html#apiAnalyticsInactiveRestaurantData).

The restaurants included in the payout reporting data organized by settled date can be limited using either the `restaurantIds` or `excludedRestaurantIds` value in the message body. You can include restaurant GUIDs for only one of these values. Any restaurants listed with the `restaurantIds` value are included in the payout reporting data, with any restaurants not listed excluded. Any restaurants listed with the `excludedRestaurantIds` value are excluded from the payout reporting data, with any restaurants not listed included. When both are left blank, all restaurants are included automatically.

The following table specifies the returned set of values in the payout reporting data organized by settled date. The values are listed in the order they appear in the response.

| Value name | Definition | 
| --- | --- |
| `restaurantGuid` | The unique identifier assigned to the restaurant by the Toast platform. | 
| `restaurantName` | The restaurant’s name. | 
| `restaurantLocationName` | The restaurant’s location name. | 
| `restaurantLocationCode` | The restaurant’s location code. | 
| `settledDate` | The date when the payout was either processed or settled. | 
| `salesPeriodStartDateTime` | The date and time of the first payment included in the payout amount. | 
| `salesPeriodEndDateTime` | The date and time of the last payment included in the payout amount. | 
| `transactionCount` | The number of transactions included in the payout. | 
| `paymentAmount` | The amount paid to the restaurant by guests using cards that contributes towards the payout amount. | 
| `refundAmount` | The amount refunded to guests by the restaurant that contributes towards the payout amount. | 
| `totalFeeAmount` | The amount paid or owed by the restaurant in fees that contributes towards the payout amount. An example is the processing fees charged by card providers on payments. | 
| `withholdingAmount` | The amount owed to Toast by the restaurant for products and services. For example, this includes Toast Capital, Fundraising, and Instant Deposit. | 
| `payoutAmount` | The amount to be deposited into the restaurant’s account. This amount is calculated by subtracting the `refundAmount`, `totalFeeAmount`, and `withholdingAmount` amounts from the `paymentAmount`. | 
| `payoutStatus` | The status of the payout. The status can be:- `CAPTURED`: Toast collected the guest card payments included in the `payoutAmount` successfully.
- `SENT`: Toast sent the `payoutAmount` to the bank. It may take some time to appear in the account.
- `NONE`: The payout failed, or the payout was made prior to January 10, 2024 and is unavailable.

 | 

