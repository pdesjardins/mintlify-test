---
title: "Quote time strategy settings"
id: adminQuoteTimeStrategySettings
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminQuoteTimeStrategyOmitChunkFromSearchIndex.md
parentSectionTitle: "Quote time strategy"
previousSectionFile: adminGuide-adminQuoteTimeStrategies.md
previousSectionTitle: "Quote time strategies"
nextSectionFile: adminGuide-adminUsingQuoteTimeStrategiesOffline.md
nextSectionTitle: "Using quote time strategies offline"
excerpt: "The following table provides information about the quote time strategies available on the Takeout & delivery page in Toast Web."
keywords: [quote,time,strategy,settings]
procedures: 0
codeExamples: 0
---

### Quote time strategy settings

The following table provides information about the quote time strategies available on the Takeout & deliverypage in Toast Web.



> **Note**
> 
> Changes to quote times are reflected on the [Online ordering dashboard](adminOnlineOrderingDashboard.html) and on [Orders Hub](platformOrdersHubOverview.html).


| Quote time strategy | Configuration | 
| --- | --- |
| SmartQuote | The amount of time calculated by the Toast platform that the kitchen needs to prepare the items in an order placed for takeout or delivery. - Specify minimum and maximum prep times in hours and minutes.

 | 
| Manual | The amount of time the kitchen needs to prepare the items in an order placed for takeout or delivery.- Specify time in hours and minutes.
- Adjust time by five minute increments.

 | 
| Kitchen capacity | When using Kitchen capacitystrategy, the Toast platform automatically alerts you if the time slot when placing a future or immediate order is full.- Order volume number must be between 1 and 99.
- Item volume number must be between 1 and 99.

As an additional setting, enter order price rules for Toast online orders.- Enter a price and additional time. The additional time is added to the takeout and delivery time (this only applies to first-party delivery).
- Multiple price rules can be created.
- If there are more than two rules, the rule with the greater price must have a greater time. For example, if a rule is any order over $10.00 has one hour added to the takeout time, then a $5.00 order cannot have a greater time. That time must be less than one hour, such as 45 minutes.

 | 
| Order price | The Order price strategy’s configuration is explained above in the Kitchen capacity strategy section.Enter order price rules for Toast online orders.- Enter a price and additional time. The additional time is added to the takeout and delivery time (this only applies to first-party delivery).
- Multiple price rules can be created.
- If there are more than two rules, the rule with the greater price must have a greater time. For example, if a rule is any order over $10.00 has one hour added to the takeout time, then a $5.00 order cannot have a greater time. That time must be less than one hour, such as 45 minutes.

 | 

