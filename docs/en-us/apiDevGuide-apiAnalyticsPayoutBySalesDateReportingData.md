---
title: "Payout reporting data by sales date"
id: apiAnalyticsPayoutBySalesDateReportingData
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiAnalyticsPayoutReportingDataOmitChunkFromSearchIndex.md
parentSectionTitle: "Payout reporting data"
previousSectionFile: apiDevGuide-apiAnalyticsPayoutByPaymentsReportingData.md
previousSectionTitle: "Payout reporting data by payments"
nextSectionFile: apiDevGuide-apiAnalyticsGuestDataOmitChunkFromSearchIndex.md
nextSectionTitle: "Guest reporting data"
excerpt: "Retrieving the payout reporting data by sales date is a two-step process. You must:"
keywords: ["payout", "reporting", "data", "sales", "date", "/era/v1/payout/sales-date/{timeRange}", "reportRequestGuid", "/era/v1/payout/sales-date/{requestReportGuid}"]
procedures: 0
codeExamples: 0
---

Retrieving the payout reporting data by sales date is a two-step
      process. You must:

1. Send a `POST` request to the
          `/era/v1/payout/sales-date/{timeRange}` endpoint to
          create a request for payout reporting data organized by sales date
          for the restaurants in a management group. The response is the
          `reportRequestGuid`, the unique request identifier. The
          analytics API supports retrieving payout reporting data for the day,
          week, and month time ranges. For more information, see [Creating a request for payout reporting data by sales
        date](apiDevGuide-apiAnalyticsPayoutBySalesDateReportingData#apiAnalyticsPayoutBySalesDateReportingDataCreateRequest).


2. Send a `GET` request to the
          `/era/v1/payout/sales-date/{requestReportGuid}` endpoint
          to retrieve the payout reporting data organized by sales date. For
          more information, see [Retrieving the payout reporting data by sales date](apiDevGuide-apiAnalyticsPayoutBySalesDateReportingData#apiAnalyticsPayoutBySalesDateReportingDataRetrieveData).



## Creating a request for payout reporting data by sales
        date

Send a `POST` request to the
        `/era/v1/payout/sales-date/{timeRange}` endpoint to request
        payout reporting data organized by sales date for that specific time
        range. The `timeRange` can be `day`,
        `week`, or `month`. The type of time range you
        use determines the rate limit for this endpoint and method type. The
        rate limit for `month` time ranges is 10 requests per hour.
        The rate limit for `day` and `week` time ranges
        is 10 requests per minute and 60 requests per hour. For more
        information about API rate limits for the analytics API, see [Analytics API rate limits](apiDevGuide-apiAnalyticsRateLimiting).

You can limit the reporting data to inactive restaurants only
        using the `onlyInactiveRestaurants` query parameter. For
        more information, see [Viewing inactive restaurant data](apiDevGuide-apiAnalyticsInactiveRestaurantData).

To create a request for payout reporting data organized by sales
        date, include the following:

- The `startDate` value in the message body, in
            `YYYYMMDD` format. This identifies the start date for
            the range of payment sales dates. This value must match the
            `endDate` value if using the `day` time
            range.


- The `endDate` value in the message body, in
            `YYYYMMDD` format. This identifies the end date for the
            range of payment sales dates. This value must match the
            `startDate` value if using the `day` time
            range.


- The `restaurantIds` value in the message body.
            This identifies the only restaurants to include in the returned
            data using the restaurant GUID. All restaurants not listed are
            excluded from the returned data. Leave the
            `restaurantIds` value and the
            `excludedRestaurantIds` value empty to include all
            restaurants.


- The `excludedRestaurantIds` value in the message
            body. This identifies the only restaurants to exclude in the
            returned data using the restaurant GUID. All restaurants not
            listed are included in the returned data. Leave the
            `excludedRestaurantIds` value and the
            `restaurantIds` value empty to include all
            restaurants.





> **Important**
> 
> You can include restaurant GUIDs for either
          `restaurantIds` or `excludedRestaurantIds` but
          not for both. Listing restaurant GUIDs for both results in a 400
          error or blank payout reporting data. They are contradictory values
          that cannot be used together.


### Request for payout reporting data by sales date

The following example **curl** command sends a
          `POST` request to the
          `/era/v1/payout/sales-date/{timeRange}` endpoint. This
          example uses the `day` time range.

```
curl -i -X POST \ 'https://[toast-api-hostname]/era/v1/payout/sales-date/day' \
  -H 'Authorization: Bearer [token]' \
  -H 'Content-Type: application/json' \
  -d @[request-info].json \
```



(1) Send a POST request to the
              /era/v1/payout/sales-date/{timeRange} endpoint of
              the analytics API. The {timeRange} in this example
              is day.

(2) Include an authentication token. For more information, see
              Authentication and restaurant access.

(3) Set the data type of the message body to
              application/json.

(4) Include details about the requested payout reporting data
              organized by sales date in the message body. The following
              example is the message body for this curl
              command example.

### Message body for payout reporting data by sales date

The following example shows the message body for creating a
          payout reporting data by sales date request.

```
{
    "startDate": "20240710",
    "endDate": "20240710",
    "restaurantIds": ["95a96d7b-dbf5-46d3-98c5-c65c8ad18021"],
    "excludedRestaurantIds": []
}
```



(1) The start date of the time range for the payout reporting
              data, in YYYYMMDD format.

(2) The end date of the time range for the payout reporting
              data, in YYYYMMDD format. This is the same value as
              the start date for the day time range.

(3) The list of restaurant GUIDs from the management group to
              include in the payout reporting data. Restaurant GUIDs not
              listed are excluded.

(4) The list of restaurant GUIDs from the management group to
              exclude from the payout reporting data organized by sales date.
              In this example, restaurants are included with the
              restaurantIds value, so all other restaurants are
              excluded automatically.

### Response to request for payout reporting data by sales
          date

The following example shows the response from the
          `/era/v1/payout/sales-date/day` endpoint.

```
"bc5279b0-a46d-4707-94e6-614edd31f2b3"
```



(1) The GUID for the payout reporting data organized by sales
              date request, also called the reportRequestGuid.
              For more information about how to retrieve data using the
              analytics API, see Understanding the analytics API process.

For an example that shows how to retrieve the payout reporting
          data by sales date, see [Retrieving the payout reporting data by sales date](apiDevGuide-apiAnalyticsPayoutBySalesDateReportingData#apiAnalyticsPayoutBySalesDateReportingDataRetrieveData).

## Retrieving the payout reporting data by sales date

Send a `GET` request to the
        `/era/v1/payout/sales-date/{reportRequestGuid}` endpoint to
        retrieve payout reporting data organized by sales date. The rate limit
        for this endpoint and method type is five requests per second and 30
        requests per minute. For more information about API rate limits for
        the analytics API, see [Analytics API rate limits](apiDevGuide-apiAnalyticsRateLimiting).

### Request to retrieve payout reporting data by sales
          date

The following example **curl** command sends a
          `GET` request to the
          `/era/v1/payout/sales-date/{reportRequestGuid}`
          endpoint.

```
curl -X GET \ 'https://[toast-api-hostname]/era/v1/payout/sales-date/
bc5279b0-a46d-4707-94e6-614edd31f2b3' \
  -H 'Authorization: Bearer [token]'
```



(1) Send a GET request to the
              /era/v1/payout/sales-date endpoint of the analytics
              API.

(2) Include the GUID for the payout reporting data organized
              by sales date request, also called the
              reportRequestGuid. For more information about how
              to retrieve data using the analytics API, see Understanding the analytics API process.

(3) Include an authentication token. For more information, see
              Authentication and restaurant access.

### Response to retrieval request for payout reporting data by
          sales date

The following example shows the response from the
          `/era/v1/payout/sales-date/{reportRequestGuid}`
          endpoint.

```
[
    {
        "restaurantGuid": "95a96d7b-dbf5-46d3-98c5-c65c8ad18021",
        "restaurantName": "Grove Place Cafe",
        "restaurantLocationName": null,
        "restaurantLocationCode": "",
        "salesDate": "20240723",
        "settledDates": [
            "20240724"
        ],
        "transactionCount": 9,
        "paymentAmount": 12.58,
        "refundAmount": 9.79,
        "totalFeeAmount": 1.35,
        "withholdingAmount": 0.0,
        "payoutAmount": 1.44
    }
]

```

## Understanding the payout reporting data by sales date

Payout reporting data by sales date contains objects that
        correspond to each available restaurant and sales date combination.
        You can also choose to retrieve data for currently inactive
        restaurants. For more information, see [Viewing inactive restaurant data](apiDevGuide-apiAnalyticsInactiveRestaurantData).

The restaurants included in the payout reporting data organized
        by sales date can be limited using either the
        `restaurantIds` or `excludedRestaurantIds` value
        in the message body. You can include restaurant GUIDs for only one of
        these values. Any restaurants listed with the
        `restaurantIds` value are included in the payout reporting
        data, with any restaurants not listed excluded. Any restaurants listed
        with the `excludedRestaurantIds` value are excluded from
        the payout reporting data, with any restaurants not listed included.
        When both are left blank, all restaurants are included
        automatically.

The following table specifies the returned set of values in the
        payout reporting data organized by sales date. The values are listed
        in the order they appear.

| Value name | Definition | 
| --- | --- |
| `restaurantGuid` | The unique identifier assigned to the
                  restaurant by the Toast platform. | 
| `restaurantName` | The restaurant’s name. | 
| `restaurantLocationName` | The restaurant’s location name. | 
| `restaurantLocationCode` | The restaurant’s location code. | 
| `salesDate` | The date when the payment was completed.
                   | 
| `settledDate` | The date when the payouts associated with the
                  payment were either processed or settled. | 
| `transactionCount` | The number of transactions made on the sales
                  date. | 
| `paymentAmount` | The amount paid to the restaurant by guests
                  using cards on the sales date. | 
| `refundAmount` | The amount refunded to guests by the restaurant
                  for payments made on the sales date. | 
| `totalFeeAmount` | The amount paid or owed by the restaurant in
                  fees associated with payments made on the sales date. An
                  example is the processing fees charged by card providers on
                  payments. | 
| `withholdingAmount` | The amount owed to Toast by the restaurant for
                  products and services. For example, this includes Toast
                  Capital, Fundraising, and Instant Deposit. | 
| `payoutAmount` | The amount to be deposited into the
                  restaurant’s account associated with the sales date. This
                  amount is calculated by subtracting the
                  `refundAmount`, `totalFeeAmount`, and
                  `withholdingAmount` from the
                  `paymentAmount`. | 

