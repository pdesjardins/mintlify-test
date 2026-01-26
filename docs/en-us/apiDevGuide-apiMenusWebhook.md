---
title: "Menus webhook"
id: apiMenusWebhook
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-portalWebhooksReferenceOmitChunkFromSearchIndex.md
parentSectionTitle: "Webhooks reference"
previousSectionFile: apiDevGuide-apiGuestOrderFulfillmentStatusWebhook.md
previousSectionTitle: "Guest order fulfillment status webhook"
nextSectionFile: apiDevGuide-devOrdersWebhookRef.md
nextSectionTitle: "Orders webhook"
externalReferences: [https://doc.toasttab.com/openapi/menus/overview/]
excerpt: "The menus webhook sends a message when a restaurant that uses your integration has published a change to its menus. The message payload includes the GUID of the affected restaurant and a timestamp..."
keywords: [eventCategory,menus_updated,eventType]
procedures: 0
codeExamples: 0
---

### Menus webhook

The `menus`webhook sends a message when a restaurant that uses your integration has published a change to its menus. The message payload includes the GUID of the affected restaurant and a timestamp for when the restaurant last published its menus. Having this information allows your integration client to [request a new menu](https://doc.toasttab.com/openapi/menus/overview/), keeping your integration in sync with the Toast platform. The `menus`webhook is the preferred method for determining if the menu data you have for a restaurant has gone stale.

If you are using the `menus`webhook, Toast support recommends also polling the `/metadata`endpoint of the menus API every 30 minutes. This provides a backup in case your integration misses a message from the `menus`webhook. The `/metadata`endpoint provides an alternative method for determining if a restaurant has published changes to its menu. Using the `/metadata`endpoint, you can retrieve the most recent date and time that a restaurant's menu was published. For more information on the `/metadata`endpoint, see [Determining if a restaurant's menu data has gone stale](apiGettingMenuInformationOmitChunkFromSearchIndex.html#apiDeterminingIfYourMenuJsonIsOutdated_V2).

Menus webhook messages follow the [standard message data schema](portalWebhooksOmitChunkFromSearchIndex.html#apiMessageDataSchema). When a message is published to your webhook endpoint for the `menus`event category, the `eventCategory`value is set to `menus`. Currently, `menus_updated`is the only `eventType`for the `menus`event category. For details on the payload for this event type, see [menus_updated](apiMenusWebhook.html#apiMenusUpdated).

#### menus_updated

A restaurant that uses your integration has published a change to its menus.

Attributes in the `menus_updated`event's payload include:

| Value | Description | 
| --- | --- |
| `restaurantGuid` | A unique Toast POS identifier for the restaurant whose menu has changed.data type:stringformat:uuid | 
| `publishedDate` | The most recent date and time that the menus for this restaurant were published. This timestamp is in the UTC time zone (not the restaurant's local timezone). The date and time are expressed in ISO 8601 format.data type:string | 

**Example 9.2. Payload example for the menus_updated event**

```
{
    "timestamp": “2019-09-16T21:01:53.685Z”,
    "eventCategory": "menus",
    "eventType": "menus_updated",
    "guid": "00000000-0000-0000-0000-000000000000",
    "details": {
        "restaurantGuid": "00000000-1111-2222-3333-444444444444",
        "publishedDate": "2021-10-06T20:11:01.737Z"
    }
}
```

  
