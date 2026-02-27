---
title: "Post-outage experience"
id: platformPostOutage
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformPaymentsOfflineModeOmitChunkFromSearchIndex.md
parentSectionTitle: "Offline support"
previousSectionFile: adminGuide-adminPendingTipsWhenOffline.md
previousSectionTitle: "Pending tips when offline"
nextSectionFile: adminGuide-platformPublishingDocsOmitChunkFromSearchIndex.md
nextSectionTitle: "Chapter 7. Publishing"
excerpt: "After..."
keywords: ["postoutage", "experience"]
procedures: 0
codeExamples: 0
---

After your Toast POS device goes offline, network-dependent payment methods, such as gift cards or loyalty redemptions, become inactive. However, you can still accept card payments. Card payments are held in a payment queue and are submitted for processing once your Toast POS device is online again.



> **Note**
> 
> To enable card payment queuing, navigate to and select Continue accepting card payments without waiting for authorization (recommended).


Once your Toast POS device is online: 

- Queued card payments are submitted for processing.


- You can resume using payment methods that require a connection to Toast. Such payment methods include gift cards, loyalty redemptions, and other payment types that require network or internet access.


- You can continue guest lookup actions including gift card, loyalty, and house account guest lookup.



- Payments process normally and the guest is charged as expected.


- Payments can show one of the following status tags after your Toast POS device is back online. Tags display on top of the check’s payment method, as shown below.



![Location of the status tag.](https://doc.toasttab.com/doc/media/pwfPostOutagetagLocation.png)

The below table contains the possible payment tags and their descriptions.


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className=""><div className=""><p className="text-base leading-relaxed">Tag</p></div></th>
      <th className=""><div className=""><p className="text-base leading-relaxed">Descriptions</p></div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Voiding </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"> A payment is actively being voided. This means the payment was authorized, but is being canceled prior to capture, and the cardholder will not be charged. </p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4">Refunded</div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"> A payment was authorized and captured successfully, then returned to the cardholder. </p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Authorized</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">A payment was submitted and is expected to process when captured. No further action is needed.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Captured</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"> A payment has been successfully processed, and is expected to settle with the merchant. </p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Backgrounded</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"> A card payment was attempted while offline and the check was closed. However, when the Toast POS device reconnected to the network, the payment was declined. Checks with this tag are moved from closed status to open status once the device is back online.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Declined</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The card payment used while offline was declined after your Toast POS device reconnected.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Yellow pending</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">A yellow pending tag indicates the payment is queued for payment processing. While payments are pending, do not: </p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">Delete your Toast POS device's memory.</p></li><li className=""><p className="text-base leading-relaxed">Uninstall the Toast POS app.</p></li></ul> <p className="text-base leading-relaxed"> Taking either of these actions can result in losing pending payments. Lost payments cannot be recovered. If your Toast POS device doesn't have Internet connectivity, attempt to reconnect your Toast POS device to your network as soon as possible. </p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Red pending</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">A red pending tag indicates the payment was queued for processing, but payments are now paused. To resolve, refer to the red banner at the top of the Toast POS device, as shown in the image below. Paused card payments must be resolved before continuing to process a pending payment. While payments are pending, do not: </p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">Delete your Toast POS device's memory.</p></li><li className=""><p className="text-base leading-relaxed">Uninstall the Toast POS app.</p></li></ul> <p className="text-base leading-relaxed"> Taking either of these actions can result in losing pending payments. Lost payments cannot be recovered. If your Toast POS device doesn't have Internet connectivity, attempt to reconnect your Toast POS device to your network as soon as possible. </p>![Pending red banner.](https://doc.toasttab.com/doc/media/pwfVoidsRedPendingBanner.png)</div></td>
    </tr>
  </tbody>
</table>
</div>

