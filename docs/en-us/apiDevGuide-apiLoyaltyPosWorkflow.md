---
title: "POS workflow"
id: apiLoyaltyPosWorkflow
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiBuildingALoyaltyIntegrationOmitChunkFromSearchIndex.md
parentSectionTitle: "Loyalty program integrations"
previousSectionFile: apiDevGuide-apiLoyaltyTransactionDescriptions.md
previousSectionTitle: "Transaction types"
nextSectionFile: apiDevGuide-apiLoyaltyKioskWorkflow.md
nextSectionTitle: "Kiosk workflow"
excerpt: "This section describes the user interface workflow for loyalty transactions in the Toast POS app."
keywords: ["workflow"]
procedures: 1
codeExamples: 0
---

This section describes the user interface workflow for loyalty transactions in the Toast POS app.

1. The Rewards button is listed as a menu group. When you open the Rewards group, you see the Lookup Customer button.

![Image](https://doc.toasttab.com/doc/media/image1.png)


2. The Lookup button opens a dialog box that a restaurant employee uses to key in, swipe, scan, or search (by name, email, or phone) to find the loyalty program account for a restaurant guest.

![Image](https://doc.toasttab.com/doc/media/loyalty_lookup.png)


3. After the employee finds the loyalty program account for the guest, a list of loyalty program offers is displayed. If an offer is item-level, it specifies the Toast POS identifier for the selection (GUID). If that selection is not in the check, it is disabled.

![Image](https://doc.toasttab.com/doc/media/image4.png)


4. After adding items to the check, the restaurant employee returns to the rewards screen (using the Look Up Customerbutton). Additional offers may be eligible.

The restaurant employee selects the Redeembutton to add an offer to the check. Offers that are not eligible for redemption on the current check are disabled and the redeem button will not be shown.

Offers will display on the POS alphabetically by name.

![Image](https://doc.toasttab.com/doc/media/image2.png)


5. The rewards is added to the check as a discount.



