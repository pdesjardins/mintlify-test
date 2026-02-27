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
      <th className=""><div className="">Orders component</div></th>
      <th className=""><div className="">In store</div></th>
      <th className=""><div className="">Online</div></th>
      <th className=""><div className="">Orders API</div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className=""><div className="">Menu item availability</div></td>
      <td className=""><div className="">Menu item configuration for in-store availability. <br/> Able to check availability based on the current time and inventory. </div></td>
      <td className=""><div className="">Menu item configuration for online availability. <br/> Can check availability based on the current time and inventory. </div></td>
      <td className=""><div className="">Cannot add open menu items to the order. An open menu item is one where the restaurant employee specifies both the item description and price. <br/> Can add open price menu items and special requests. <br/> No other configuration for menu item availability. <br/> Cannot verify availability based on time or inventory. </div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Scheduled orders</div></td>
      <td className=""><div className=""></div></td>
      <td className=""><div className="">Online ordering configuration to indicate whether to allow scheduled orders.</div></td>
      <td className=""><div className="">No restriction on whether the orders API can be used to create scheduled orders.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Discounts</div></td>
      <td className=""><div className="">Can select applicable discounts. <br/> Discounts can be applied automatically. </div></td>
      <td className=""><div className=""></div></td>
      <td className=""><div className="">Cannot apply an open amount discount.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Discount promotional codes</div></td>
      <td className=""><div className="">Prompted for promotional code if required for the discount.</div></td>
      <td className=""><div className="">Enter the promotional code to receive the associated discount.</div></td>
      <td className=""><div className="">No validation of a provided promotional code.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Order approvals</div></td>
      <td className=""><div className="">No required order approval for order firing.</div></td>
      <td className=""><div className="">Can configure online orders to require approval for order firing.</div></td>
      <td className=""><div className="">No required order approval for order firing.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Payment options</div></td>
      <td className=""><div className="">Can use any active payment option.</div></td>
      <td className=""><div className="">Can configure available payment options for takeout and delivery orders.</div></td>
      <td className=""><div className="">Can create orders using either a credit card or an <code className="">OTHER</code> payment type. <br/> Can only add credit card payments to an existing order.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Text messages</div></td>
      <td className=""><div className="">Can send text messages to guests.</div></td>
      <td className=""><div className=""></div></td>
      <td className=""><div className="">Cannot send text messages to guests.</div></td>
    </tr>
  </tbody>
</table>
</div>

