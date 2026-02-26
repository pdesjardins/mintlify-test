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
keywords: ["quote", "time", "strategy", "settings"]
procedures: 0
codeExamples: 0
---

The following table provides information about the quote time strategies available on the Takeout & deliverypage in Toast Web.



> **Note**
> 
> Changes to quote times are reflected on the [Online ordering dashboard](adminGuide-adminOnlineOrderingDashboard) and on [Orders Hub](adminGuide-platformOrdersHubOverview).



<table>
  <thead>
    <tr>
      <th>Quote time strategy</th>
      <th>Configuration</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>SmartQuote</td>
      <td>The amount of time calculated by the Toast platform that the kitchen needs to prepare the items in an order placed for takeout or delivery. <ul><li>Specify minimum and maximum prep times in hours and minutes.</li></ul></td>
    </tr>
    <tr>
      <td>Manual</td>
      <td>The amount of time the kitchen needs to prepare the items in an order placed for takeout or delivery.<ul><li>Specify time in hours and minutes.</li><li>Adjust time by five minute increments.</li></ul></td>
    </tr>
    <tr>
      <td>Kitchen capacity</td>
      <td>When using Kitchen capacitystrategy, the Toast platform automatically alerts you if the time slot when placing a future or immediate order is full.<ul><li>Order volume number must be between 1 and 99.</li><li>Item volume number must be between 1 and 99.</li></ul><br/>As an additional setting, enter order price rules for Toast online orders.<ul><li>Enter a price and additional time. The additional time is added to the takeout and delivery time (this only applies to first-party delivery).</li><li>Multiple price rules can be created.</li><li>If there are more than two rules, the rule with the greater price must have a greater time. For example, if a rule is any order over $10.00 has one hour added to the takeout time, then a $5.00 order cannot have a greater time. That time must be less than one hour, such as 45 minutes.</li></ul></td>
    </tr>
    <tr>
      <td>Order price</td>
      <td>The Order price strategy’s configuration is explained above in the Kitchen capacity strategy section.<br/>Enter order price rules for Toast online orders.<ul><li>Enter a price and additional time. The additional time is added to the takeout and delivery time (this only applies to first-party delivery).</li><li>Multiple price rules can be created.</li><li>If there are more than two rules, the rule with the greater price must have a greater time. For example, if a rule is any order over $10.00 has one hour added to the takeout time, then a $5.00 order cannot have a greater time. That time must be less than one hour, such as 45 minutes.</li></ul></td>
    </tr>
  </tbody>
</table>

