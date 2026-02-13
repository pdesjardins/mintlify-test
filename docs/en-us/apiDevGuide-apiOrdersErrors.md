---
title: "Orders API errors"
id: apiOrdersErrors
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiOrdersOvercviewOmitChunkFromSearchIndex.md
parentSectionTitle: "About the orders API"
previousSectionFile: apiDevGuide-apiOrdersFirstOrder.md
previousSectionTitle: "Submitting your first order to the orders API"
nextSectionFile: apiDevGuide-portalApiGettingOrdersOmitChunkFromSearchIndex.md
nextSectionTitle: "Getting order information"
excerpt: "The entries in the table below define errors you may encounter while using the orders API. These entries are ordered alphabetically by error message."
keywords: ["Address 1", "deliveryInfo.address1", "customer.firstName", "startDate", "endDate)", "businessDate", "endDate", "menuGroups", "menuItems", "type=Discount"]
procedures: 0
codeExamples: 0
---

The entries in the table below define errors you may encounter while using the orders API. These entries are ordered alphabetically by error message.

| Message | Resolution | 
| --- | --- |
| `Address 1` for delivery address cannot be empty  | The `Address 1` field in your request is empty. Input the customer's address in the `deliveryInfo.address1` field. | 
| Customer first name cannot be empty  | Add a value the `customer.firstName`field. | 
| Customer phone cannot be empty  | Add a value to the `customer.phone` field.  | 
| EITHER (`startDate` and `endDate)` OR `businessDate` is required | Input both a start date and end date or a business date to your request.  | 
| Input `startDate` must be before `endDate` | Check the `startDate` and `endDate` values throughout your request and ensure that the `startDate` time stamps occur before the `endDate` time stamps. | 
| Item (*`{item GUID}`*) does not belong to the group (*`{item group GUID}`*) |  A menu item in your request does not belong to the referenced menu group. Update the menu item's `menuGroups`. You can find `menuItems` and `menuGroups` values by submitting a `GET` request to the `/menus/v2/menus` endpoint. | 
| Referenced entity (`type=Discount`) must contain a GUID | The discount in your request requires a GUID. You can find discount GUIDs by sending a `GET`request to the `/config/v2/discounts`endpoint. | 
| Referenced entity (`type=MenuItem`) must contain either a GUID or `MultiLocationId` | Your request contains a menu item entry that is missing a GUID or a `multilocationId`. You can find The GUID and `multilocationId` values by submitting a `GET` request from the appropriate menu endpoint. For more information see [devGuide](apiDevGuide-apiComparingMenusAPIV2AndV3) | 
|  Restaurant({*`restaurant GUID`*}) has been deleted | The restaurant GUID that you are using in your order request refers to a restaurant that's been deleted. Stop all API requests to this restaurant.  | 

