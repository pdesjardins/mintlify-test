---
title: "Kiosk workflow"
id: apiLoyaltyKioskWorkflow
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiBuildingALoyaltyIntegrationOmitChunkFromSearchIndex.md
parentSectionTitle: "Loyalty program integrations"
previousSectionFile: apiDevGuide-apiLoyaltyPosWorkflow.md
previousSectionTitle: "POS workflow"
nextSectionFile: apiDevGuide-apiLoyaltyDiscountProcessing.md
nextSectionTitle: "Reward offers processing"
externalReferences: [https://central.toasttab.com/s/article/Kiosk-Placing-Orders-Making-Payments-and-Tipping]
excerpt: "This section describes the user interface workflow for loyalty transactions in Toast Kiosk."
keywords: ["kiosk", "workflow", "LOYALTY_INQUIRE", "Offer", "LOYALTY_REDEEM", "LOYALTY_ACCRUE"]
procedures: 1
codeExamples: 0
---

This section describes the user interface workflow for loyalty transactions in Toast Kiosk.

1. On the Kiosk device, the guest taps the **START** button.


2. The guest adds items to their order. For more information, see the [Toast Central article](https://central.toasttab.com/s/article/Kiosk-Placing-Orders-Making-Payments-and-Tipping) about placing an order using Toast Kiosk. 



> **Note**
> 
> The guest can add rewards to their order at any point before checkout.



3. On the bottom right of the screen, the guest taps the **+ Add rewards** button.

![Image](https://doc.toasttab.com/doc/media/loyalty-kiosk-workflow-1.png)


4. On the **Loyalty + Rewards** screen, the guest can do one of the following: 

- Tap the **SCAN CODE** button and scan the QR code on a loyalty card or app.


- Swipe a loyalty card.



Your integration will receive a `LOYALTY_INQUIRE`request.


5. Next to the discount they want to apply, the guest taps **Redeem**. Offers that are not eligible for redemption on the current check are disabled and the **Redeem** button is shaded gray.



> **Important**
> 
> Partners are responsible for confirming which offers are eligible for redemption, using the `applicable` boolean in the `Offer` object.


![Image](https://doc.toasttab.com/doc/media/loyalty-kiosk-workflow-3.png)

The reward is added to the check as a discount.

![Image](https://doc.toasttab.com/doc/media/loyalty-kiosk-workflow-4.png)


6. The guest continues adding items to their order, or checkout. When the payment process starts, your integration will receive a `LOYALTY_REDEEM` request. Once the payment is completed, your integration will receive a `LOYALTY_ACCRUE`request.



