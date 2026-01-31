---
title: "Chapter 2. Orders"
id: devPortalPlatformGuideOrdersOmitChunkFromSearchIndex
type: chapter
documentId: adminGuide
parentSectionFile: adminGuide-index.md
parentSectionTitle: "Platform guide"
previousSectionFile: adminGuide-techReleaseNotesLimitedRelease.md
previousSectionTitle: "Limited release status for product changes"
nextSectionFile: adminGuide-adminOrderWorkflowOmitChunkFromSearchIndex.md
nextSectionTitle: "Order workflows and processing"
externalReferences: [https://doc.toasttab.com/openapi/orders/overview]
procedures: 0
codeExamples: 0
---

# Chapter 2. Orders

## Orders overview

### Order information

An order is the basic building block of a restaurant transaction. Each order specifies:

- The items that a guest purchases.


- The amount that the guest is charged.


- How the guest receives the order.


- How the guest pays for the order.



![Diagram that shows the basic components of an order](https://doc.toasttab.com/doc/media/order-components.png)



****About checks****
: Each order contains one or more checks. An order usually has only one check, but it can have multiple checks. For example, a party of guests might request separate checks so that each guest can pay separately.

Each check includes:

- The menu item selections and prices.


- Applicable taxes. See [Taxes](adminTaxesOmitChunkFromSearchIndex.html#adminTaxesOverview).


- Discounts on the menu item selections and on the entire check. See [Discounts](adminDiscountsIntroOmitChunkFromSearchIndex.html#platformDiscountsOverview).


- Service charges on the check. See [Service charges](adminServiceChargesOmitChunkFromSearchIndex.html#adminServiceChargeOverview).


- Information about the guest. See [Guests](devPortalPlatformGuideGuestsOmitChunkFromSearchIndex.html#adminGuestDataOverview).


- Payments that the guest made on the order.





****Other order information****
: Outside of the checks, the order tracks how the guest receives the ordered items:

- The selected [dining option](adminDiningOptions.html). A dining option is associated with a specific dining behavior (in-person, takeout, curbside pickup, delivery).


- The restaurant employee who is responsible for the order.


- For in-person dining, the table where the guest is located.


- For delivery orders, the delivery address and instructions.


- For curbside pickup orders, information about the vehicle that is picking up the order.







### Guest personal identifiable information

Toast products use guest personal identifiable information (PII) to help restaurant employees identify who an order belongs to. For example, in the case of a takeout order, a cashier needs to know which order belongs to a guest picking up an order.

#### Tab name

When using the POS modes listed below on a Toast POS device, you can create a tab name that contains a guest's PII with the Tab function. While a tab name is most commonly used to input a guest's name, some restaurants may use this field to input a guest's name, address, or phone number.

- Dine-in


- Kiosk


- Takeout


- Delivery



You can also create a tab name using the `tabName`field in the `checks` object of the Toast orders API. For more information about the orders API, see the [orders API reference documentation](https://doc.toasttab.com/openapi/orders/overview).

#### Tab name display

When an employee creates a tab name for an order, it is displayed in the areas described below, in addition to being displayed on the POS device.

| Product | Description | 
| --- | --- |
| Kitchen Display System (KDS) | If a ticket has a tab name, the tab name displays on the KDS ticket as shown in the image below.![Tab name shown on KDS.](https://doc.toasttab.com/doc/media/platformOrdersPiiTabNameKds.png)

 | 
| Receipts | Receipts can be configured to display a tab name. In Toast Web navigate to Payments > Checks & receipt setup > Guest receipt setup. If the Show Tab Name setting is set to Show tab name on customer receipts, a ticket's tab name displays on the guest receipt as seen in the image below. ![Tab name shown on receipt.](https://doc.toasttab.com/doc/media/platformOrdersPiiReceiptTabName.png)

 | 
| Order detail summary report | A ticket's tab name shows in the Order details summary report as seen in image below. From Toast Web navigate to Reports > Sales > Order details. The tab name field only shows if a tab name was used on the order.![Tab name shown on the Order Details report.](https://doc.toasttab.com/doc/media/platformOrdersPiiOrderDetailsReport.png)

 | 

