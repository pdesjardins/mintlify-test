---
title: "Calculating order wait time"
id: calculatingOrderWaitTime
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-portalCreatingAndUpdatingOrdersOmitChunkFromSearchIndex.md
parentSectionTitle: "Updating order information"
previousSectionFile: apiDevGuide-orders_api_future_orders.md
previousSectionTitle: "Scheduling future orders"
nextSectionFile: apiDevGuide-apiAddingItemsToACheck.md
nextSectionTitle: "Adding items to an existing check"
excerpt: "When you use the orders API to create an order, the orders API does not validate the time when you submit the order. The orders API accepts the order even if, for example, the restaurant is not..."
keywords: ["promisedDate", "estimatedFulfillmentDate"]
procedures: 0
codeExamples: 0
---

When you use the orders API to create an order, the orders API does not validate the time when you submit the order. The orders API accepts the order even if, for example, the restaurant is not currently open, is not currently accepting online orders, or will close before the order can be fulfilled.

You can use information from the restaurant configuration to:

- Determine when the restaurant is open and is accepting online orders.


- For as soon as possible (ASAP) orders, estimate the amount of time that the guest will wait until a delivery order arrives or a takeout order is available.


- For scheduled orders, ensure that the `promisedDate`that you provide is realistic.



When you use the orders API to create the order, the `estimatedFulfillmentDate` value in the response indicates when the order will be fulfilled. The algorithm that the Toast platform uses to set `estimatedFulfillmentDate` includes the configured restaurant quotes times, hours, and throttling.

## Restaurant configuration settings that affect order wait time

A restaurant uses Toast Web or a Toast POS device to configure the following settings that affect order wait times:



****Quote times for takeout and delivery****
: The restaurant sets a default quote time for takeout and delivery orders. The quote time indicates how long it usually takes to fulfill a takeout or delivery order.

For example, a takeout order by default might take 25 minutes, and a delivery order by default might take one hour.



****Throttling times for takeout and delivery****
: In response to an unexpected surge in takeout or delivery orders, the restaurant can add throttling time to the original quote time.

For example, when the restaurant is busy, takeout orders might take an additional 10 minutes. If the default quote time for a takeout order is 25 minutes, then the total preparation time is 35 minutes.



****Restaurant hours of operation****
: Each restaurant configures the hours when it is open for business.



****Restaurant hours for online ordering****
: Restaurants that use Toast Online Ordering can configure when they accept online takeout and delivery orders. These times might be different from the restaurant's hours of operation.

For example, a restaurant is open from 11:00 AM to 9:00 PM. However, they only take online delivery orders from 4:00 PM to 8:00 PM, and online takeout orders from 12:00 PM to 8:00 PM.





## Retrieving the configured preparation time and hours of operation

To retrieve information about the restaurant configuration, including the quote times, throttling times, and the restaurant hours of operation, send a `GET` request to the `/restaurants/\{restaurantGUID\}` endpoint of the restaurants API.

### Takeout and delivery quote and throttling times

In the response to the `GET` request to the `/restaurants/\{restaurantGUID\}/` endpoint, the `prepTimes` object contains the current quote time and throttling time configurations.

- The `deliveryPrepTime` and `takeoutPrepTime` values contain the delivery and takeout quote times.


- The `deliveryThrottlingTime` and `takeoutThrottlingTime` values contain the current delivery and takeout throttling times.



The following example shows the `prepTimes` object from the response from a `GET` request to the `/restaurants/\{restaurantGUID\}` endpoint of the restaurants API.

**Example 2.5. Example takeout and delivery preparation and throttling time configuration from the restaurants API**

```
  "prepTimes": \{
    "deliveryPrepTime": 60,
    "deliveryThrottlingTime": 0,
    "takeoutPrepTime": 30,
    "takeoutThrottlingTime": 0,
    "deliveryTimeAfterOpen": 0,
    "deliveryTimeBeforeClose": 0,
    "takeoutTimeAfterOpen": 0,
    "takeoutTimeBeforeClose": 0
  \}
```



(1) The amount of time, in minutes, that it takes to prepare and deliver a delivery order.

(2) The amount of time, in minutes, that restaurant employees have chosen to delay delivery orders from firing. The throttling time allows restaurant employees to handle a temporary surge in orders.

(3) The amount of time, in minutes, that it takes to prepare a takeout order.

(4) The amount of time, in minutes, that restaurant employees have chosen to delay takeout orders from firing. The throttling time allows restaurant employees to handle a temporary surge in orders.

(5) The deliveryTimeAfterOpen, deliveryTimeBeforeClose, takeoutTimeAfterOpen, and takeoutTimeBeforeClose settings are discontinued. They cannot be configured in the Toast platform. In the response from the restaurants API, the values are always 0.

  
### Restaurant opening and closing times

