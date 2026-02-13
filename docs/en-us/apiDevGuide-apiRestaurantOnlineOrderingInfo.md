---
title: "Online ordering configuration"
id: apiRestaurantOnlineOrderingInfo
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiGettingRestaurantInfoOmitChunkFromSearchIndex.md
parentSectionTitle: "Getting restaurant info"
previousSectionFile: apiDevGuide-apiRestaurantInformation.md
previousSectionTitle: "Getting information about a specific restaurant"
nextSectionFile: apiDevGuide-apiGettingOnlineOrderingSchedules.md
nextSectionTitle: "Getting online ordering schedules"
excerpt: "The return data from a GET request to the /restaurants/{restaurantGUID} endpoint of the restaurants API includes an OnlineOrdering object with the configuration for the restaurant's Toast Online..."
keywords: ["online", "ordering", "configuration", "/restaurants/{restaurantGUID}", "OnlineOrdering", "specialRequests", "ccSameDay", "ccFuture"]
procedures: 0
codeExamples: 1
---

The return data from a `GET` request to the `/restaurants/{restaurantGUID}` endpoint of the restaurants API includes an `OnlineOrdering` object with the configuration for the restaurant's Toast Online Ordering service. If the restaurant has the Toast Online Ordering feature, restaurant employees configure these settings on the Takeout & delivery &gt; Toast online ordering &gt; Toast Online Ordering page in the Toast Web.

The following example shows the online ordering configuration values in the return data from a `GET` request to the `/restaurants/{restaurantGUID}` endpoint of the restaurants API.

**Example 6.5. Online ordering configuration in the restaurants API**


```
  "onlineOrdering": {
    "enabled": true,
    "scheduling": true,
    "specialRequests": true,
    "specialRequestsMessage": "No substitutes. Additions may be charged extra.",
    "paymentOptions": {
      "delivery": {
        "cash": true,
        "ccSameDay": true,
        "ccFuture": true
      },
      "takeout": {
        "cash": true,
        "ccSameDay": true,
        "ccFuture": true,
        "ccInStore": true
      },
      "ccTip": true
    }
  }
```



(1) Indicates whether the restaurant accepts online orders from the Toast Online Ordering service.

(2) A value of true means that guests can schedule orders to be fulfilled in the future, while a value of false means that scheduled orders cannot be placed and instead are fulfilled as soon as possible. If true, the restaurant can configure the maximum number of days in the future that scheduled orders can be placed.

(3) Whether guests can add instructions to their online orders.

(4) If specialRequests is true, provides a message to guests in the special requests dialog box where guests add their instructions. For example, the message might list order limitations for guest requests.

(5) Information on the forms of payments that the restaurant accepts for delivery and takeout online orders.

(6) Information on the forms of payments that the restaurant accepts for online delivery orders.

(7) Whether cash is accepted as payment for the order.

(8) Whether the restaurant accepts online credit card payment for orders that are delivered on the same day.

(9) Whether the restaurant accepts online credit card payment for scheduled (future) orders.

(10) Information on the forms of payments that the restaurant accepts for online takeout orders. The cash, ccSameDay, and ccFuture values have the same meaning as the delivery versions.

(11) Whether the restaurant accepts credit card payment when the guest picks up the takeout order in the restaurant. If false, the guest must pay online.

(12) Whether guest who order online are allowed to add tips to the order when paying by credit card.

  
