---
title: "Takeout and delivery orders"
id: adminOfflineDelivery
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformOffPremiseOfflineModeOmitChunkFromSearchIndex.md
parentSectionTitle: "Offline support"
previousSectionFile: adminGuide-platformOffPremiseOfflineModeOmitChunkFromSearchIndex.md
previousSectionTitle: "Offline support"
nextSectionFile: adminGuide-adminOfflineOnlineOrdering.md
nextSectionTitle: "Toast Online Ordering"
excerpt: "You can place takeout and delivery orders when..."
keywords: ["takeout", "delivery", "orders"]
procedures: 0
codeExamples: 0
---

You can place takeout and delivery orders when the device is in offline mode. However, you cannot look up guest information to link the order to an existing guest account. If you attempt to do so, the following message displays on the lookup dialog:

![The Toast POS device showing the lookup error message in offline mode.](https://doc.toasttab.com/doc/media/offline-lookup.png)

To complete the order, you can manually enter the guest information. However, doing so may result in duplicate guest accounts after you come back online, because the Toast platform does not sync the two accounts together even if their information is identical.



> **Note**
> 
> If an employee takes a delivery payment on a device with digital receipts configured, the payment goes through but the device user is never prompted for the digital receipt options (signature and tip). On the Payment Terminal, the check is in a paid state.
> This is expected behavior in both online and offline mode. A check with the delivery dining option does not go through the tip entry and signature entry workflows, because it is assumed that a guest would not be physically present when the delivery order is placed. That is, delivery mode is meant to take payment on a device without a guest present.
> If the device is in offline mode, the payment operation may also auto switch the device user to the passcode screen.


