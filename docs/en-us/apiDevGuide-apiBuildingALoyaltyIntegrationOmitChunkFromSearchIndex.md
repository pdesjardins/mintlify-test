---
title: "Loyalty program integrations"
id: apiBuildingALoyaltyIntegrationOmitChunkFromSearchIndex
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-portalOutboundIntegrationsOmitChunkFromSearchIndex.md
parentSectionTitle: "Chapter 10. Outbound integrations"
previousSectionFile: apiDevGuide-apiGiftCardIntegrationReferenceApiImplementation.md
previousSectionTitle: "Reference gift card API implementation"
nextSectionFile: apiDevGuide-apiLoyaltyIntegrationOverview.md
nextSectionTitle: "Loyalty integration implementation"
procedures: 0
codeExamples: 0
---

## Loyalty program integrations

### Loyalty program integration overview

You can use the Toast loyalty integration API to integrate your loyalty program with the Toast platform.

**Integration overview**

- Toast POS restaurant employees can select a Rewardsbutton while processing a guest transaction. The Rewardsbutton prompts the employee to find the guest's loyalty account. Employees can manually enter a guest's loyalty account identifier, swipe a guest’s rewards card, scan a QR code, or search for a loyalty account by name, phone number, or email.


- After the employee finds a guest's loyalty account, rewards that are available are displayed along with a Redeembutton.


- The employee selects the Redeembutton for a reward. The reward appears as a negative amount in the check price.

The employee selects Redeemfor additional rewards if the guest wants to redeem them.


- Rewards can apply either check-level or item-level discounts.


- You manage all validation logic and discount totals on behalf of your restaurant client.


- Accruing rewards happens asynchronously after the restaurant guest pays the check.


- You provide information about loyalty program use to the restaurants you work with. For example, information about rewards offers used and sales information related to those offers.





> **Note**
> 
> Toast loyalty integration API integrations are not supported when a restaurant experiences an Internet outage or other network disruption. When a restaurant does not have a functioning network, it is in *offline mode*. For more information, see [adminGuide#adminOfflineModeOverview].




> **Note**
> 
> Toast Loyalty balances cannot be retrieved using the Toast APIs.