In the response to the `GET` request to the `/restaurants/\{restaurantGUID\}` endpoint of the restaurants API, the `schedules` value contains information about when the restaurant is open for business.

The following example shows the `schedules` value with the opening and closing time values.

**Example 2.6. Example of daily opening and closing times in the response from the restaurants API**

```
"schedules": \{
  "daySchedules": \{
    "1495000000000023": \{
      "scheduleName": "Weekdays",
      "services": [
        
        [contents omitted]
      ],
      "openTime": "06:00:00.000",
      "closeTime": "02:00:00.000"
    },
    "1495000000000024": \{
      "scheduleName": "Weekends",
      "services": [
        
        [contents omitted]
        
      ],
      "openTime": "11:00:00.000",
      "closeTime": "05:00:00.000"
    }
  },
  "weekSchedule": \{
    "monday": "1495000000000023",
    "tuesday": "1495000000000023",
    "wednesday": "1495000000000023",
    "thursday": "1495000000000023",
    "friday": "1495000000000023",
    "saturday": "1495000000000024",
    "sunday": "1495000000000024"
  \}
\}
```



(1) The identifier of a one-day schedule configured for a restaurant. Each schedule can then be assigned to one or more days of the week.

(2) The time that the restaurant opens on days that use this day schedule. Times are expressed in 24-hour format. For days that use this schedule, the restaurant opens at 6:00 AM.

(3) The time that the restaurant closes on days that use this day schedule. Times are expressed in 24-hour format. For days that use this schedule, the restaurant closes at 2:00 AM.

(4) The identifier of another one-day schedule configured for a restaurant.

(5) The time that the restaurant opens on days that use this day schedule. Times are expressed in 24-hour format. For days that use this schedule, the restaurant opens at 11:00 AM.

(6) The time that the restaurant closes on days that use this day schedule. Times are expressed in 24-hour format. For days that use this schedule, the restaurant closes at 5:00 AM.

(7) The identifier of the day schedule that is used on this day of the week. The day of the week is determined by the local time zone of the restaurant.

(8) The identifier of the day schedule that is used on this day of the week. The day of the week is determined by the local time zone of the restaurant.

  
### Restaurant online ordering hours

Restaurants that use Toast Online Ordering can configure when they accept online orders. The restaurant can have different hours for online and takeout orders. They can also configure specific exceptions to those hours.

To see the current hours for online delivery and takeout orders, send a `GET` request to the `/orderingSchedule`endpoint of the order management configuration API.

For more information, see [Getting online ordering schedules](apiDevGuide-apiGettingOnlineOrderingSchedules).

## Estimating takeout order wait time

To calculate the estimated takeout order wait time, you add the amount of time it takes to prepare takeout orders and the amount of time that restaurant employees have chosen to delay takeout order firing.

- `takeoutPrepTime` - The time it takes to prepare a takeout order.


- `takeoutThrottlingTime` - The time that restaurant employees have chosen to delay takeout orders.



For example, if `takeoutPrepTime` is 25 minutes, and `takeoutThrottlingTime` is 10 minutes, then the total estimated order wait time is 35 minutes.

If the current time is outside of the restaurant's hours of operation, then you must include the amount of time until the restaurant is open. You can use the restaurant `openTime` and `closeTime` values to determine whether takeout service is available. For example, if the current time is 10:00 AM, but the restaurant does not accept open or accept online takeout orders until 12:00 PM, then you need to add two hours to the order wait time.

For a scheduled order, you must also make sure that `promisedDate` is within the allowed maximum amount of time for future orders. For example, a restaurant might not accept scheduled orders for a date that is more than two weeks in the future.

## Estimating delivery order wait time

To calculate the estimated delivery order wait time, you add the amount of time it takes to prepare delivery orders and the amount of time that restaurant employees have chosen to delay delivery order firing.

- `deliveryPrepTime` - The time it takes to prepare and deliver a delivery order.


- `deliveryThrottlingTime` - the time that restaurant employees have chosen to delay delivery orders.



For example, if `deliveryPrepTime` is 50 minutes, and `deliveryThrottlingTime` is 10 minutes, then the total estimated order wait time is 60 minutes.

If the current time is outside of the restaurant's hours of operation, then you must include the amount of time until the restaurant is open. You can use the restaurant `openTime` and `closeTime` values to determine whether delivery service is available. For example, if the current time is 10:00 AM, but the restaurant does not open or accept delivery orders until 12:00 PM, then you need to add two hours to the order wait time.

For a scheduled order, you must also make sure that `promisedDate` is within the allowed maximum amount of time for future orders. For example, a restaurant might not accept scheduled orders for a date that is more than two weeks in the future.

