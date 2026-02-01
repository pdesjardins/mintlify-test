---
title: "Understanding data discrepancies"
id: apiAnalyticsDataDiscrepancies
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiAboutAnalyticsOmitChunkFromSearchIndex.md
parentSectionTitle: "About the analytics API"
previousSectionFile: apiDevGuide-apiAnalyticsRateLimiting.md
previousSectionTitle: "Analytics API rate limits"
nextSectionFile: apiDevGuide-apiAnalyticsInactiveRestaurantData.md
nextSectionTitle: "Viewing inactive restaurant data"
excerpt: "Data discrepancies can occur..."
keywords: [understanding,data,discrepancies]
procedures: 0
codeExamples: 0
---

### Understanding data discrepancies

Data discrepancies can occur when orders are modified. When an order is modified, the changes are updated in the analytics data. The time until the analytics data reflects this update depends on the when the order is modified and when the order was originally scheduled for fulfillment:



> **Note**
> 
> The date an order was originally scheduled for fulfillment is considered the *initial order open date*.


- If an order is modified within the range of 11 days before or two days after the *initial order open date*, the analytics data is updated within two and four hours of when the order was modified.


- If an order is modified outside that range of 11 days before or two days after the *initial order open date*, the analytics data is updated within six days of when the order was modified.



For example, an order is created on September 8 and scheduled for fulfillment on September 10. September 10 is the *initial order open date*, while September 8 is the day the order was created. If the guest calls and changes the order to be scheduled for September 12 instead, September 10 remains the *initial order open date*, but the new date for scheduled fulfillment becomes September 12.

For example, an order is scheduled for August 15, which is the *initial order open date*. If the order is modified between August 4 and August 17, the modification is reflected in the analytics data within two to four hours. If the order is modified before August 4 or after August 17, the modification is reflected in the analytics data within six days. If the order is modified on August 18, then the data is updated by August 24, six days after the order is modified.

