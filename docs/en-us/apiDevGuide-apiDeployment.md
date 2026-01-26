---
title: "Deployment best practices"
id: apiDeployment
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-generalToastApiInformationOmitChunkFromSearchIndex.md
parentSectionTitle: "General Toast API information"
previousSectionFile: apiDevGuide-apiExampleRequests.md
previousSectionTitle: "Example API requests"
nextSectionFile: apiDevGuide-apiHandlingDowntimes.md
nextSectionTitle: "Handling Toast API downtime"
excerpt: "When you deploy updates to your integration, use the following best practices:"
keywords: [Do not deploy on weekends,Avoid peak traffic hours,Deploy updates incrementally,Monitor errors and roll back if needed]
procedures: 0
codeExamples: 0
---

### Deployment best practices

When you deploy updates to your integration, use the following best practices:



****Do not deploy on weekends****
: Only deploy updates on Monday through Thursday.

Do not deploy updates on Fridays, Saturdays, or Sundays, because of the increased restaurant activity on weekends and the reduced availability of Toast technical support.



****Avoid peak traffic hours****
: Restaurants' peak traffic tends to happen at evening mealtime. Do not deploy significant integration updates between 20:00 UTC and 02:00 UTC.

These hours correspond to evening meal rush times for a majority of Toast platform restaurants in their local timezones.



****Deploy updates incrementally****
: Deploy updates to a small percentage of customers first and gradually increase the deployment percentage over time.

Toast support recommends that you first deploy to 1% of customers, then to 5%, then 10%, 25%, 50%, and finally 100%.



****Monitor errors and roll back if needed****
: Monitor errors while you deploy updates.

If you see a significant increase in errors or latency after you deploy your change, then roll back your updates.





