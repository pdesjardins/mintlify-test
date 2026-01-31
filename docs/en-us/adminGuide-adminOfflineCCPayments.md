---
title: "Offline card payments"
id: adminOfflineCCPayments
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformPaymentsOfflineModeOmitChunkFromSearchIndex.md
parentSectionTitle: "Offline support"
previousSectionFile: adminGuide-platformPaymentsOfflineModeOmitChunkFromSearchIndex.md
previousSectionTitle: "Offline support"
nextSectionFile: adminGuide-adminCompletingShiftReviewOffline.md
nextSectionTitle: "Completing shift review offline"
excerpt: "During offline mode, you can still take card payments. When you process a card payment in offline mode, the Toast POS app takes the card information, encrypts it, and stores it on the Toast POS..."
keywords: [offline,card,payments]
procedures: 0
codeExamples: 0
---

### Offline card payments

During offline mode, you can still take card payments. When you process a card payment in offline mode, the Toast POS app takes the card information, encrypts it, and stores it on the Toast POS device. When the device is back online, the system sends the stored card information to the card networks for authorization.



> **Important**
> 
> There is a risk associated with taking offline payments, because payments cannot be verified until the Internet connection is restored. This means an offline payment can be denied when your system returns online. Please be aware that you are responsible for any declined, expired, or disputed payments while operating in offline mode. If this is a concern, you should select Continue accepting card payments without waiting for authorization as your background processing mode. For more information about the processing modes, see [processing modes](adminOfflineCCPayments.html#adminOfflineCCProcessing). Toast strongly recommends tablets that have taken offline payments return online within three days, preferably within 24 hours, to mitigate the possibility of a chargeback.


#### Card authorizations and payment disruptions

You can set the Card authorization and payment disruption option to control whether your restaurant can still process card transactions after losing its connectivity. As part of the card payment workflow, card authorization requests are processed in real time or in the background, depending on the configured Card authorization and payment disruptionsetting.

You can also set a transaction limit for offline transactions which allows you to limit the dollar amount of credit card transactions taken offline. Transactions above the configured amount require manager approval and this limit does not include gratuity.

**Procedure 6.127. Configure card authorizations during a disruption**

1. [Access Toast Web ](platformToastPlatformConceptsOmitChunkFromSearchIndex.html#adminAccessToastAdminBackend).


2. Select Payments > Payment options. Scroll down to the Card authorization and payment disruptions section.


3. Select a setting that determines the card authorization experience:

- Continue accepting card payments without waiting for authorization (recommended): Payments are stored in the background and submitted when the outage is resolved. There is a risk cards could be declined after guests leave. This option is especially useful for quick service restaurants with a high volume of transactions that are willing to accept the risk of losing a payment in exchange for optimal speed in processing the payment.



> **Note**
> 
> If your Toast POS device is offline, managers with the 6.3 Payments Setup permission can temporarily override the card authorization experience setting at the POS and accept card payments for background processing. Card payments taken during offline mode are stored and submitted once the Toast POS is online.



- Do not accept card payments (wait until authorization is available): You will not be able to accept card payments during a disruption. Guests will need to use an alternate payment method, such as cash. You will not be at risk of declined card payments. While this option has low financial risk, the guest experience could be impacted.




4. With the Transaction Limit setting, you can optionally set a dollar amount limit for credit card transactions taken while in offline mode. Note that this threshold is not applied to employees who have the [Offline/Background Credit Card Processing](platformEmployeesOmitChunkFromSearchIndex.html#permissionOfflineCCProcessing) permission. A payment larger than the configured threshold requires manager approval.


5. Save and publish your changes.



#### Auto-capturing payments

The Toast POS device auto-captures card payments every night after closeout. The card payments authorized throughout the day are captured into a batch to be processed. Once this process occurs, the payments cannot be updated with tips or otherwise adjusted in any way.

If your Toast POS device is offline and an auto-capture is approaching, contact Toast support to temporarily disable auto-capture until your Internet connection is re-established. Disabling auto-capture ensures Toast does not capture your card payments until you have properly updated them, such as entering card tips.

#### Card pre-authorization

In offline mode, the Toast POS app cannot communicate with credit card payment processors. Therefore, if you use the credit/debit card pre-authorization feature, cards cannot be pre-authorized in offline mode.

However, if a card was pre-authorized before going into offline mode, the card information is preserved and can be used as a form of payment when online mode returns. As with any card payment, if you close a check using the Saved CC option in offline mode, which was pre-authorized before going offline, it will be processed after the device comes back online.

