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

The return data from a `GET` request to the `/restaurants/&#123;restaurantGUID&#125;` endpoint of the restaurants API includes an `OnlineOrdering` object with the configuration for the restaurant's Toast Online Ordering service. If the restaurant has the Toast Online Ordering feature, restaurant employees configure these settings on the Takeout & delivery &gt; Toast online ordering &gt; Toast Online Ordering page in the Toast Web.

The following example shows the online ordering configuration values in the return data from a `GET` request to the `/restaurants/&#123;restaurantGUID&#125;` endpoint of the restaurants API.

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



    <tr className="">
      <td className=""><a href="#co-d1e709B5CC56A8-7562-434E-9596-72D2B0334CE4" className="">(1)</a></td>
      <td className="">Indicates whether the restaurant accepts online orders from the Toast Online Ordering service.</td>
    </tr>
    <tr className="">
      <td className=""><a href="#co-d1e711B5CC56A8-7562-434E-9596-72D2B0334CE4" className="">(2)</a></td>
      <td className="">A value of <code className="">true</code> means that guests can schedule orders to be fulfilled in the future, while a value of <code className="">false</code> means that scheduled orders cannot be placed and instead are fulfilled as soon as possible. If <code className="">true</code>, the restaurant can configure the maximum number of days in the future that scheduled orders can be placed.</td>
    </tr>
    <tr className="">
      <td className=""><a href="#co-d1e713B5CC56A8-7562-434E-9596-72D2B0334CE4" className="">(3)</a></td>
      <td className="">Whether guests can add instructions to their online orders.</td>
    </tr>
    <tr className="">
      <td className=""><a href="#co-d1e715B5CC56A8-7562-434E-9596-72D2B0334CE4" className="">(4)</a></td>
      <td className="">If <code className="">specialRequests</code> is <code className="">true</code>, provides a message to guests in the special requests dialog box where guests add their instructions. For example, the message might list order limitations for guest requests.</td>
    </tr>
    <tr className="">
      <td className=""><a href="#co-d1e717B5CC56A8-7562-434E-9596-72D2B0334CE4" className="">(5)</a></td>
      <td className="">Information on the forms of payments that the restaurant accepts for delivery and takeout online orders.</td>
    </tr>
    <tr className="">
      <td className=""><a href="#co-d1e720B5CC56A8-7562-434E-9596-72D2B0334CE4" className="">(6)</a></td>
      <td className="">Information on the forms of payments that the restaurant accepts for online delivery orders.</td>
    </tr>
    <tr className="">
      <td className=""><a href="#co-d1e722B5CC56A8-7562-434E-9596-72D2B0334CE4" className="">(7)</a></td>
      <td className="">Whether cash is accepted as payment for the order.</td>
    </tr>
    <tr className="">
      <td className=""><a href="#co-d1e724B5CC56A8-7562-434E-9596-72D2B0334CE4" className="">(8)</a></td>
      <td className="">Whether the restaurant accepts online credit card payment for orders that are delivered on the same day.</td>
    </tr>
    <tr className="">
      <td className=""><a href="#co-d1e726B5CC56A8-7562-434E-9596-72D2B0334CE4" className="">(9)</a></td>
      <td className="">Whether the restaurant accepts online credit card payment for scheduled (future) orders.</td>
    </tr>
    <tr className="">
      <td className=""><a href="#co-d1e728B5CC56A8-7562-434E-9596-72D2B0334CE4" className="">(10)</a></td>
      <td className="">Information on the forms of payments that the restaurant accepts for online takeout orders. The <code className="">cash</code>, <code className="">ccSameDay</code>, and <code className="">ccFuture</code> values have the same meaning as the <code className="">delivery</code> versions.</td>
    </tr>
    <tr className="">
      <td className=""><a href="#co-d1e730B5CC56A8-7562-434E-9596-72D2B0334CE4" className="">(11)</a></td>
      <td className="">Whether the restaurant accepts credit card payment when the guest picks up the takeout order in the restaurant. If <code className="">false</code>, the guest must pay online.</td>
    </tr>
    <tr className="">
      <td className=""><a href="#co-d1e733B5CC56A8-7562-434E-9596-72D2B0334CE4" className="">(12)</a></td>
      <td className="">Whether guest who order online are allowed to add tips to the order when paying by credit card.</td>
    </tr>
  
