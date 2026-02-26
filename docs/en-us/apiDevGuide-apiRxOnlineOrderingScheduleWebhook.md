---
title: "Restaurant online ordering schedule webhook"
id: apiRxOnlineOrderingScheduleWebhook
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-portalWebhooksReferenceOmitChunkFromSearchIndex.md
parentSectionTitle: "Webhooks reference"
previousSectionFile: apiDevGuide-apiRxAvailabilityWebhook.md
previousSectionTitle: "Restaurant availability webhook"
nextSectionFile: apiDevGuide-apiStockWebhook.md
nextSectionTitle: "Stock webhook"
externalReferences: [https://central.toasttab.com/s/article/Scheduling-Future-Orders]
excerpt: "The restaurant online ordering schedule webhook allows you to receive real-time updates when a restaurant saves and publishes changes to their online ordering schedule. Typically, online ordering..."
keywords: ["order_schedule", "eventCategory", "ordering_schedule", "eventType", "ordering_schedule_updated"]
procedures: 0
codeExamples: 0
---



> **Note**
> 
> This feature is in limited release.


The restaurant online ordering schedule webhook allows you to receive real-time updates when a restaurant saves and publishes changes to their online ordering schedule. Typically, online ordering partners check a restaurant’s online ordering schedule 24 hours before, which means that they may miss scheduling changes between checks. For example, if you check a restaurant's online ordering schedule at 6 AM every morning, but the restaurant makes a change at 8 AM, you will miss this scheduling change and your platform will display the restaurant's old online ordering schedule. For more information on how to get a restaurant’s online ordering schedule, see [Getting online ordering schedules](apiDevGuide-apiGettingOnlineOrderingSchedules).

The restaurant online ordering schedule webhook checks for updates to a restaurant’s online ordering schedule, such as when they:

- Make changes to their online ordering schedule for takeout, and first and third-party delivery orders 


- Add, edit, or remove overrides


- Configure the time when they will stop accepting online orders





> **Note**
> 
> To trigger a webhook update, you must save and publish your online ordering schedule changes.


The restaurant online ordering schedule webhook messages follow the [standard message data schema](apiDevGuide-apiMessageDataSchema). When a message is published to your webhook endpoint for the `order_schedule` event category, the `eventCategory` value is set to `ordering_schedule`and the `eventType` is set to `ordering_schedule_updated`.

## Configuring online ordering schedules 

You can configure your online ordering schedule and overrides in Toast Web. Choose Takeout & delivery &gt; Online ordering hours to open the Online ordering hourssection. For more information, see [Online ordering hours overview](adminGuide-adminOnlineOrderingScheduleOverview).

## ordering_schedule_updated

Attributes in the `ordering_schedule_updated` event’s payload include:

| Value | Description | 
| --- | --- |
| `restaurantGuid` | A unique Toast POS identifier for the restaurant.data type:stringformat:uuid | 
| `orderingSchedule` | The parent object that holds information about the days and times when the restaurant location accepts online orders.  | 
| `servicePeriods` | An object that contains information about the restaurant's online ordering schedule. The `servicePeriods` array contains the following fields and values:- `diningOptionBehavior``TAKE_OUT` or `DELIVERY`The dining behavior.data type: string
- `dayPeriods`Object that contains information about the specific day and time range when the restaurant location accepts online orders.data type: object- `day`The day the online ordering schedule is returned for.data type: string
- `timeRanges`Key-value pair detailing the start and end time for online ordering in HH:MM format.data type: object- `start`The local time in HH:MM format when the restaurant’s online ordering hours start.data type: string
- `end`The local time in HH:MM format when the restaurant’s online ordering hours end.data type: string





 | 
| `overrides` | An object that contains information about planned overrides. Overrides only affect Toast Online Ordering and third-party orders. For more information, see [Configuring overrides](adminGuide-adminConfigureOnlineOrderingHoursOverview#adminConfigureOverridesOnOnlineOrderingHours). The overrides array contains the following fields and values: - `description`The description of the override.data type: string
- `diningOptionBehavior``TAKE_OUT` or `DELIVERY`The dining behavior.data type: string
- `businessDate`The day the override applies to in YYYYMMDD format. data type: integer- `timeRanges`Key-value pair detailing the start and end time for online ordering in HH:MM format.data type: object- `start`The local time in HH:MM format when the restaurant’s online ordering hours start.data type: string
- `end`The local time in HH:MM format when the restaurant’s online ordering hours end.data type: string





 | 
| `scheduledOrderMaxDays` | Number of days an online order can be placed into the future.data type:integer

> **Note**
> 
> The restaurant online ordering schedule webhook does not send a message when there is a change to the maximum number of days scheduled orders can be placed into the future.
> For more information, see this [Toast Central article](https://central.toasttab.com/s/article/Scheduling-Future-Orders).


 | 
| `lastOrderConfiguration` | `UNTIL_CLOSING_TIME` or `UNTIL_PREPTIME_CUTOFF`Indicates when the restaurant will stop accepting online orders. data type: string | 

**Example 9.12. Payload for an `ordering_schedule`_updated event**


```
{
  "timestamp": "2025-05-06T20:35:21.083Z",
  "eventCategory": "ordering_schedule",
  "eventType": "ordering_schedule_updated",
  "guid": "5b6ba185-7c75-4f72-9885-0a821de275cc",
  "details": {
    "restaurantGuid": "d6bf0376-cea1-47c0-a63c-9fc06638a5a6",
    "orderingSchedule": {
      "servicePeriods": [
        {
          "diningOptionBehavior": "DELIVERY",
          "dayPeriods": [
            {
              "day": "SATURDAY",
              "timeRanges": [
                {
                  "start": [
                    12,
                    0
                  ],
                  "end": [
                    0,
                    0
                  ]
                }
              ]
            },
            {
              "day": "SUNDAY",
              "timeRanges": [
                {
                  "start": [
                    11,
                    0
                  ],
                  "end": [
                    23,
                    0
                  ]
                }
              ]
            }
          ]
        },
        {
          "diningOptionBehavior": "TAKE_OUT",
          "dayPeriods": [
            {
              "day": "TUESDAY",
              "timeRanges": [
                {
                  "start": [
                    8,
                    0
                  ],
                  "end": [
                    20,
                    0
                  ]
                }
              ]
            },
            {
              "day": "WEDNESDAY",
              "timeRanges": [
                {
                  "start": [
                    10,
                    0
                  ],
                  "end": [
                    20,
                    0
                  ]
                }
              ]
            },
            {
              "day": "THURSDAY",
              "timeRanges": [
                {
                  "start": [
                    12,
                    0
                  ],
                  "end": [
                    21,
                    0
                  ]
                }
              ]
            }
          ]
        }
      ],
      "overrides": [
        {
          "description": "team party",
          "diningOptionBehavior": [
            "DELIVERY"
          ],
          "businessDate": 20250531,
          "timeRanges": [
            {
              "start": [
                9,
                0
              ],
              "end": [
                21,
                0
              ]
            }
          ]
        }
      ],
      "scheduledOrderMaxDays": 3,
      "lastOrderConfiguration": "UNTIL_CLOSING_TIME"
    }
  }
}
```

  
