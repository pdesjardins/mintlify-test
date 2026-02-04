---
title: "Delivery settings"
id: adminConfigureDelivery
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminDeliveryAndTDSOmitChunkFromSearchIndex.md
parentSectionTitle: "First-party delivery and Toast Delivery Services"
previousSectionFile: adminGuide-adminDeliveryOverview.md
previousSectionTitle: "Delivery overview"
nextSectionFile: adminGuide-adminSetDeliveryMinimum.md
nextSectionTitle: "Setting a delivery minimum"
externalReferences: [https://central.toasttab.com/s/article/Delivery-Mode-1493048871021, https://central.toasttab.com/s/article/Getting-Started-Toast-Delivery-Services-Setup]
keywords: ["delivery", "settings"]
procedures: 0
codeExamples: 0
---



> **Important**
> 
> The settings described in the following sections only apply to the delivery options in Toast Web. These sections do not cover Delivery mode in the Toast POS app. For information about how to use Delivery mode, see [Get Help with Delivery Mode, and Dispatch Drivers](https://central.toasttab.com/s/article/Delivery-Mode-1493048871021).


### Toast Delivery Services (TDS)



> **Note**
> 
> To enable and activate TDS, you must have a subscription to Toast Online Ordering. For more information, see [Get Started With Toast Delivery Services](https://central.toasttab.com/s/article/Getting-Started-Toast-Delivery-Services-Setup).


If you have a subscription to Toast Online Ordering, you can activate and enable TDS through the setup checklist available in Toast Web. Complete the setup checklist to activate TDS.

#### Creating a TDS job and employee

After you enable TDS, the Toast platform creates a Delivery Service Driver job and an employee named TDS (first name) Driver(last name). All TDS orders are assigned to this employee.

### Configuring delivery options

You can configure your delivery options on the Takeout/delivery page in Toast Web.

**Procedure 3.28. To configure your delivery option**

1. [Access Toast Web](adminAccessToastAdminBackend.html).


2. Choose Takeout & delivery \> Availability \> Takeout/delivery to open the Takeout/delivery page.


3. In the Delivery section, under the Delivery Enabled? setting, select one of the following:

- Enable delivery using Toast Delivery Services. Select this option for TDS.

You must choose how to collect your guest's billing information. You can choose from one of the following options:

- Billing customer information always matches delivery information


- Always prompt for billing customer information prior to delivery information


- Always prompt for billing customer information after delivery information




- Enable delivery using your own delivery drivers. Select this option for first-party delivery.

You must choose how to collect your guest's billing information. You can choose from one of the following options:

- Billing customer information always matches delivery information


- Always prompt for billing customer information prior to delivery information


- Always prompt for billing customer information after delivery information




- Disable delivery. Select this option to turn off delivery. You can also turn off delivery from the [online ordering dashboard](adminOnlineOrderingDashboard.html).




4. Select the Save button to save your changes.



#### Configuring your delivery dining behavior

On the Dining options page in Toast Web, you can configure dining behaviors for your delivery dining options. In Toast Web, choose Kitchen \> Dining options \> Dining options to open the Dining optionspage. For first-party delivery, configure your dining option and then select Delivery as the dining behavior. At least one dining option must have Delivery set as a dining behavior. For TDS, the Toast platform automatically generates a Toast Delivery Services dining option and sets the dining behavior to Delivery. The Toast Delivery Services dining option is locked and you cannot edit it.

#### Setting your online ordering schedule

In the Online ordering hours section in Toast Web, you can set your online ordering hours for delivery. In Toast Web, choose Takeout & delivery \> Online ordering hours to view your online ordering hours for takeout and delivery. Your online ordering schedule is displayed on your Toast Online Ordering website and the Local by Toast app.

#### Configuring payment options

On the Online ordering page in Toast Web, you configure how your guests pay for delivery orders. In Toast Web, choose Takeout & delivery \> Availability \> Online ordering to open the Online orderingpage. Navigate to the Delivery payment optionssection. For first-party delivery orders, you can choose to allow payment by: Cash, Credit Card - Online (Same Day Orders), and Credit Card - Online (Future Orders). Guests must pay for TDS orders by credit card or debit card. Guests cannot pay for TDS orders with cash.

