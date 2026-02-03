---
title: "Aggregating the aggregated sales reporting data"
id: apiAnalyticsMetricsReportingDataAggregation
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiAnalyticsMetricsReportingDataOmitChunkFromSearchIndex.md
parentSectionTitle: "Aggregated sales reporting data"
previousSectionFile: apiDevGuide-apiAnalyticsMetricsReportingDataRetrieveData.md
previousSectionTitle: "Retrieving the aggregated sales reporting data"
nextSectionFile: apiDevGuide-apiAnalyticsMetricsReportingDataUnderstandingData.md
nextSectionTitle: "Understanding aggregated sales reporting data"
excerpt: "The default way to view the..."
keywords: ["aggregating", "aggregated", "sales", "reporting", "data", "aggregateBy", "HOUR", "groupBy", "/era/v1/metrics/{timeRange}"]
procedures: 0
codeExamples: 0
---

The default way to view the aggregated sales reporting data is by day for each location. If you use the `day` time range, you can choose to view the data by hour for each location instead. Use the `aggregateBy` query parameter set to `HOUR` in the `/era/v1/metrics/day` request to organize the data by hour instead of day.

Optionally, you can choose to aggregate the data into subsections according to an order's dining option, order source, revenue center, or a combination of two of these values. Use the `groupBy` value in the message body of the `/era/v1/metrics` or `/era/v1/metrics/\{timeRange\}` request to create subsections organized by dining option, order source, revenue center, or a combination of two of these values.

#### Using the `aggregateBy` query parameter

The `aggregateBy` query parameter divides the metric data into either daily or hourly increments. Setting `aggregateBy` to `DAY` divides the order data into daily intervals and setting to `HOUR` divides the order data into hourly intervals. The data is aggregated by `DAY` by default. You can only aggregate by `HOUR` when using the `/era/v1/metrics/day`request.

The following example shows a `/era/v1/metrics/day`request that uses the `aggregateBy` query parameter set to `HOUR`:

```
curl -i -X POST \ 'https://`[toast-api-hostname]`/era/v1/metrics/day?aggregateBy=HOUR' \  
  -H 'Authorization: Bearer `[token]`' \
  -H 'Content-Type: application/json' \
  -d @`[request-info]`.json \

```



(1) Send a POST request to the /era/v1/metrics/\{timeRange\} endpoint of the analytics API. The \{timeRange\} is set to day.

(2) Use the aggregateBy query parameter set to HOUR to group the aggregated sales reporting data by hour instead of day.

(3) Include an authentication token. For more information, see Authentication and restaurant access.

(4) Set the data type of the message body to application/json.

(5) Include details about the requested aggregated sales reporting data in the message body. For an example of the message body, see Message body for the aggregated sales reporting data request using aggregateBy and groupBy.

When aggregating by day, the report splits the data into sections by day, which are organized from oldest to newest. For example, the following list shows the structure of aggregated sales reporting data, aggregated by day, for one example restaurant.

- Day 1


- Day 2


- Day 3



When aggregating by hour, the report splits the data into sections by hour, which are organized from oldest to newest. For example, the following list shows the structure of aggregated sales reporting data, aggregated by hour, for one example restaurant:

- Day 1, Hour 9


- Day 1, Hour 10


- Day 1, Hour 11


- Day 1, Hour 12


- Day 1, Hour 13


- Day 1, Hour 14





> **Note**
> 
> Aggregating by hour is only available to the `day`time range. Aggregating by hour results in the same day for each section, with each section representing a different hour.


The hour number corresponds to the 24 hours of the day, starting at `0` and ending at `23`. `0`represents the interval between 12 AM and 1 AM, `1`represents the interval between 1 AM and 2 AM, `2`represents the interval between 2 AM and 3 AM, and so on.

#### Using the `groupBy` value

The `groupBy` value in the message body of a `/era/v1/metrics` or `/era/v1/metrics/\{timeRange\}` request can group the returned data by the dining option associated with an order, the order source which is the method used to submit the order, the revenue center associated with an order, or a combination of two of these values. Use `DINING_OPTION` to group the aggregated sales reporting data by dining option, `ORDER_SOURCE` to group by order source, and `REVENUE_CENTER` to group by revenue center.

The following example shows the message body for a `/era/v1/metrics/week` request that uses the `groupBy` value with `DINING_OPTION`.

```
\{
  "startBusinessDate": "20220824",
  "endBusinessDate": "20220830",
  "restaurantIds": [
    "497f6eca-6276-4993-bfeb-53cbbbba6f08"
  ],
  "groupBy": [
    "DINING_OPTION"
  ]
\}

```



(1) The start date of the time range for the aggregated sales reporting data, in YYYYMMDD format.

(2) The end date of the time range for the aggregated sales reporting data, in YYYYMMDD format.

(3) The list of restaurant GUIDs from the management group to include in the aggregated sales reporting data. Restaurant GUIDs not listed are excluded.

(4) This request is for aggregated sales reporting data grouped by dining option.

