---
title: "Chapter 6. Restaurant info"
id: portalApiGettingRestaurantInfoOmitChunkFromSearchIndex
type: chapter
documentId: apiDevGuide
parentSectionFile: apiDevGuide-index.md
parentSectionTitle: "Developer guide"
previousSectionFile: apiDevGuide-apiUpdatingInventoryInformationOmitChunkFromSearchIndex.md
previousSectionTitle: "Updating stock information"
nextSectionFile: apiDevGuide-apiGettingRestaurantInfoOmitChunkFromSearchIndex.md
nextSectionTitle: "Getting restaurant info"
externalReferences: [https://doc.toasttab.com/openapi/orders/overview/, https://doc.toasttab.com/openapi/labor/overview/]
procedures: 0
codeExamples: 0
---

# Chapter 6. Restaurant info

## Restaurant information overview

The restaurants API has endpoints that let you obtain two types of information about restaurants:

- The `/restaurants/v1/groups/{managementGroupGUID}/restaurants`endpoint returns a list of the restaurants that belong to a restaurant management group.


- The `/restaurants/v1/restaurants/{restaurantGUID}`endpoint returns configuration information about a specific restaurant location. This configuration information is more business oriented (such as the restaurant's location, services, and schedules) than the information returned by the [configuration API](apiPartnersGettingAccessibleRestaurants.html).



### Restaurant closeoutHour and business dates

The restaurant API's `closeoutHour`determines your restaurant's `businessDate`value in other Toast APIs. The `closeoutHour`is a value from 0-12 (midnight (0) to noon (12)), which represents your restaurant's Business Day Cutoffconfiguration in Toast Web. For example, if your restaurant's Business Day Cutofffield is set to 4 AM, the `closeoutHour`value will be `4`. The time zone for the Business Day Cutoffis determined by your restaurant's Time Zoneconfiguration in Toast Web.



> **Note**
> 
> Your restaurant's Business Day Cutoffand Time Zoneconfigurations can only be updated by Toast Support.


#### Toast Web business closeout operations

When your restaurant's `closeoutHour`time has been reached, the following operations occur in Toast Web:

- Any employees who are still clocked in are automatically clocked out.


- Card payments that have not been captured yet are automatically captured. This is typically the entire day's card payments.





> **Note**
> 
> The Toast platform will not close unpaid orders. Unpaid orders remain open until they are resolved either by being paid or voided.


#### Toast API business closeout operations

When your restaurant's `closeoutHour`time has been reached, the following operations occur in Toast APIs.

**Orders API **

- `closeDate`: The `closeDate`value is set to a time after the `closeoutHour`.


- `modifiedDate`: The `modifiedDate`value is set to a time after the `closeoutHour`.



For more information about the orders API, see [Toast orders API](https://doc.toasttab.com/openapi/orders/overview/).

**Labor API **

- `outDate`: Any time entries without an `outDate`value are automatically closed and the `outDate`value is set to the business cut-off time.


- `modifiedDate`: The `modifiedDate`value is set to the business cut-off time for any time entries closed at the business cut-off time.



For more information about the labor API, see [Toast labor API](https://doc.toasttab.com/openapi/labor/overview/).

