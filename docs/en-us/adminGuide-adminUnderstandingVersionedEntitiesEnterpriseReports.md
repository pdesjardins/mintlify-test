---
title: "Understanding versioned entities in enterprise reports"
id: adminUnderstandingVersionedEntitiesEnterpriseReports
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminUsingReportsEnterprisesOmitChunkFromSearchIndex.md
parentSectionTitle: "Reports for enterprises"
previousSectionFile: adminGuide-adminUnderstandingDataAggregationEnterpriseReports.md
previousSectionTitle: "Understanding data aggregation in enterprise reports"
nextSectionFile: adminGuide-adminEnterpriseReportDetails.md
nextSectionTitle: "Enterprise report details"
excerpt: "Versioned entities are automatically rolled up into a single entry on Toast reports. For example, consider the illustration below, which shows three versions of the Trout menu item, one for the..."
keywords: ["understanding", "versioned", "entities", "enterprise", "reports"]
procedures: 0
codeExamples: 0
---

Versioned entities are automatically rolled up into a single entry on Toast reports. For example, consider the illustration below, which shows three versions of the Trout menu item, one for the Corporate restaurant group and one each for the Boston and Burlington locations. On the **Reports &gt; Menus &gt; Product mix** report, these three versions are rolled up into a single Trout entry and their data is either averaged out (in the case of **Avg Price**) or totaled (in the case of **Item Qty** and **Gross Amount**) to produce the information you see.

![Image](https://doc.toasttab.com/doc/media/mmm_reports_version_rollup.png)

