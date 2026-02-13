---
title: "Analytics API overview"
id: apiAnalyticsOverview
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiAboutAnalyticsOmitChunkFromSearchIndex.md
parentSectionTitle: "About the analytics API"
previousSectionFile: apiDevGuide-apiAboutAnalyticsOmitChunkFromSearchIndex.md
previousSectionTitle: "About the analytics API"
nextSectionFile: apiDevGuide-apiAnalyticsUnderstandingProcess.md
nextSectionTitle: "Understanding the analytics API process"
externalReferences: [https://www.toasttab.com/customers/shop/software-services/restaurant-management-suite?tier=Pro]
excerpt: "You can use the analytics API to request and view analytics data for restaurants in a management group."
keywords: ["analytics", "overview"]
procedures: 0
codeExamples: 0
---



> **Important**
> 
> All metric data supported in the analytics API does not adhere
        to accounting standards such as GAAP rules. This information is solely
        for informational purposes. Toast, Inc. does not offer accounting or
        tax advice.


You can use the analytics API to request and view analytics data
      for restaurants in a [management group](adminGuide-adminManagementGroup).



> **Note**
> 
> Access to the analytics API requires an active subscription to
        [Toast
        Restaurant Management Suite Pro](https://www.toasttab.com/customers/shop/software-services/restaurant-management-suite?tier=Pro) or higher.


You can use the analytics API to:

- Retrieve aggregated sales reporting data, which provides a
          high-level view of orders data for a restaurant. This includes sales
          and labor information. For more information, see [Aggregated sales reporting data overview](apiDevGuide-apiAnalyticsMetricsReportingDataOverview).


- Retrieve check reporting data, which provides a detailed look
          at checks for a restaurant for a single day. For more information,
          see [Check reporting data overview](apiDevGuide-apiAnalyticsCheckReportingDataOverview).


- Retrieve labor reporting data, which provides a detailed look
          at employee and job information. For more information, see [Labor reporting data overview](apiDevGuide-apiAnalyticsLaborReportingDataOverview).


- Retrieve menu reporting information, which provides a detailed
          look at menu and menu entity information. For more information, see
          [Menu reporting data overview](apiDevGuide-apiAnalyticsMenuReportingDataOverview).


- Retrieve payout reporting data, which provides a detailed look
          at all deposits made to an account. For more information, see [Payout reporting data overview](apiDevGuide-apiAnalyticsPayoutReportingDataOverview).


- Retrieve guest reporting information, which provides a look at
          payment details associated with a guest's payment card. For more
          information, see [Guest reporting data overview](apiDevGuide-apiAnalyticsGuestDataOverview).


- Retrieve restaurant information, which provides the names and
          GUIDs for restaurants in a management group. For more information,
          see [Restaurant information overview](apiDevGuide-apiAnalyticsRestaurantInfoOverview).



Toast APIs, including the analytics API, control access to
      integration functionality using client authentication. When you
      authenticate your API client you use client credentials that you get
      from the Toast integrations team. The Toast platform includes different
      API integration types and uses separate API client credentials for each
      integration type. For information about using client credentials to
      authenticate and access Toast APIs, see [Authentication and restaurant access](apiDevGuide-authentication).

**Important information about analytics API client authentication
        credentials**

- Analytics API authentication credentials are different from
          other Toast API authentication credentials.


- If your organization has access to other Toast APIs, you
          cannot use the authentication credentials for other Toast APIs to
          access the analytics API. You must use separate client
          authentication credentials for the analytics API.



