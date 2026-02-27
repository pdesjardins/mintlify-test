---
title: "Guest personal identifiable information"
id: platformOrdersPii
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformOrdersOverviewOmitChunkFromSearchIndex.md
parentSectionTitle: "Orders overview"
previousSectionFile: adminGuide-platformOrdersOverview.md
previousSectionTitle: "Order information"
nextSectionFile: adminGuide-adminOrderWorkflowOmitChunkFromSearchIndex.md
nextSectionTitle: "Order workflows and processing"
externalReferences: [https://doc.toasttab.com/openapi/orders/overview]
excerpt: "Toast products use guest personal identifiable information (PII) to help restaurant employees identify who an order belongs to. For example, in the case of a takeout order, a cashier needs to know..."
keywords: ["guest", "personal", "identifiable", "information"]
procedures: 0
codeExamples: 0
---

Toast products use guest personal identifiable information (PII) to help restaurant employees identify who an order belongs to. For example, in the case of a takeout order, a cashier needs to know which order belongs to a guest picking up an order.

## Tab name

When using the POS modes listed below on a Toast POS device, you can create a tab name that contains a guest's PII with the Tab function. While a tab name is most commonly used to input a guest's name, some restaurants may use this field to input a guest's name, address, or phone number.

- Dine-in


- Kiosk


- Takeout


- Delivery



You can also create a tab name using the `tabName`field in the `checks` object of the Toast orders API. For more information about the orders API, see the [orders API reference documentation](https://doc.toasttab.com/openapi/orders/overview).

## Tab name display

When an employee creates a tab name for an order, it is displayed in the areas described below, in addition to being displayed on the POS device.


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className="">Product</th>
      <th className="">Description</th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="">Kitchen Display System (KDS)</td>
      <td className="">If a ticket has a tab name, the tab name displays on the KDS ticket as shown in the image below. <br/> ![Tab name shown on KDS.](https://doc.toasttab.com/doc/media/platformOrdersPiiTabNameKds.png) <br/> </td>
    </tr>
    <tr className="">
      <td className="">Receipts</td>
      <td className="">Receipts can be configured to display a tab name. In Toast Web navigate to Payments &gt; Checks & receipt setup &gt; Guest receipt setup. If the Show Tab Name setting is set to Show tab name on customer receipts, a ticket's tab name displays on the guest receipt as seen in the image below. ![Tab name shown on receipt.](https://doc.toasttab.com/doc/media/platformOrdersPiiReceiptTabName.png)</td>
    </tr>
    <tr className="">
      <td className="">Order detail summary report</td>
      <td className="">A ticket's tab name shows in the Order details summary report as seen in image below. From Toast Web navigate to Reports &gt; Sales &gt; Order details. The tab name field only shows if a tab name was used on the order. <br/> ![Tab name shown on the Order Details report.](https://doc.toasttab.com/doc/media/platformOrdersPiiOrderDetailsReport.png) <br/> </td>
    </tr>
  </tbody>
</table>
</div>

