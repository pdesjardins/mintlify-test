---
title: "Effect of order source on order validation and processes"
id: platformOrdersSourceEffects
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminOrderWorkflowOmitChunkFromSearchIndex.md
parentSectionTitle: "Order workflows and processing"
previousSectionFile: adminGuide-platformOrdersTrackFulfillment.md
previousSectionTitle: "Tracking the order fulfillment"
nextSectionFile: adminGuide-adminViewingOrderDetailsOmitChunkFromSearchIndex.md
nextSectionTitle: "Viewing order details"
excerpt: "The order source indicates how the order was placed."
keywords: ["effect", "order", "source", "validation", "processes", "OTHER"]
procedures: 0
codeExamples: 0
---

The order source indicates how the order was placed.

- Created at the restaurant on some form of Toast device such as a handheld device or a kiosk.


- Submitted online from a website.


- Created using the orders API.



The origin of the order can have an affect on how the order is processed. For example, orders that are placed using the orders API are subject to less validation than orders created at the restaurant.

The following table summarizes the differences in order processing among the order sources.

| Orders component | In store | Online | Orders API | 
| --- | --- | --- | --- |
| Menu item availability | Menu item configuration for in-store availability.Able to check availability based on the current time and inventory.  | Menu item configuration for online availability.Can check availability based on the current time and inventory.  | Cannot add open menu items to the order. An open menu item is one where the restaurant employee specifies both the item description and price.Can add open price menu items and special requests.No other configuration for menu item availability.Cannot verify availability based on time or inventory.  | 
| Scheduled orders |  | Online ordering configuration to indicate whether to allow scheduled orders. | No restriction on whether the orders API can be used to create scheduled orders. | 
| Discounts | Can select applicable discounts.Discounts can be applied automatically.  |  | Cannot apply an open amount discount. | 
| Discount promotional codes | Prompted for promotional code if required for the discount. | Enter the promotional code to receive the associated discount. | No validation of a provided promotional code. | 
| Order approvals | No required order approval for order firing. | Can configure online orders to require approval for order firing. | No required order approval for order firing. | 
| Payment options | Can use any active payment option. | Can configure available payment options for takeout and delivery orders. | Can create orders using either a credit card or an `OTHER` payment type.Can only add credit card payments to an existing order. | 
| Text messages | Can send text messages to guests. |  | Cannot send text messages to guests. | 

