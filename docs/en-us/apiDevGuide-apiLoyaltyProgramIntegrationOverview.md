---
title: "Loyalty program integration overview"
id: apiLoyaltyProgramIntegrationOverview
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiBuildingALoyaltyIntegrationOmitChunkFromSearchIndex.md
parentSectionTitle: "Loyalty program integrations"
previousSectionFile: apiDevGuide-apiBuildingALoyaltyIntegrationOmitChunkFromSearchIndex.md
previousSectionTitle: "Loyalty program integrations"
nextSectionFile: apiDevGuide-apiLoyaltyIntegrationOverview.md
nextSectionTitle: "Loyalty integration implementation"
excerpt: "You can use the Toast loyalty integration API to integrate your loyalty program with the Toast platform."
keywords: ["loyalty", "program", "integration", "overview"]
procedures: 0
codeExamples: 0
---

You can use the Toast loyalty integration API to integrate your loyalty program with the Toast platform.

**Integration overview**

- Toast POS restaurant employees can select a Rewards button while processing a guest transaction. The Rewards button prompts the employee to find the guest's loyalty account. Employees can manually enter a guest's loyalty account identifier, swipe a guest’s rewards card, scan a QR code, or search for a loyalty account by name, phone number, or email.


- After the employee finds a guest's loyalty account, rewards that are available are displayed along with a Redeembutton.


- The employee selects the Redeem button for a reward. The reward appears as a negative amount in the check price.

The employee selects Redeem for additional rewards if the guest wants to redeem them.


- Rewards can apply either check-level or item-level discounts.


- You manage all validation logic and discount totals on behalf of your restaurant client.


- Accruing rewards happens asynchronously after the restaurant guest pays the check.


- You provide information about loyalty program use to the restaurants you work with. For example, information about rewards offers used and sales information related to those offers.





> **Note**
> 
> Toast loyalty integration API integrations are not supported when a restaurant experiences an Internet outage or other network disruption. When a restaurant does not have a functioning network, it is in *offline mode*. For more information, see [Offline mode overview](adminGuide-adminOfflineModeOverview).




> **Note**
> 
> Toast Loyalty balances cannot be retrieved using the Toast APIs.


