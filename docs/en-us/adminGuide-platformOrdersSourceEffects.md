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
      <th className=""><div className=""><p className="text-base leading-relaxed">Orders component</p></div></th>
      <th className=""><div className=""><p className="text-base leading-relaxed">In store</p></div></th>
      <th className=""><div className=""><p className="text-base leading-relaxed">Online</p></div></th>
      <th className=""><div className=""><p className="text-base leading-relaxed">Orders API</p></div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Menu item availability</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Menu item configuration for in-store availability.</p> <p className="text-base leading-relaxed">Able to check availability based on the current time and inventory. </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Menu item configuration for online availability.</p> <p className="text-base leading-relaxed">Can check availability based on the current time and inventory. </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Cannot add open menu items to the order. An open menu item is one where the restaurant employee specifies both the item description and price.</p> <p className="text-base leading-relaxed">Can add open price menu items and special requests.</p> <p className="text-base leading-relaxed">No other configuration for menu item availability.</p> <p className="text-base leading-relaxed">Cannot verify availability based on time or inventory. </p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Scheduled orders</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4">Online ordering configuration to indicate whether to allow scheduled orders.</div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">No restriction on whether the orders API can be used to create scheduled orders.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Discounts</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Can select applicable discounts.</p> <p className="text-base leading-relaxed">Discounts can be applied automatically. </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Cannot apply an open amount discount.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Discount promotional codes</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Prompted for promotional code if required for the discount.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Enter the promotional code to receive the associated discount.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">No validation of a provided promotional code.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Order approvals</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">No required order approval for order firing.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Can configure online orders to require approval for order firing.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">No required order approval for order firing.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Payment options</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Can use any active payment option.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Can configure available payment options for takeout and delivery orders.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Can create orders using either a credit card or an <code className="font-mono text-sm">OTHER</code> payment type.</p> <p className="text-base leading-relaxed">Can only add credit card payments to an existing order.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Text messages</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Can send text messages to guests.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Cannot send text messages to guests.</p></div></td>
    </tr>
  </tbody>
</table>
</div>

