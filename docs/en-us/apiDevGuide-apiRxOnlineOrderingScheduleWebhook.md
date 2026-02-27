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


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className=""><div className="">Value</div></th>
      <th className=""><div className="">Description</div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">restaurantGuid</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">A unique Toast POS identifier for the restaurant.</p> <p className="text-base leading-relaxed">data type: string</p> <p className="text-base leading-relaxed">format: uuid</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">orderingSchedule</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The parent object that holds information about the days and times when the restaurant location accepts online orders. </p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">servicePeriods</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">An object that contains information about the restaurant's online ordering schedule. </p> <p className="text-base leading-relaxed">The <code className="font-mono text-sm">servicePeriods</code> array contains the following fields and values:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">diningOptionBehavior</code></p> <p className="text-base leading-relaxed"><code className="font-mono text-sm">TAKE_OUT</code> or <code className="font-mono text-sm">DELIVERY</code></p> <p className="text-base leading-relaxed">The dining behavior.</p> <p className="text-base leading-relaxed">data type: string</p></li><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">dayPeriods</code></p> <p className="text-base leading-relaxed">Object that contains information about the specific day and time range when the restaurant location accepts online orders.</p> <p className="text-base leading-relaxed">data type: object</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">day</code></p> <p className="text-base leading-relaxed">The day the online ordering schedule is returned for.</p> <p className="text-base leading-relaxed">data type: string</p></li><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">timeRanges</code></p> <p className="text-base leading-relaxed">Key-value pair detailing the start and end time for online ordering in HH:MM format.</p> <p className="text-base leading-relaxed">data type: object</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">start</code></p> <p className="text-base leading-relaxed">The local time in HH:MM format when the restaurant’s online ordering hours start.</p> <p className="text-base leading-relaxed">data type: string</p></li><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">end</code></p> <p className="text-base leading-relaxed">The local time in HH:MM format when the restaurant’s online ordering hours end.</p> <p className="text-base leading-relaxed">data type: string</p></li></ul></li></ul></li></ul></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">overrides</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">An object that contains information about planned overrides. Overrides only affect Toast Online Ordering and third-party orders. For more information, see <a href="adminGuide-adminConfigureOnlineOrderingHoursOverview#adminConfigureOverridesOnOnlineOrderingHours" className="">Configuring overrides</a>. </p> <p className="text-base leading-relaxed">The overrides array contains the following fields and values: </p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">description</code></p> <p className="text-base leading-relaxed">The description of the override.</p> <p className="text-base leading-relaxed">data type: string</p></li><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">diningOptionBehavior</code></p> <p className="text-base leading-relaxed"><code className="font-mono text-sm">TAKE_OUT</code> or <code className="font-mono text-sm">DELIVERY</code></p> <p className="text-base leading-relaxed">The dining behavior.</p> <p className="text-base leading-relaxed">data type: string</p></li><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">businessDate</code></p> <p className="text-base leading-relaxed">The day the override applies to in YYYYMMDD format. </p> <p className="text-base leading-relaxed">data type: integer</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">timeRanges</code></p> <p className="text-base leading-relaxed">Key-value pair detailing the start and end time for online ordering in HH:MM format.</p> <p className="text-base leading-relaxed">data type: object</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">start</code></p> <p className="text-base leading-relaxed">The local time in HH:MM format when the restaurant’s online ordering hours start.</p> <p className="text-base leading-relaxed">data type: string</p></li><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">end</code></p> <p className="text-base leading-relaxed">The local time in HH:MM format when the restaurant’s online ordering hours end.</p> <p className="text-base leading-relaxed">data type: string</p></li></ul></li></ul></li></ul></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">scheduledOrderMaxDays</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Number of days an online order can be placed into the future.</p> <p className="text-base leading-relaxed">data type: integer</p> <blockquote><strong>Note</strong> The restaurant online ordering schedule webhook does not send a message when there is a change to the maximum number of days scheduled orders can be placed into the future. For more information, see this <a href="https://central.toasttab.com/s/article/Scheduling-Future-Orders" className="">Toast Central article</a>.</blockquote> </div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">lastOrderConfiguration</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">UNTIL_CLOSING_TIME</code> or <code className="font-mono text-sm">UNTIL_PREPTIME_CUTOFF</code></p> <p className="text-base leading-relaxed">Indicates when the restaurant will stop accepting online orders. </p> <p className="text-base leading-relaxed">data type: string</p></div></td>
    </tr>
  </tbody>
</table>
</div>

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

  
