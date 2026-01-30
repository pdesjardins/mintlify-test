---
title: "Getting menu information"
id: apiGettingMenuInformationOmitChunkFromSearchIndex
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-portalApiGettingMenusOmitChunkFromSearchIndex.md
parentSectionTitle: "Chapter 4. Menus"
previousSectionFile: apiDevGuide-portalApiGettingMenusOmitChunkFromSearchIndex.md
previousSectionTitle: "Chapter 4. Menus"
nextSectionFile: apiDevGuide-apiMenusApiRateLimit_V2.md
nextSectionTitle: "Menus API rate limit"
externalReferences: [https://doc.toasttab.com/openapi/menus/overview/]
keywords: [getting,menu,information]
procedures: 0
codeExamples: 0
---

### Determining if a restaurant's menu data has gone stale

There are two methods for determining if the menu data your integration client has for a restaurant has gone stale, the `menus` webhook and the `/metadata` endpoint. You should not make a call to the `/menus` endpoint for a restaurant unless you have used one of these methods to determine that the menu data you have for that restaurant is stale. While this recommendation applies to all clients of the menus API, it is particularly important for clients that have limited bandwidth.

The `menus` webhook is the preferred method for determining when a restaurant's menu data has gone stale. This webhook sends a message when a restaurant that uses your integration has published a change to its menus. The message payload includes the GUID of the affected restaurant and a timestamp, in the UTC time zone, for when the restaurant last published its menus. To keep your integration in sync with the Toast platform, request a new menu from the `/menus` endpoint after you receive a message from the `menus` webhook. If you are using the `menus`webhook, Toast support recommends also polling the `/metadata` endpoint (described below) every 30 minutes. This provides a backup in case your integration misses a message from the `menus` webhook.

As an alternative to the `menus` webhook, you can use the `/metadata` endpoint to retrieve the most recent date and time that the restaurant's menu was published, in the UTC time zone. You can compare the date and time returned by the `/metadata`endpoint to the `lastUpdated` value of the `Restaurant` object in your current menu data. Toast support strongly recommends that you do not make a call to the `/menus` endpoint unless the date and time returned by the `/metadata` endpoint is more recent than the `lastUpdated` date and time. If your integration uses the `/metadata` endpoint, Toast Support recommends that you poll the `/metadata` endpoint throughout the day to determine if your menu data has become stale.

For more information on the `menus` webhook, see [Menus webhook](apiMenusWebhook.html). For more information on the `/metadata` endpoint, see the [menus API reference documentation](https://doc.toasttab.com/openapi/menus/overview/).

