---
title: "Understanding the analytics API process"
id: apiAnalyticsUnderstandingProcess
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiAboutAnalyticsOmitChunkFromSearchIndex.md
parentSectionTitle: "About the analytics API"
previousSectionFile: apiDevGuide-apiAnalyticsOverview.md
previousSectionTitle: "Analytics API overview"
nextSectionFile: apiDevGuide-apiAnalyticsScope.md
nextSectionTitle: "Required scope for the analytics API"
excerpt: "Retrieving the analytics data involves two steps:"
keywords: [understanding,analytics,process,reportRequestGuid]
procedures: 0
codeExamples: 0
---

### Understanding the analytics API process

Retrieving the analytics data involves two steps:

1. Creating a request for the analytics data and receiving a request identifier


2. Retrieving the analytics data using the request identifier





> **Note**
> 
> The `reportRequestGuid` expires seven days after you create it. Using an expired or invalid `reportRequestGuid`results in a 404 error. The `message` of the response body contains additional information about the cause of the error.


To create a request, you send a `POST`request to the endpoint corresponding to the type and time range of the analytics data you want. When creating the request, you specify what to include in the analytics data and how you want it to be organized in query parameters and the message body. The analytics API then returns the `reportRequestGuid`, the unique identifier used to identify this request.

To retrieve the analytics data, you send a `GET` request to the endpoint corresponding to the type and time range of the initial request for analytics data. You include the `reportRequestGuid` in the request to retrieve the analytics data you defined when creating the request. The API then returns the analytics data.

