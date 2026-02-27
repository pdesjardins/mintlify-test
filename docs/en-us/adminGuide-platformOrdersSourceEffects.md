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


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className="">Orders component</th>
      <th className="">In store</th>
      <th className="">Online</th>
      <th className="">Orders API</th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="">Menu item availability</td>
      <td className="">Menu item configuration for in-store availability. <br/> Able to check availability based on the current time and inventory. </td>
      <td className="">Menu item configuration for online availability. <br/> Can check availability based on the current time and inventory. </td>
      <td className="">Cannot add open menu items to the order. An open menu item is one where the restaurant employee specifies both the item description and price. <br/> Can add open price menu items and special requests. <br/> No other configuration for menu item availability. <br/> Cannot verify availability based on time or inventory. </td>
    </tr>
    <tr className="">
      <td className="">Scheduled orders</td>
      <td className=""></td>
      <td className="">Online ordering configuration to indicate whether to allow scheduled orders.</td>
      <td className="">No restriction on whether the orders API can be used to create scheduled orders.</td>
    </tr>
    <tr className="">
      <td className="">Discounts</td>
      <td className="">Can select applicable discounts. <br/> Discounts can be applied automatically. </td>
      <td className=""></td>
      <td className="">Cannot apply an open amount discount.</td>
    </tr>
    <tr className="">
      <td className="">Discount promotional codes</td>
      <td className="">Prompted for promotional code if required for the discount.</td>
      <td className="">Enter the promotional code to receive the associated discount.</td>
      <td className="">No validation of a provided promotional code.</td>
    </tr>
    <tr className="">
      <td className="">Order approvals</td>
      <td className="">No required order approval for order firing.</td>
      <td className="">Can configure online orders to require approval for order firing.</td>
      <td className="">No required order approval for order firing.</td>
    </tr>
    <tr className="">
      <td className="">Payment options</td>
      <td className="">Can use any active payment option.</td>
      <td className="">Can configure available payment options for takeout and delivery orders.</td>
      <td className="">Can create orders using either a credit card or an <code className="">OTHER</code> payment type. <br/> Can only add credit card payments to an existing order.</td>
    </tr>
    <tr className="">
      <td className="">Text messages</td>
      <td className="">Can send text messages to guests.</td>
      <td className=""></td>
      <td className="">Cannot send text messages to guests.</td>
    </tr>
  </tbody>
</table>
</div>

