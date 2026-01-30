---
title: "Chapter 4. Menus"
id: portalApiGettingMenusOmitChunkFromSearchIndex
type: chapter
documentId: apiDevGuide
parentSectionFile: apiDevGuide-index.md
parentSectionTitle: "Developer guide"
previousSectionFile: apiDevGuide-apiCreatingAnOrderWithPaymentInformation.md
previousSectionTitle: "Alternative payment types"
nextSectionFile: apiDevGuide-apiGettingMenuInformationOmitChunkFromSearchIndex.md
nextSectionTitle: "Getting menu information"
procedures: 0
codeExamples: 0
---

# Chapter 4. Menus

## About the menus API

### Menus API overview

Using the menus API, you can retrieve a fully resolved set of menus for the restaurant you specify. With this data, you can construct a menu that satisfies your business requirements. For example, you can use the menus API data to construct a digital menu board or create an ordering application where guests can place orders.

To retrieve data from the menus API, you send a `GET`request to the `/menus` endpoint. Before retrieving data, send a `GET` request to the `/metadata` endpoint to [determine if the menu data you have is stale](apiGettingMenuInformationOmitChunkFromSearchIndex.html#apiDeterminingIfYourMenuJsonIsOutdated_V2).

Currently, the menus API has two versions, version 2 (V2) and version 3 (V3). The [Comparing menus API V2 and V3](portalApiGettingMenusOmitChunkFromSearchIndex.html#apiComparingMenusAPIV2AndV3) section compares the two versions and provides guidance on who should use them and how.

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
> For more information on the channel visibility settings in the Toast Web, see [adminGuide#adminSpecifyingOrderingChannelVisibility] (for menu builder users) and [adminGuide#adminMenuVisibilityOverview] (for classic menu page users).


### Menus API structure mirrors Toast Web structure

The menus API returns JSON that reflects the structure that a Toast customer has defined for their restaurant's menus in Toast Web. This is also the structure that the Toast platform uses to display menus on Toast devices. For example, if a restaurant's Breakfast menu is configured to appear on a Toast POS device before a Lunch menu, then the JSON returned by the menus API will include the Breakfast menu data before the Lunch menu data. To use the menus API effectively, it is important to understand the Toast menu structure and rules described in [adminGuide#adminMenuHierarchy].

### Using menus API data to construct valid orders

If you are using the menus API data to construct an ordering application, those orders will ultimately be injected into the Toast platform using the orders API. It is important that orders injected into the orders API are properly formed and valid. The menus API provides information that you can use to ensure that orders you pass to the orders API are valid. See [Using menus API data to submit properly formed orders](apiUsingMenusApiDataToSubmitProperlyFormedOrders_V2.html) for more information.

### Menus API supports data retrieval only

The menus API returns all values for all objects in the JSON output, even if they are empty or null. The menus API currently supports data retrieval only. If any of the menu entities returned by the menus API need modification, those configuration changes must be made in the Toast Web by the Toast customer.

### Menus API returns published data only

To conserve the use of system resources, the menus API service only generates the JSON that it returns when a menu-related change has been made and published. This means that:

- The menus API returns published data only.


- The menus API does not return data for archived menu entities.


- If changes have been made to a restaurant's menu configuration in Toast Web, the Toast customer must publish those changes before the menus API can return them.



There is a period of time after a menu has been published during which the Toast platform publishes the new data and then creates the menu JSON file that the menus API returns in response to requests made to the `/menus` endpoint. The length of this time period depends on the size and complexity of the restaurant's menu. You must wait for this process to complete before the newly published data will be returned by the menus API.

### Ensuring your menu data is up-to-date

Toast Support recommends that you compare the date and time of your current menu JSON to that of the most recently published JSON to see if changes have been made before you make a call to the `/menus` endpoint. You retrieve the date and time of the most recently published JSON using the `/metadata` endpoint. See [Determining if a restaurant's menu data has gone stale](apiGettingMenuInformationOmitChunkFromSearchIndex.html#apiDeterminingIfYourMenuJsonIsOutdated_V2) for more information.



> **Important**
> 
> Best practice is to poll the `/metadata` endpoint through the day to determine if your menu JSON has become stale and make a call to the `/menus` endpoint if it has.


### Understanding the order in which modifier groups are returned

The menus API returns modifier groups in the same order in which they are displayed on the Toast POS app. For more information on the logic the Toast platform uses to determine modifier group display order on the Toast POS app, see [adminGuide#platformModifierGroupDisplayOrderOverview].

### Menus API supersedes configuration API and menu data export for menu data retrieval

The menus API supersedes the configuration API and the nightly menu JSON export for menu data retrieval. To understand the differences between these three menu retrieval mechanisms, see [Comparing the menus API with the configuration API and menu JSON export](apiComparingTheMenusApiWithTheConfigurationApiAndMenuJsonExport_V2.html).

