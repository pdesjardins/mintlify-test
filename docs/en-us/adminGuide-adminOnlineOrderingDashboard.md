---
title: "Online ordering dashboard"
id: adminOnlineOrderingDashboard
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminOnlineOrderingOmitChunkFromSearchIndex.md
parentSectionTitle: "Toast Online Ordering"
previousSectionFile: adminGuide-adminViewingOnlineOrderingSettings.md
previousSectionTitle: "Viewing online ordering settings"
nextSectionFile: adminGuide-adminFiringToastOnlineOrders.md
nextSectionTitle: "Firing Toast online orders"
externalReferences: [https://central.toasttab.com/s/article/Getting-Started-Online-Ordering#settings, https://central.toasttab.com/s/article/Online-Ordering-Advanced-Settings#throttling, https://central.toasttab.com/s/article/Managing-Your-Quote-Time-Strategy, https://central.toasttab.com/s/article/How-is-the-delivery-time-for-Toast-Delivery-Services-determined-for-the-guest]
excerpt: "On..."
keywords: ["online", "ordering", "dashboard"]
procedures: 1
codeExamples: 0
---

On the online ordering dashboard, you can quickly access settings to control your order volume and online ordering availability during peak times. From the dashboard, you can:

- Turn on/turn off/snooze online ordering availability.


- Add throttle delays for takeout orders.


- Turn on or off delivery or add a delay.



**Procedure 3.16. To access your restaurant's online ordering dashboard**

1. [Access Toast Web](adminGuide-adminAccessToastAdminBackend).


2. Choose Takeout & delivery \> Toast online ordering.



## Turning on/turning off/snoozing online ordering

From the online ordering dashboard, you can choose to turn on/turn off/snooze online ordering. The dashboard displays the online ordering setting configured on the Online ordering page in Toast Web. For more information, see [Getting Started with Online Ordering](https://central.toasttab.com/s/article/Getting-Started-Online-Ordering#settings).



> **Note**
> 
> If you do not use Toast Online Ordering, you do not see the dashboard. Instead a module is displayed asking if you want to upgrade to Toast Online Ordering. To upgrade, click the Upgrade now button. If online ordering is enabled, the setting for Toast Online Ordering is set to Ordering On. If online ordering is disabled, the setting is set to Ordering Off.


### Turn or off or snooze online ordering

Click the drop-down menu to the right of the dashboard. From the menu, make your selection. You can choose:

- On


- Snooze for 20 mins


- Snooze for 40 mins


- Off until tomorrow


- Off





> **Note**
> 
> Depending on your selection, certain options are automatically enabled or disabled. For example, if you choose to snooze online ordering for 20 minutes, this automatically disables the Delivery option.


After you make your selection, a colored label is added to the top of the dashboard. The label shows what selection was applied. For example, if you choose to snooze for 20 minutes at 10:00 AM, the label will show that online ordering is snoozed until 10:20 AM. If online ordering is enabled, the label displays your online ordering availability based on your configured [online ordering hours](adminGuide-adminConfigureOnlineOrderingHoursOverview). Your changes are automatically saved and published.

## Throttling delays for takeout orders

You can also add throttling delays for takeout orders from the online ordering dashboard. A throttling delay puts a hold on or pauses online orders. For more information, see [Online Ordering: Advanced Settings](https://central.toasttab.com/s/article/Online-Ordering-Advanced-Settings#throttling).

The takeout [quote time](https://central.toasttab.com/s/article/Managing-Your-Quote-Time-Strategy) that is displayed is the same time configured under Quote time strategy in Toast Web. Changes to the takeout quote time are automatically updated on the dashboard.

**Procedure 3.17. To add a delay for takeout orders**

1. Click the Takeout drop-down menu. From the menu, make your selection. You can choose to delay by 5 minute increments up to 120 minutes.

The takeout time is updated with a new quote time. The new takeout time is: quote time plus delay time. For example, if you have a quote time of 20 minutes and add a delay of 15 minutes, your new takeout time is 35 minutes.


2. Click the Publish all changes button to save your changes.



## Turning on and off delivery or adding a delay

Lastly, you can turn on or off delivery or add a delay from the online ordering dashboard. The dashboard displays the delivery setting configured on the Delivery page in Toast Web. Choose Takeout & delivery \> Availability \> Takeout/delivery \> Delivery to open the Delivery page. You can choose to turn on or off Toast Delivery Services (TDS) or first-party delivery. If you have TDS configured, all setting changes are defaulted to apply to TDS orders.



> **Note**
> 
> The delivery setting also appears as an icon on the dashboard. Click the icon to display the delivery setting.


**Procedure 3.18. To turn off TDS or first-party delivery**

1. Toggle the Delivery button from On to Off. This greys out the Delivery option and disables delivery on the Delivery page.


2. Click the Publish all changes button to save your changes.



**Procedure 3.19. To turn on TDS or first-party delivery**

1. Toggle the Delivery button from Off to On. This enables delivery on the Delivery page.

If you have TDS configured, the new delivery time is the takeout quote time plus DoorDash delivery time. [TDS uses the Takeout quote time](https://central.toasttab.com/s/article/How-is-the-delivery-time-for-Toast-Delivery-Services-determined-for-the-guest) and adds the additional DoorDash delivery time.


2. Click the Publish all changes button to save your changes.



**Procedure 3.20. To add a delay for first-party delivery orders**

For first-party delivery, the delivery quote time that is displayed is the same time configured under Quote time strategy in Toast Web. Changes to the delivery quote time are automatically updated on the dashboard.



> **Note**
> 
> You can only add a delay for first-party delivery orders. You cannot add a delay for TDS deliveries. For TDS orders, Toast recommends you add a takeout delay to adjust the quote time.


1. Click the Delivery drop-down menu. From the menu, make your selection. You can choose to delay by 5 minute increments up to 120 minutes.

The delivery time is updated with a new quote time. The new delivery time is: quote time plus delay time. For example, if you have a quote time of 40 minutes and add a delay of 5 minutes, your new delivery time is 45 minutes.


2. Click the Publish all changes button to save your changes.



