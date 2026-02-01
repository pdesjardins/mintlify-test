---
title: "Comparing menus API V2 and V3"
id: apiComparingMenusAPIV2AndV3
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiAboutTheMenusApiOmitChunkFromSearchIndex.md
parentSectionTitle: "About the menus API"
previousSectionFile: apiDevGuide-apiGettingMenuInformationFromTheMenusAPI.md
previousSectionTitle: "Menus API overview"
nextSectionFile: apiDevGuide-apiMenusApiStructureMirrorsToastAdministrationBackEndStructure.md
nextSectionTitle: "Menus API structure mirrors Toast Web structure"
excerpt: "When choosing which version of the menus API to use, follow these guidelines:"
keywords: [comparing,menus]
procedures: 0
codeExamples: 0
---

### Comparing menus API V2 and V3

When choosing which version of the menus API to use, follow these guidelines:

- *Ordering partner integrations must use V3 of the menus API*.


- Other integration partners should continue to use V2. Currently, V3 only supports ordering partner integrations.



To understand the difference between V2 and V3 of the menus API, you must understand channel visibility. Toast menu entities each have a set of channel visibility settings in Toast Web. Restaurants use these settings to control where the menu entity is visible. If a menu entity is visible on a channel, then it is available for ordering on that channel. Channel examples include the Toast POS app, Toast kiosks, a restaurant's Toast Online Ordering website, and online ordering partner websites such as Grubhub and Uber Eats.

#### Channel visibility in menus API V2

With menus API V2, requests sent to the `/menus`endpoint return all menu entities for all of the specified restaurant's menus. The data for each menu entity includes a `visibility` array that defines which channels the menu entity is visible on. Possible values included in this array are `POS`, `KIOSK`, `TOAST_ONLINE_ORDERING`, and `ORDERING_PARTNERS`. Partner integrations use this `visibility` array to determine whether to include a menu entity in their integration or not. For example, consider a menu item whose `visibility` array contains `POS` but not `ORDERING_PARTNERS`. Ordering partner integrations would have to include logic to filter this menu item out to keep it from displaying on their online ordering websites.

Also, with the `/V2/menus` endpoint, there is no way to distinguish which specific online ordering partner channels a menu entity is visible on, so a menu entity whose `visibility`array includes the `ORDERING_PARTNERS` value is considered visible to all online ordering partners.

#### Channel visibility in menus API V3

With menus API V3, the `/menus` endpoint has been re-factored for ordering partners so it returns only menu entities that are visible to the ordering partner making the request. This eliminates the need for an ordering partner integration to filter the menu data it receives from the `/menus` endpoint. The Toast platform uses the partner token included with the request to determine which ordering partner made the request and filters the menu data accordingly. To access the `/V3/menus` endpoint, an ordering partner's API account must have the `menus.channel:read` scope.

Currently, menus API V3 only supports ordering partners. Additional re-factoring will happen in the future to support other types of partner integrations, including integrations that continue to need an aggregated view of all of a restaurant's menu entities.



> **Note**
> 
> For more information on the channel visibility settings in the Toast Web, see [Specifying ordering channel visibility](adminSpecifyingOrderingChannelVisibility.html) (for menu builder users) and [Visibility overview](adminMenuVisibilityOverview.html) (for classic menu page users).