When you use `DINING_OPTION`, the data is split into subsections by dining option, which are organized alphabetically by the dining option name, and then by day for that dining option. For example, the following list shows the structure of aggregated sales reporting data for one example restaurant, covering two days and two dining options.

- Day 1, Dining Option A


- Day 2, Dining Option A


- Day 1, Dining Option B


- Day 2, Dining Option B



When you use `ORDER_SOURCE`, the data is split into subsections by order source, which are organized alphabetically by the name of the order source, and then by day for that order source. For example, the following list shows the structure of aggregated sales reporting data for one example restaurant, covering two days and two order sources.

- Day 1, Order Source 1


- Day 2, Order Source 1


- Day 1, Order Source 2


- Day 2, Order Source 2



When you use `REVENUE_CENTER`, the data is split into subsections by revenue center, which are organized alphabetically by the revenue center name, and then by day for that revenue center. For example, the following list shows the structure of aggregated sales reporting data for one example restaurant, covering two days and two revenue centers.

- Day 1, Revenue Center A


- Day 2, Revenue Center A


- Day 1, Revenue Center B


- Day 2, Revenue Center B





> **Note**
> 
> If no revenue center is associated with an order, the revenue center name is `No Revenue Center`.


When grouping by both `DINING_OPTION` and `ORDER_SOURCE`, the data is split into subsections by dining option, then by order source, and finally by day. The order in which the options are listed does not affect the response. They are listed alphabetically by dining option and then order source. For example, the following list shows the structure of aggregated sales reporting data for one example restaurant covering two days, four dining options, and three order sources.

- Day 1, Dining Option 1, Order Source 1


- Day 2, Dining Option 1, Order Source 1


- Day 1, Dining Option 2, Order Source 2


- Day 2, Dining Option 2, Order Source 2


- Day 1, Dining Option 3, Order Source 2


- Day 2, Dining Option 3, Order Source 1


- Day 2, Dining Option 3, Order Source 2


- Day 1, Dining Option 4, Order Source 3



When grouping by both `DINING_OPTION` and `REVENUE_CENTER`, the data is split into subsections by dining option, then by revenue center, and finally by day. The order in which the options are listed does not affect the response. They are listed alphabetically by dining option and then revenue center. For example, the following list shows the structure of aggregated sales reporting data for one example restaurant covering two days, two revenue centers, and two dining options.

- Day 1, Revenue Center A, Dining Option A


- Day 2, Revenue Center A, Dining Option A


- Day 1, Revenue Center B, Dining Option A


- Day 2, Revenue Center B, Dining Option A


- Day 1, Revenue Center A, Dining Option B


- Day 2, Revenue Center B, Dining Option B



When grouping by both `ORDER_SOURCE` and `REVENUE_CENTER`, the data is split into subsections by revenue center, then by order source, and finally by day. The order in which the options are listed does not affect the response. The response lists each section alphabetically by revenue center and then order source. For example, the following list shows the structure of aggregated sales reporting data for one example restaurant covering two days, two revenue centers, and two order sources.

- Day 1, Revenue Center A, Order Source A


- Day 1, Revenue Center A, Order Source B


- Day 2, Revenue Center A, Order Source A


- Day 1, Revenue Center B, Order Source B


- Day 2, Revenue Center B, Order Source A


- Day 2, Revenue Center B, Order Source B



If the `groupBy` value uses two values and is used in conjunction with the `aggregateBy` query parameter set to `HOUR`, the aggregated sales reporting data is split into sections by hour, then by either dining option, revenue center, or order source respectively. For example, the aggregated sales reporting data for one example restaurant covering two hours, two dining options, and two revenue centers, is structured similarly to the following:

- Day 1, Revenue Center A, Dining Option A, Hour 8


- Day 1, Revenue Center B, Dining Option A, Hour 8


- Day 1, Revenue Center A, Dining Option B, Hour 8


- Day 1, Revenue Center B, Dining Option B, Hour 8


- Day 1, Revenue Center A, Dining Option A, Hour 9


- Day 1, Revenue Center B, Dining Option A, Hour 9


- Day 1, Revenue Center A, Dining Option B, Hour 9


- Day 1, Revenue Center B, Dining Option B, Hour 9



#### Example using `aggregateBy` and `groupBy`

This section includes examples of how to create a request for and retrieve aggregated sales reporting data that is aggregated into hourly intervals, and then grouped into subsections by dining option and revenue center for a single example restaurant.

##### Request for aggregated sales reporting data using `aggregateBy` and `groupBy`

The following example **curl** command sends a `POST` request to the `/era/v1/metrics/day` endpoint.

```
curl -i -X POST \ 'https://`[toast-api-hostname]`/era/v1/metrics/day?aggregateBy=HOUR' \
  -H 'Authorization: Bearer `[token]`' \
  -H 'Content-Type: application/json' \
  -d @`[request-info]`.json \

```



(1) Send a POST request to the /era/v1/metrics/\{timeRange\} endpoint of the analytics API. The \{timeRange\} in this example is day.

(2) Use the aggregateBy query parameter set to HOUR to group the aggregated sales reporting data by hour. For more information, see Using the aggregateBy query parameter.

