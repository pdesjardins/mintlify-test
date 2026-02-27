---
title: "Getting online ordering schedules"
id: apiGettingOnlineOrderingSchedules
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiGettingRestaurantInfoOmitChunkFromSearchIndex.md
parentSectionTitle: "Getting restaurant info"
previousSectionFile: apiDevGuide-apiRestaurantOnlineOrderingInfo.md
previousSectionTitle: "Online ordering configuration"
nextSectionFile: apiDevGuide-apiGettingRxOnlineOrderingAvailability.md
nextSectionTitle: "Getting a restaurant's online ordering availability"
externalReferences: [https://central.toasttab.com/s/article/How-do-I-set-up-my-take-out-and-delivery-options-1492745822028, https://central.toasttab.com/s/article/How-do-I-set-up-my-take-out-and-delivery-options-1492745822028#Enabling]
excerpt: "To retrieve a restaurant..."
keywords: ["GET", "/orderingSchedule", "Toast-Restaurant-External-ID", "DELIVERY", "TAKEOUT", "diningOptionBehavior", "scheduledOrderMaxDays", "TAKE_OUT"]
procedures: 0
codeExamples: 3
---

To retrieve a restaurant location's online ordering schedule, send a `GET` request to the `/orderingSchedule`endpoint of the order management configuration API. This endpoint returns a restaurant location’s online ordering hours for takeout, delivery, or both. The ordering schedule indicates the hours when a guest can place orders for immediate or future fulfillment.



> **Important**
> 
> Retrieve a restaurant's online ordering schedule at least once per day at the end of the business day. This ensures that you have up-to-date information about when online ordering hours begin and end on the next business day. [Future orders](apiDevGuide-orders_api_future_orders) must fall within a restaurant's ordering hours. You are responsible for respecting the restaurant’s hours. The orders API will not validate against these hours.


**Example 6.6. Request for a restaurant's online ordering schedule**

In the following example, you send a `GET` request to the `/orderingSchedule` endpoint with the `Toast-Restaurant-External-ID` to retrieve a restaurant location's online ordering schedule.


```
curl -X GET \
-H "Authorization: Bearer eyJzI1NiJ9hbGciOiJSU.eyJhd9yaXR5Ij
oiQ1JVTkNIVElNRSIsInJzR3VpZCI6IjE4YzQ5YWJlLWFlODItNGFlYy04ND
M1LWJhYTRjMjVlYTY2MiIsInNjb3BlIjpbImxWQiOlsidG9hc3QiXSwibmFt
aW5nQXV0aGhYm9yIiwib3JkZXJzIiwidXNlcm1nbXQiXSwiZXhwIjoxNDg0M
zg5ODUwLCJqdGkiOiJlMDYzZjJkMy1jNGYyLTRiZjItODJmNi01MTg1NWMzZ
DAxM2YiLCJjbGllbnRfaWQiOiJjcnVuY2h0aW1lIn0.X1_0y9Hzj5F9gdOw2
o6VSYTyZwooAJiFMDmNakbZrtiUdYwLzuLwLpCMQzX5pKYtOqDUz_cetGJL3
txKL1L-K2j1Enoq8An8hEM6e8J0KdAiwrYFO3W3CmWedaoz95K9ghNZVCs28
Td2Sp3Ix3fObxbrvanocx9_OT8S9uM8hdSXmBI_ykTWvOVgK4hO24V3DJy4b
9bz1FtgOvrClhELxCe8dJy7jiwAR60xczlCF5rna98RMLN6zY4ffjmljKFZ6
QV0KkVppWjEiJn7oFHiIylCX1sSg7sddrGatj0xJzts3GJ8u8_lryUNHaEvJ
dWq4Yzwo007AMgxjH9d241Y-g" \
-H "Toast-Restaurant-External-ID: 27d35c6a-7068-49f7-bee0-25e654e1227a"  \
"https://[toast-api-hostname]/ordermgmt-config/v1/published/orderingSchedule
```



    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e88264BB8911-6D33-427B-B2BF-261630CB0B01" className="">(1)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Include an authentication token. For more information, see <a href="apiDevGuide-authentication" className="">Authentication and restaurant access</a>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e88464BB8911-6D33-427B-B2BF-261630CB0B01" className="">(2)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Specify the location GUID of the restaurant whose online ordering schedule you want to retrieve.</p></div></td>
    </tr>
  
**Example 6.7. Response containing a restaurant's online ordering schedule**

The following example shows a restaurant location's online ordering schedule for both `DELIVERY` and `TAKEOUT` dining option behaviors. The `/orderingSchedule` endpoint returns an array of values configured in the [Online ordering hours](adminGuide-adminConfigureOnlineOrderingHoursOverview) section on the Takeout & delivery page in Toast Web. Restaurant operators must have [first-party delivery](https://central.toasttab.com/s/article/How-do-I-set-up-my-take-out-and-delivery-options-1492745822028) enabled in Toast Web to display DELIVERY hours.



> **Note**
> 
> Online ordering hours can extend past midnight as long as they are before the [closeout hour](apiDevGuide-apiRestaurantInformation). The closeout hour is the business day cutoff, which is the hour of the day that ends the current business day and starts the next. Allow at least 15 minutes between the end of the online ordering hour and the closeout hour. To configure your closeout hours, contact Toast support.



```
{
    "servicePeriods": [
        {
            "diningOptionBehavior": "DELIVERY" ,
            "dayPeriods": [
                {
                    "day": "MONDAY",
                    "timeRanges": [
                        {
                            "start": "11:00" ,
                            "end": "02:00"
                        }
                    ]
                },
                {
                    "day": "WEDNESDAY",
                    "timeRanges": [
                        {
                            "start": "11:00",
                            "end": "20:00"
                        }
                    ]
                },
                {
                    "day": "FRIDAY",
                    "timeRanges": [
                        {
                            "start": "11:00",
                            "end": "20:00"
                        }
                    ]
                },
                {
                    "day": "SATURDAY",
                    "timeRanges": [
                        {
                            "start": "12:00",
                            "end": "19:00"
                        }
                    ]
                }
            ]
        },
        {
            "diningOptionBehavior": "TAKE_OUT",
            "dayPeriods": [
                {
                    "day": "MONDAY",
                    "timeRanges": [
                        {
                            "start": "11:00",
                            "end": "02:00"
                        }
                    ]
                },
                {
                    "day": "WEDNESDAY",
                    "timeRanges": [
                        {
                            "start": "11:00",
                            "end": "20:00"
                        }
                    ]
                },
                {
                    "day": "FRIDAY",
                    "timeRanges": [
                        {
                            "start": "11:00",
                            "end": "20:00"
                        }
                    ]
                },
                {
                    "day": "SATURDAY",
                    "timeRanges": [
                        {
                            "start": "10:00",
                            "end": "19:00"
                        }
                    ]
                }
            ]
        }
    ],
    "overrides":  [
        {
            "description": "New operating hours",
            "diningOptionBehavior":  [
                "DELIVERY",
                "TAKE_OUT"
            ],
            "businessDate": 20211004,
            "timeRanges": [
                {
                    "start": "13:00",
                    "end": "16:00"
                }
            ]
        }
    ],
    "scheduledOrderMaxDays": 21 
}
```



    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e1163EA94E75-C09B-4686-82C8-0754D4415861" className="">(1)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <a href="apiDevGuide-apiOrderTypeDetails#apiOrdersDiningOptionTypes" className="">diningOptionBehavior</a> the online ordering schedule is returned for.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e1183EA94E75-C09B-4686-82C8-0754D4415861" className="">(2)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The local time in HH:MM format.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e1203EA94E75-C09B-4686-82C8-0754D4415861" className="">(3)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Returns scheduled overrides. Scheduled overrides are temporary periods of time (customizable increments of 15 minutes) when a restaurant can adjust their online ordering schedule for a selected date or date range. For more information, see <a href="adminGuide-adminConfigureOnlineOrderingHoursOverview#adminConfigureOverridesOnOnlineOrderingHours" className="">Configuring overrides</a>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e1223EA94E75-C09B-4686-82C8-0754D4415861" className="">(4)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Indicates which <code className="font-mono text-sm">diningOptionBehavior</code> the override applies to.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e1243EA94E75-C09B-4686-82C8-0754D4415861" className="">(5)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <a href="apiDevGuide-orders_api_future_orders" className="">maximum number of days in the future</a> a guest can schedule an online order. You should not place orders more than the <code className="font-mono text-sm">scheduledOrderMaxDays</code>. This value can be configured in the Online ordering section on the Takeout & delivery page in Toast Web.</p></div></td>
    </tr>
  
The values returned are organized by `diningOptionBehavior`.

- If the restaurants you work with manage their own delivery, use `DELIVERY` hours. For more information on how to configure self-delivery, see [Set Up Delivery Using Your Own Drivers](https://central.toasttab.com/s/article/How-do-I-set-up-my-take-out-and-delivery-options-1492745822028#Enabling).


- If you or the restaurants you work with offer third-party orders and pickup, use `TAKE_OUT` hours.


- To display general restaurant availability, use `TAKE_OUT` hours.



**Example 6.8. Determining if a restaurant accepts online orders**

In the following example, the response returns an empty array. This means the restaurant location has not configured their online ordering hours in Toast Web. We recommend you contact the restaurant location prior to going live to confirm online ordering hours have been configured.


```
{
    "servicePeriods": [],
    "overrides": [],
    "scheduledOrderMaxDays": 0
}

```

  
