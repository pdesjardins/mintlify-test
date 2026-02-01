---
title: "Performing shift review when using device groups"
id: performingShiftReviewWhenUsingDeviceGroups
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformShiftReviewOmitChunkFromSearchIndex.md
parentSectionTitle: "Shift review"
previousSectionFile: adminGuide-platformReviewingEmployeeShifts.md
previousSectionTitle: "Reviewing employee shifts"
nextSectionFile: adminGuide-platformCloseOutDayOmitChunkFromSearchIndex.md
nextSectionTitle: "Close out day"
externalReferences: [https://central.toasttab.com/s/article/Device-Groups]
excerpt: "In high volume restaurants with a lot of orders, the number of orders each device must maintain in memory can have an impact on performance. As a solution to this issue, you can split your devices..."
keywords: ["performing", "shift", "review", "device", "groups"]
procedures: 0
codeExamples: 0
---

### Performing shift review when using device groups



> **Note**
> 
> Toast is phasing out device groups and instead recommending restaurants use service area, dining option, or revenue center configurations to segment their restaurant operations. For more information, see this [Toast Central article](https://central.toasttab.com/s/article/Device-Groups).


In high volume restaurants with a lot of orders, the number of orders each device must maintain in memory can have an impact on performance. As a solution to this issue, you can split your devices into device groups. Devices in a device group share orders with each other but not with other devices outside of their device group. This approach reduces the number of orders each device must maintain in memory.

In the following illustration, the restaurant does not use device groups and all orders are maintained in memory on all devices:

![Image](https://doc.toasttab.com/doc/media/device-groups-without-device-groups.png)

In this illustration, the restaurant splits its devices into two groups, Dining Room and Bar, and the devices associated with those groups only need to maintain a portion of the restaurant's orders in memory.

![Image](https://doc.toasttab.com/doc/media/device-groups-with-device-groups.png)

Toast support can help you determine if your restaurant should use device groups or not. If you do use device groups, the name of the device group a device belongs to is listed on the Toast POS home screen, the device setup screen, and the POS access code screen, as a prefix to the restaurant name and location, allowing you to quickly tell which device group a device belongs to.

![Image](https://doc.toasttab.com/doc/media/device-groups-device-group-name.png)

Also, if your restaurant uses device groups, your servers must be aware of them during shift reviews. For a server to complete a shift review, all of the server's orders must be closed. In a restaurant that uses device groups, it is possible to have an open order in one device group while trying to complete a shift review from a device in another device group. In this situation, the server will not be able to see the open order that is preventing the shift review from being completed because the device they are using for shift review can only access orders in its own device group. To prevent this issue, servers should close all the open orders they have across all device groups before attempting a shift review.

