---
title: "Offline mode overview"
id: adminOfflineModeOverview
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminOfflineModeOmitChunkFromSearchIndex.md
parentSectionTitle: "Offline support"
previousSectionFile: adminGuide-adminOfflineModeOmitChunkFromSearchIndex.md
previousSectionTitle: "Offline support"
nextSectionFile: adminGuide-platformOfflineMode.md
nextSectionTitle: "Offline mode"
externalReferences: [https://status.toasttab.com/]
excerpt: "As a cloud-based app, the Toast platform must use the internet to connect to its cloud-based services. Other Toast operations, such as sending credit card information to credit card networks for..."
keywords: ["offline", "mode", "overview", "Offline mode"]
procedures: 0
codeExamples: 0
---

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


Depending on which [type of disruption](adminGuide-adminOfflineModeOverview#platformOfflineDisruptionTypes) you are experiencing, what [data synchronization method](adminGuide-adminOfflineModeOverview#platformOfflineDataSyncMethods) is in use, and how many devices are affected, how offline mode works for your restaurant can differ.

## Disruption types

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
> Online orders rely on the Toast platform cloud-based service to send and receive API requests. When a restaurant experiences any type of outage, the restaurant can no longer send and receive API requests through this service. Once connection is restored, the restaurant receives all online orders sent during the outage. Toast support recommends that integrations use the [restaurant availability webhook](apiDevGuide-apiRxAvailabilityWebhook) to avoid creating online orders while the restaurant offline. Placing orders while offline can contribute to the kitchen being overwhelmed with orders once the connection is restored.


For more information on what you can do while using offline mode depending on the disruption type, see [Data synchronization methods for offline mode](adminGuide-adminOfflineModeOverview#platformOfflineDataSyncMethods) and choose the data synchronization method.

### Local network disruption

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
> If using [offline mode](adminGuide-platformOfflineMode), this step can prevent backup printing and should be done last.




### Internet service provider disruption

*If the internet connection is down*, something is wrong on your internet service provider’s end. 



> **Note**
> 
> When the local area network (including Wi-Fi connections) is working, but the Toast POS device cannot connect to the internet, the printer connections are still functional.


![Diagram of the Toast platform for a restaurant experiencing an internet service provider disruption.](https://doc.toasttab.com/doc/media/isp-disruption-offline.png)

When you experience an internet connection disruption, try the following:

- Verify that the Ethernet cable between your modem and router is connected.


- Contact your internet service provider and ask if they are experiencing any outages and how they can help troubleshoot. They might recommend turning your modem off and on.



### Toast platform cloud-based server disruption

*If there is a Toast platform cloud-based server outage*, something is wrong on the Toast end, and support is working on fixing it.



> **Note**
> 
> When the local network and internet connections are working, but the Toast POS device cannot connect to the Toast platform cloud-based service, the printer connections are still functional.


![Diagram of the Toast platform for a restaurant experiencing a Toast platform cloud-based server disruption.](https://doc.toasttab.com/doc/media/cloud-disruption-offline.png)

When you experience a Toast platform cloud-based service disruption, you can visit the [Toast status page](https://status.toasttab.com/) for a message about the outage and sign up for future updates.

## Data synchronization methods for offline mode

Toast is migrating from the current data synchronization method to one that implements local sync. Local sync enables devices to communicate with each other through a local, eligible device automatically assigned by Toast called the local hub device.

Depending on which data synchronization method is in use, the Toast platform behaves in two ways when offline:

- [Offline mode](adminGuide-platformOfflineMode)



> **Note**
> 
> Toast plans to deprecate the offline mode method and switch entirely to offline mode with local sync.



- [Offline mode with local sync](adminGuide-platformOfflineModeLocalSync)



With *offline mode*, Toast devices communicate through the Toast platform cloud-based service. For example, when online and an order is added on a Toast POS device, it is sent to the Toast platform cloud-based service, which sends it to all devices at the same restaurant. When offline, the device cannot send orders to the Toast platform cloud-based service, which means that order data is stored locally on each individual device.

With* offline mode with local sync*, Toast devices use the local hub device as the communication point between all Toast devices on a local network. For example, when online and an order is added on a Toast POS device, it is sent to the local hub device, which sends it to the rest of the devices at the same restaurant. When offline due to an internet or Toast outage, an order added to a Toast POS device is sent to the local hub device, which distributes it to the other devices. The local hub device cannot send orders to the Toast platform cloud-based service when offline.