(3) Include an authentication token. For more information, see Authentication and restaurant access.

(4) Set the data type of the message body to application/json.

(5) Include details about the requested aggregated sales reporting data in the message body. The following example is the message body for this curl command example.

##### Message body for the aggregated sales reporting data request using `aggregateBy` and `groupBy`

The following example shows the message body for the `/era/v1/metrics/day` request that uses the `groupBy` value with `DINING_OPTION` and `REVENUE_CENTER`.

```
\{
  "startBusinessDate": "20230201",
  "restaurantIds": [
    "43211888-2860-46c7-a8c8-32ba462e1280"
  ],
  "excludedRestaurantIds": [],
  "groupBy": [
    "DINING_OPTION", 
    "REVENUE_CENTER"
  ]
\}

```



(1) The start date of the time range for the aggregated sales reporting data, in YYYYMMDD format. The endBusinessDate value is optional for requests using the day time range.

(2) The list of restaurant GUIDs from the management group to include in the aggregated sales reporting data. Restaurant GUIDs not listed are excluded.

(3) The list of restaurant GUIDs from the management group to exclude from the aggregated sales reporting data. For this example, one restaurant is included, which excludes all other restaurants automatically.

(4) This request is for aggregated sales reporting data grouped by dining option and revenue center.



> **Important**
> 
> Adding restaurant GUIDs to both `restaurantIds`and `excludedRestaurantIds` results in an error. For more information, see [Creating a request for aggregated sales reporting data](apiAnalyticsMetricsReportingDataCreateRequest.html).


##### Response to the request for aggregated sales reporting data using `aggregateBy` and `groupBy`

The following example shows the response from the `/era/v1/metrics/day` endpoint.

```
"3a29d28e-171f-43d8-a36a-0a26fe65783d"
```



(1) The GUID for the aggregated sales reporting data request, also called the reportRequestGuid. For more information about how to retrieve data using the analytics API, see Understanding the analytics API process.

##### Request to retrieve the aggregated sales reporting data using `aggregateBy` and `groupBy`

The following example **curl** command sends a `GET` request to the `/era/v1/metrics/\{reportRequestGuid\}` endpoint.

```
curl -X GET \ 'https://`[toast-api-hostname]`/era/v1/metrics/
3a29d28e-171f-43d8-a36a-0a26fe65783d/' \
  -H 'Authorization: Bearer `[token]`'

```



(1) Send a GET request to the /era/v1/metrics endpoint of the analytics API.

(2) Include the GUID for the aggregated sales reporting data request, also called the reportRequestGuid. For more information about how to retrieve data using the analytics API, see Understanding the analytics API process.

(3) Include an authentication token. For more information, see Authentication and restaurant access.

##### Response to the retrieval request for aggregated sales reporting data using `aggregateBy` and `groupBy`

The following example shows the response from the `/era/v1/metrics/\{reportRequestGuid\}` endpoint.

```
[
    \{
        "restaurantGuid": "43211888-2860-46c7-a8c8-32ba462e1280",
        "businessDate": "20230201",
        [content omitted]
        "revenueCenter": "Bar",
        "diningOption": "Dine In",
        "businessHour": "7"
    },
    \{
        "restaurantGuid": "43211888-2860-46c7-a8c8-32ba462e1280",
        "businessDate": "20230201",
        "guestCount": 14,
        [content omitted]
        "revenueCenter": "Bar",
        "diningOption": "Take Out",
        "businessHour": "7"
    },
    \{
        "restaurantGuid": "43211888-2860-46c7-a8c8-32ba462e1280",
        "businessDate": "20230201",
        [content omitted]
        "revenueCenter": "Dining Room",
        "diningOption": "Take Out",
        "businessHour": "7"
    },
    \{
        "restaurantGuid": "43211888-2860-46c7-a8c8-32ba462e1280",
        "businessDate": "20230201",
        [content omitted]
        "revenueCenter": "No Revenue Center",
        "diningOption": "Take Out",
        "businessHour": "7"
    },
    \{
        "restaurantGuid": "43211888-2860-46c7-a8c8-32ba462e1280",
        "businessHour": "20230201",
        [content omitted]
        "revenueCenter": "Bar",
        "diningOption": "Dine In",
        "businessHour": "8"
    },
    \{
        "restaurantGuid": "43211888-2860-46c7-a8c8-32ba462e1280",
        "businessDate": "20230201",
        [content omitted]
        "revenueCenter": "Bar",
        "diningOption": "Take Out",
        "businessHour": "8"
    },
    \{
        "restaurantGuid": "43211888-2860-46c7-a8c8-32ba462e1280",
        "businessDate": "20230201",
        [content omitted]
        "revenueCenter": "Dining Room",
        "diningOption": "Take Out",
        "businessHour": "8"
    },
    \{
        "restaurantGuid": "43211888-2860-46c7-a8c8-32ba462e1280",
        "businessDate": "20230201",
        [content omitted]
        "revenueCenter": "No Revenue Center",
        "diningOption": "Take Out",
        "businessHour": "8"
    \},
    [content omitted]
]

```

