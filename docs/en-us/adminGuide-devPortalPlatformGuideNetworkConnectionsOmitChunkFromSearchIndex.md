---
title: "Chapter 11. Network connections"
id: devPortalPlatformGuideNetworkConnectionsOmitChunkFromSearchIndex
type: chapter
documentId: adminGuide
parentSectionFile: adminGuide-index.md
parentSectionTitle: "Platform guide"
previousSectionFile: adminGuide-platformKitchenPrintersOffline.md
previousSectionTitle: "Kitchen printers"
nextSectionFile: adminGuide-platformIntegrationsOmitChunkFromSearchIndex.md
nextSectionTitle: "Chapter 12. Integrations"
externalReferences: [https://status.toasttab.com/]
procedures: 0
codeExamples: 0
---

# Chapter 11. Network connections

## Offline support

### Offline mode overview

As a cloud-based app, the Toast platform must use the internet to connect to its cloud-based services. Other Toast operations, such as sending credit card information to credit card networks for authorization and connecting with third-party integrations, must be performed through the internet and the Toast platform cloud-based service. The internet connection is provided by an internet service provider (ISP).

The internet connection is made through a network router. The router can also provide a Wi-Fi network for the restaurant. Although network connection types can vary from one restaurant to another, Toast terminals and access points typically have hard-wired Ethernet connections to the router. Mobile (handheld) devices typically have Wi-Fi connections, and printers may use hardwired or Wi-Fi connections. Toast support recommends using hardwired connections where possible.

If a Toast restaurant experiences a disruption at any of these points, the Toast platform detects the connection loss. If the connection loss is at the Toast platform cloud-based service, ISP, or network level, the Toast platform identifies that the devices are offline and switches the affected devices to offline mode. **Offline mode** allows a restaurant to continue functioning as normally as possible if a Toast POS device is forced offline. After 40 seconds of offline activity, an offline banner appears on the Toast POS app and provides information on the cause of the disruption, what actions you can and cannot do, and resolution steps. When the connection is restored, the Toast platform automatically switches the device back online.

An offline state is triggered by the following:

- The local network connection is disrupted.


- The internet connection is disrupted.


- The Toast platform cloud-based server connection is disrupted.





> **Note**
> 
> Keep in mind that one device can be offline while other devices are online. For example, if you take a handheld device with you to deliver an order, the device is offline and will use offline mode when you are out of Wi-Fi range, but the device returns online when it is within the restaurant's Wi-Fi coverage area again. In this scenario, offline limitations apply only to that device, and not to the other online devices at the restaurant.


Depending on which [type of disruption](devPortalPlatformGuideNetworkConnectionsOmitChunkFromSearchIndex.html#platformOfflineDisruptionTypes) you are experiencing, what [data synchronization method](devPortalPlatformGuideNetworkConnectionsOmitChunkFromSearchIndex.html#platformOfflineDataSyncMethods) is in use, and how many devices are affected, how offline mode works for your restaurant can differ.

#### Disruption types

The type of disruption you experience affects the offline working conditions for your restaurant. Each disruption type has it's own steps to resolve the disruption.



> **Important**
> 
> A single offline device on a local network with multiple devices that are online indicates a problem with the device rather than a disruption.


If your restaurant is offline, the disruption can be:

- The local network is unavailable.



> **Note**
> 
> If you have more than one device on a local network, and this disruption only affects one device, the issue is specific to the device.



- The internet connection is down.


- A Toast platform cloud-based service outage.





> **Important**
> 
> Online orders rely on the Toast platform cloud-based service to send and receive API requests. When a restaurant experiences any type of outage, the restaurant can no longer send and receive API requests through this service. Once connection is restored, the restaurant receives all online orders sent during the outage. Toast support recommends that integrations use the [restaurant availability webhook](apiRxAvailabilityWebhook.html) to avoid creating online orders while the restaurant offline. Placing orders while offline can contribute to the kitchen being overwhelmed with orders once the connection is restored.


For more information on what you can do while using offline mode depending on the disruption type, see [Data synchronization methods for offline mode](devPortalPlatformGuideNetworkConnectionsOmitChunkFromSearchIndex.html#platformOfflineDataSyncMethods) and choose the data synchronization method.

##### Local network disruption

*If the local network is down*, something is wrong with your router. 



> **Note**
> 
> When there is no local network connection at all, there are no printer connections.


![Diagram of the Toast platform for a restaurant experiencing a local network disruption.](https://doc.toasttab.com/doc/media/network-router-disruption-offline.png)

If a single device is unable to connect to the local network, the other devices on the local network continue to function normally.

![Diagram of the Toast platform for a single Toast POS device experiencing a local network disruption.](https://doc.toasttab.com/doc/media/network-device-disruption-offline.png)

When you experience a local network connection disruption, try the following:

- Verify that all Ethernet cables are plugged in.


- Verify that all printers and switches are plugged in and turned on.


- On a Toast POS device, check your Wi-Fi connection status. ToastGo devices must be connected to a secured Toast network.


- Turn your router off and on again.



> **Caution**
> 
> If using [offline mode](devPortalPlatformGuideNetworkConnectionsOmitChunkFromSearchIndex.html#platformOfflineMode), this step can prevent backup printing and should be done last.




##### Internet service provider disruption

*If the internet connection is down*, something is wrong on your internet service provider’s end. 



> **Note**
> 
> When the local area network (including Wi-Fi connections) is working, but the Toast POS device cannot connect to the internet, the printer connections are still functional.


![Diagram of the Toast platform for a restaurant experiencing an internet service provider disruption.](https://doc.toasttab.com/doc/media/isp-disruption-offline.png)

When you experience an internet connection disruption, try the following:

- Verify that the Ethernet cable between your modem and router is connected.


- Contact your internet service provider and ask if they are experiencing any outages and how they can help troubleshoot. They might recommend turning your modem off and on.



##### Toast platform cloud-based server disruption

*If there is a Toast platform cloud-based server outage*, something is wrong on the Toast end, and support is working on fixing it.



> **Note**
> 
> When the local network and internet connections are working, but the Toast POS device cannot connect to the Toast platform cloud-based service, the printer connections are still functional.


![Diagram of the Toast platform for a restaurant experiencing a Toast platform cloud-based server disruption.](https://doc.toasttab.com/doc/media/cloud-disruption-offline.png)

When you experience a Toast platform cloud-based service disruption, you can visit the [Toast status page](https://status.toasttab.com/) for a message about the outage and sign up for future updates.

#### Data synchronization methods for offline mode

Toast is migrating from the current data synchronization method to one that implements local sync. Local sync enables devices to communicate with each other through a local, eligible device automatically assigned by Toast called the local hub device.

Depending on which data synchronization method is in use, the Toast platform behaves in two ways when offline:

- [Offline mode](devPortalPlatformGuideNetworkConnectionsOmitChunkFromSearchIndex.html#platformOfflineMode)



> **Note**
> 
> Toast plans to deprecate the offline mode method and switch entirely to offline mode with local sync.



- [Offline mode with local sync](devPortalPlatformGuideNetworkConnectionsOmitChunkFromSearchIndex.html#platformOfflineModeLocalSync)



With *offline mode*, Toast devices communicate through the Toast platform cloud-based service. For example, when online and an order is added on a Toast POS device, it is sent to the Toast platform cloud-based service, which sends it to all devices at the same restaurant. When offline, the device cannot send orders to the Toast platform cloud-based service, which means that order data is stored locally on each individual device.

With* offline mode with local sync*, Toast devices use the local hub device as the communication point between all Toast devices on a local network. For example, when online and an order is added on a Toast POS device, it is sent to the local hub device, which sends it to the rest of the devices at the same restaurant. When offline due to an internet or Toast outage, an order added to a Toast POS device is sent to the local hub device, which distributes it to the other devices. The local hub device cannot send orders to the Toast platform cloud-based service when offline.

### Offline mode

Toast devices use offline mode when experiencing a connection issue. Offline mode indicates Toast devices communicate with each other through the Toast platform cloud-based services.



> **Important**
> 
> If the restaurant cannot communicate with the Toast cloud, the devices cannot communicate with each other.


The content of the Toast POS device offline messaging depends on the primary mode of your Toast POS device and the Toast products you use. For example, if your restaurant uses online ordering and KDS devices, the offline dialog for a Toast POS device using payment terminal mode during an internet service disruption reflects offline behavior for those products in relation to payment terminal mode. In this example, the messaging includes sending KDS tickets to backup printers if configured, continuing to take orders and payments, not turning off the device while offline, and other related guidance.

For details on Toast platform functionality in offline mode, see:

- [Takeout and delivery orders](platformOffPremiseOfflineModeOmitChunkFromSearchIndex.html#adminOfflineDelivery)


- [Toast Online Ordering](adminOfflineOnlineOrdering.html)


- [Employee clock-in and clock-out](platformEmployeesOfflineModeOmitChunkFromSearchIndex.html#adminOfflineEmployees)


- [Offline card payments](adminOfflineCCPayments.html)



#### Offline mode check number assignments

If your restaurant goes offline, your Toast POS devices still generate a check number for any orders that are created while offline. Offline check numbers are calculated in the following way: 

1. Add 2 to the POS device number.


2. Next, the new device number is multiplied by 1000. This calculation gives you a new base check number.


3. Check numbers begin incrementing based on the new base check number.



For example, if your Toast POS device number is 1, while in offline mode, your check numbers will start at 3000 ((1+2) * 1000).

Once your POS devices are back online, check numbering resumes from where it left off before going offline, and the offline mode check numbers are no longer used.

#### Offline due to a local network connection disruption

When a device is offline due to a local network connectivity issue, a banner displays at the top of the Toast POS app screen to inform you the device is offline and there is a local network connection issue. When the device initially switches to offline mode, a dialog opens, informing you what you can still do while offline and what actions to avoid.

The following banner displays at the top of the Toast POS device.

![The offline banner indicating a local network connection issue.](https://doc.toasttab.com/doc/media/network_outage_banner.png)

A dialog similar to the following opens on the Toast POS device.

![The dialog informing you what you can and cannot do during a local network connection issue.](https://doc.toasttab.com/doc/media/platform-offline-legacy-network-outage-dialog.png)

Select Got it to close the dialog or Troubleshoot to view troubleshooting options for a local network disruption.

The following dialog shows troubleshooting information.

![The dialog informing you how to access troubleshooting information for a local network disruption and some troubleshooting methods.](https://doc.toasttab.com/doc/media/platform-offline-legacy-network-outage-troubleshoot.png)

Select Done to close the dialog.

To open this dialog again, select What to doon the offline banner.

To recover, first check that your local network cable is securely connected or Wi-Fi is enabled on the device. For more information, see [Local network disruption](devPortalPlatformGuideNetworkConnectionsOmitChunkFromSearchIndex.html#platformOfflineNetworkDisruptionType).

After the issue is resolved and the local network connection is restored, the offline banner disappears.

#### Offline due to an internet service disruption

When a device is offline due to an internet connection issue, a banner displays at the top of the Toast POS app screen to inform you that the device is offline and there is an internet connection issue. When the device initially switches to offline mode, a dialog opens, informing you what you can still do while offline and what actions to avoid.

The following banner displays at the top of the Toast POS device.

![The offline banner indicating an internet service disruption.](https://doc.toasttab.com/doc/media/isp_outage_banner.png)

A dialog similar to the following opens on the Toast POS device.

![The dialog informing you what you can and cannot do during an internet service disruption.](https://doc.toasttab.com/doc/media/platform-offline-legacy-internet-outage-dialog.png)

Select Got it to close the dialog or Troubleshoot to view troubleshooting options for an internet service disruption.

The following dialog shows troubleshooting information.

![The dialog informing you how to access troubleshooting information for an internet service disruption and some troubleshooting methods.](https://doc.toasttab.com/doc/media/platform-offline-legacy-internet-outage-troubleshoot.png)

Select Done to close the dialog.

To open this dialog again, select What to doon the offline banner.

To resolve this issue, contact your internet service provider (ISP). For more information, see [Internet service provider disruption](devPortalPlatformGuideNetworkConnectionsOmitChunkFromSearchIndex.html#platformOfflineInternetDisruptionType).

Once the issue is resolved for the device and the connection is restored, the offline banner disappears.

#### Offline due to a Toast platform cloud-based service disruption

When a device is offline due to a Toast platform cloud-based service disruption, a banner displays at the top of the Toast POS app screen to inform you that the device is offline because of a Toast platform cloud-based service disruption. When the device initially switches to offline mode, a dialog opens, informing you what you can still do while offline and what actions to avoid.

The following banner displays at the top of the Toast POS device.

![The offline banner indicating a Toast platform cloud-based service disruption.](https://doc.toasttab.com/doc/media/toast_outage_banner.png)

A dialog similar to the following opens on the Toast POS device.

![The dialog informing you what you can and cannot do during a Toast platform cloud-based service disruption.](https://doc.toasttab.com/doc/media/platform-offline-legacy-toast-outage-dialog.png)

Select Got it to close the dialog or Troubleshoot to view troubleshooting options for a Toast platform cloud-based service disruption.

The following dialog shows troubleshooting information.

![The dialog informing you how to access troubleshooting information for a Toast platform cloud-based service disruption.](https://doc.toasttab.com/doc/media/platform-offline-legacy-toast-outage-troubleshoot.png)

Select Done to close the dialog.

To open this dialog again, select What to doon the offline banner.

This is a Toast service issue and Toast is working to resolve it. You can visit the [Toast status page](https://status.toasttab.com/) for information about current outages.

Once the issue is resolved for the device and the connection is restored, the offline banner disappears.

#### Best practices and available operations

This section provides some best practices for offline Toast POS devices using offline mode, as well as listing which Toast operations are, and are not, available.



> **Note**
> 
> These best practices and operations apply to internet service provider and Toast platform cloud-based service disruptions.




**Offline mode supportability guidelines**

- **Do not** uninstall and reinstall the Toast POS app on a device. Doing so permanently removes all stored data and payments from the device.


- **Do not** clear the device's cache or the Toast app data. Doing so permanently removes all stored data and payments from the device.


- **Do not** log in or log out of the Toast POS app. You will not be able to log back in until the connection is restored.


- **Do not** turn your network router off and on while offline. The devices will not be able to print offline until the connection is restored.


- Add and update orders on the same device. Devices cannot sync with each other while offline, so orders added or updated on one device do not appear on other devices. Toast recommends each employee choose a single device to place and update orders. More than one front of house employee can work on a device, but it is important that they use only that one device while offline.


- Keep merchant copies of receipts signed by guests as records for payments taken offline, in case the payment is lost.


- Consider installing a cellular network backup stick to help prevent triggering offline mode.


- Set up a kitchen printer to print tickets that would normally display on a KDS device. For instructions, see [Adding a kitchen printer](platformKitchenOperationsAndFulfillmentOmitChunkFromSearchIndex.html#adminAddKitchenPrinter).


- Contact Toast support to [temporarily disable the auto-capture process](adminOfflineCCPayments.html#adminOfflineAutoCapture) if your system does not re-establish connectivity by the end of the business day. This gives you time to make adjustments to credit card payments before they are captured. Once the payments are captured, you cannot make updates.



**Operations available in offline mode**

- Print kitchen tickets to backup printers (if configured). For more information, see the [Printing Mode](platformKitchenConfigReferenceOmitChunkFromSearchIndex.html#configPrintingMode) and [Always Print Tickets](platformKitchenConfigReferenceOmitChunkFromSearchIndex.html#configPrepStationsAlwaysPrintTickets) settings.



> **Note**
> 
> Kitchen workflows use *offline mode with local sync*, unless an error is detected by the KDS. For more information, see [KDS devices](platformKitchenOpsOfflineSupportOmitChunkFromSearchIndex.html#platformOfflineKDSDevices).



- Use scales for weighted menu items.


- Process credit cards as offline payments. For more information, see [Offline card payments](adminOfflineCCPayments.html).


- Add credit card or non-cash tips onto payments.


- Open cash drawers (if printers are available).


- Print customer receipts at terminals (if printers are available).



Select Learn More in the offline banner to see the supported operations and whether printers are available.

**Operations and features not available in offline mode**

- Display POS and Kiosk orders on KDS devices.



> **Note**
> 
> Kitchen workflows automatically use *offline mode with local sync*, unless an error is detected by the KDS. For more information, see [KDS devices](platformKitchenOpsOfflineSupportOmitChunkFromSearchIndex.html#platformOfflineKDSDevices).



- Send and receive orders on Kiosks.


- Clock in or clock out on separate devices.


- Log into or log out of the Toast POS application. You will not be able to log back in until the connection is restored.


- Share orders between devices.


- Access guest data and online reports.


- Completing shift reviews.


- Using EMV credit card mode (credit cards must be swiped).


- Process gift card sales or gift cards as a payment method.


- Redeem rewards (loyalty) points as a payment method.


- Use house accounts as a payment method.


- Redeem customer credits as a payment method.


- Look up guest information for takeout or delivery orders. For details, see [Takeout and delivery orders](platformOffPremiseOfflineModeOmitChunkFromSearchIndex.html#adminOfflineDelivery).


- Resync orders and resync all data. The Resync Orders and the Resync ALL Dataoperations on devices are disabled during offline mode. This prevents the erasure of stored information on the device, which means you would lose all sales data and payments without the ability to retrieve them.



### Offline mode with local sync

Offline mode with local sync uses a Toast device as the point of connection, or the local hub device, between all devices on a restaurant's local network. This allows Toast devices to communicate with each other in the event that an issue arises with the internet service provider or the Toast platform cloud-based service. The local hub device relays updates from one device to other devices and to the Toast platform cloud-based service. Offline mode with local sync relies on a local network connection to function.



> **Important**
> 
> This feature is not compatible for restaurants using Elo v1 devices.


The content of the Toast POS device offline messaging depends on the primary mode of your Toast POS device and the Toast products you use. For example, if your restaurant uses online ordering and KDS devices, the offline dialog for a Toast POS device using payment terminal mode during an internet service disruption reflects offline behavior for those products in relation to payment terminal mode. In this example, the messaging includes continuing to send orders to KDS devices, continuing to take orders and payments, not turning off the device while offline, and other related guidance.

#### Local hub devices

For offline mode with local sync to work, your restaurant needs an eligible device to act as the local hub device.



> **Note**
> 
> Toast automatically chooses an eligible device to act as the local hub device. Toast support can reassign a different device as the local hub device.


An eligible device is:

- *Neither* a hand-held or Elo V1 device


- Using a hardwired Ethernet connection


- Connected to the restaurant's local network



> **Note**
> 
> If your restaurant uses both a Toast-managed local network and another self-managed local network, only devices using the Toast-managed local network are eligible.



- Active, meaning it received a ping from Toast within the last three minutes





> **Caution**
> 
> A local hub device can only communicate to devices on the same local network and a restaurant can only have one local hub device. If you have multiple local networks or subnets, information cannot be shared between them when offline. For example, a restaurant has two ToastGos working on a separate network. They are connected directly to the cloud, not a local hub device. When offline, the ToastGos cannot send information to or from the local hub device or each other.


A local hub device is assigned automatically by Toast.

#### Offline due to a local network connection issue

When a device is offline due to a local network connectivity issue, a banner displays at the top of the Toast POS app screen to inform you that the device is offline and that there is a local network connection issue. When the device initially switches to offline mode with local sync, a dialog opens, informing you what you can still do while offline and what actions to avoid.

The following banner displays at the top of the Toast POS device.

![The offline banner indicating a local network connection issue.](https://doc.toasttab.com/doc/media/network_outage_banner.png)

A dialog similar to the following opens on the Toast POS device.

![The dialog informing you what you can and cannot do during a local network connection issue.](https://doc.toasttab.com/doc/media/platform-offline-local-network-outage-dialog.png)

Select Got it to close the dialog or Troubleshoot to view troubleshooting options for a local network disruption.

The following dialog shows troubleshooting information.

![The dialog informing you how to access troubleshooting information for a local network disruption and some troubleshooting methods.](https://doc.toasttab.com/doc/media/platform-offline-local-network-outage-troubleshoot.png)

Select Done to close the dialog.

To open this dialog again, select What to doon the offline banner.

To recover, first check that your network cable is securely connected or Wi-Fi is enabled on the device. For more information, see [Local network disruption](devPortalPlatformGuideNetworkConnectionsOmitChunkFromSearchIndex.html#platformOfflineNetworkDisruptionType).

After the issue is resolved and the connection is restored, the offline banner disappears.

#### Offline due to an internet service disruption

When a device is offline due to local network connectivity or internet issues, a banner displays at the top of the Toast POS app screen to inform you that the device is offline because of an internet issue. When the device initially switches to offline mode with local sync, a dialog opens, informing you what you can still do while offline and what actions to avoid.

The following banner displays at the top of the Toast POS device.

![The offline banner indicating an internet service disruption.](https://doc.toasttab.com/doc/media/isp_outage_banner.png)

A dialog similar to the following opens on the Toast POS device.

![The dialog informing you what you can and cannot do during an internet service disruption.](https://doc.toasttab.com/doc/media/platform-offline-local-internet-outage-dialog.png)

Select Got it to close the dialog or Troubleshoot to view troubleshooting options for an internet service disruption.

The following dialog shows troubleshooting information.

![The dialog informing you how to access troubleshooting information for an internet service disruption and some troubleshooting methods.](https://doc.toasttab.com/doc/media/platform-offline-local-internet-outage-troubleshoot.png)

Select Done to close the dialog.

To open this dialog again, select What to doon the offline banner.

To resolve this issue, contact your ISP (internet service provider). For more information, see [Internet service provider disruption](devPortalPlatformGuideNetworkConnectionsOmitChunkFromSearchIndex.html#platformOfflineInternetDisruptionType).

Once the issue is resolved for the device and the connection is restored, the offline banner disappears.

#### Offline due to a Toast platform cloud-based service disruption

When a device is offline due to a Toast platform cloud-based service disruption, a banner displays at the top of the Toast POS app screen to inform you that the device is offline because of a Toast platform cloud-based service disruption. When the device initially switches to offline mode with local sync, a dialog opens, informing you what you can still do while offline and what actions to avoid.

The following banner displays at the top of the Toast POS device.

![The offline banner indicating a Toast platform cloud-based service disruption.](https://doc.toasttab.com/doc/media/toast_outage_banner.png)

A dialog similar to the following opens on the Toast POS device.

![The dialog informing you what you can and cannot do during a Toast platform cloud-based service disruption.](https://doc.toasttab.com/doc/media/platform-offline-local-toast-outage-dialog.png)

Select Got it to close the dialog or Troubleshoot to view troubleshooting options for a Toast platform cloud-based service disruption.

The following dialog shows troubleshooting information.

![The dialog informing you how to access troubleshooting information for a Toast platform cloud-based service disruption.](https://doc.toasttab.com/doc/media/platform-offline-local-toast-outage-troubleshoot.png)

Select Done to close the dialog.

To open this dialog again, select What to doon the offline banner.

This is a Toast service issue and Toast is working to resolve the issue. You can visit the [Toast status page](https://status.toasttab.com/) for information about current outages.

Once the issue is resolved for the device and the connection is restored, the offline banner disappears.

#### Best practices and available operations

This section provides some best practices for offline Toast POS devices using offline mode with local sync, as well as listing which Toast operations are, and are not, available.



> **Note**
> 
> These best practices and operations apply to internet service provider and Toast platform-cloud based service disruptions.


**Offline mode with local sync supportability guidelines**

- **Do not** uninstall and reinstall the Toast POS app on a device. Doing so permanently removes all stored data and payments from the device.


- **Do not** forcibly close the Toast POS app.


- **Do not** clear the device's cache or the Toast app data. Doing so permanently removes all stored data and payments from the device.


- **Do not** log in or out of the Toast POS app. You will not be able to log back in until the connection is restored.


- **Do not** turn your network router off and on while offline. Tickets from POS devices will not appear on the KDS device until the local network connection is restored. For more information, see [KDS devices](platformKitchenOpsOfflineSupportOmitChunkFromSearchIndex.html#platformOfflineKDSDevices).


- **Do not** disconnect a Toast POS device from the local network. This includes leaving wireless range, using airplane mode, or connecting to a different network. The device cannot share data between devices until it reconnects to the local network.


- Add and update orders on the same device. KDS devices can receive orders from POS devices on the same local network. However, orders sent from one POS device cannot be seen on another device unless it is a KDS device. Toast recommends each employee choose a single device to place and update orders. More than one front of house employee can work on a device, but it is important that they use only that one device while offline.


- Use separate devices for your cable modem and network router. This allows you to restart the cable modem separately while still maintaining local network connectivity.


- Keep merchant copies of receipts signed by guests as records for payments taken offline, in case the payment is lost.


- Consider installing a cellular network backup stick to help prevent triggering offline mode.


- Contact Toast support to [temporarily disable the auto-capture process](adminOfflineCCPayments.html#adminOfflineAutoCapture) if your system does not re-establish connectivity by the end of the business day. This gives you time to make adjustments to credit card payments before they are captured. Once the payments are captured, you cannot make updates.



**Operations available in offline mode with local sync**

- Display POS and Kiosk orders on KDS devices on the same local network (if configured). If you do not use KDS devices, tickets print at kitchen printers (if configured). For more information, see [KDS devices](platformKitchenOpsOfflineSupportOmitChunkFromSearchIndex.html#platformOfflineKDSDevices) and [Kitchen printers](platformKitchenPrintersOffline.html).


- Use scales for weighted menu items.


- Process credit cards as offline payments. For more information, see [Offline card payments](adminOfflineCCPayments.html).


- Add credit card or non-cash tips onto payments.


- Open cash drawers (if printers are available).


- Print customer receipts at terminals (if printers are available).



Select Learn More in the offline banner to see the supported operations and whether printers are available.

**Operations and features not available in offline mode with local sync**

- Send and receive orders on Kiosks.


- Clock in or clock out on separate devices.


- Log into or log out of the Toast POS application. You will not be able to log back in until the connection is restored.


- Sharing orders between devices on the same local network that are not KDS devices. KDS devices will show all orders regardless of which device they were taken on.


- Printing kitchen tickets when fulfilled or as needed from the KDS device for orders created during an outage.


- Access guest data and online reports.


- Employee shift reviews.


- EMV credit card mode (credit cards must be swiped).


- Process gift card sales or as a payment method.


- Redeem rewards (loyalty) points as a payment method.


- House accounts as a payment method.


- Redeem customer credits as a payment method.


- Look up guest information for takeout or delivery orders. For details, see [Takeout and delivery orders](platformOffPremiseOfflineModeOmitChunkFromSearchIndex.html#adminOfflineDelivery).


- Resync orders and resync all data. The Resync Orders and the Resync ALL Dataoperations on devices are disabled during offline mode. This prevents the erasure of stored information on the device, which means you would lose all sales data and payments without the ability to retrieve them.



