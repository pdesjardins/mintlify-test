---
title: "Understanding data aggregation in enterprise reports"
id: adminUnderstandingDataAggregationEnterpriseReports
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminUsingReportsEnterprisesOmitChunkFromSearchIndex.md
parentSectionTitle: "Reports for enterprises"
previousSectionFile: adminGuide-adminEnterpriseReportsOverview.md
previousSectionTitle: "Enterprise reports overview"
nextSectionFile: adminGuide-adminUnderstandingVersionedEntitiesEnterpriseReports.md
nextSectionTitle: "Understanding versioned entities in enterprise reports"
excerpt: "Many of the reports break out the data you are viewing by location and include a Location column. You can use this column to sort the data by location. The Reports > Sales > Orders report uses this..."
keywords: ["understanding", "data", "aggregation", "enterprise", "reports"]
procedures: 0
codeExamples: 0
---

Many of the reports break out the data you are viewing by location
    and include a Location column. You can use this
    column to sort the data by location. The Reports > Sales >
    Orders report uses this approach:

![Image](https://doc.toasttab.com/doc/media/mmm_reports_orders_tab_sales_report.PNG)

Other reports aggregate the data from your restaurant group/location
    selections without breaking it out by location. For example, the
    Reports > Employee performance > Labor summary
    report includes a Job Title table that lists all the
    jobs assigned to employees at the locations you have selected, without
    identifying which locations or restaurant groups the jobs apply to:

![Image](https://doc.toasttab.com/doc/media/mmm_reports_summary_tab_labor_report.PNG)

For reports that aggregate data without breaking it out by location,
    it is useful to use identifying naming conventions. For example, instead
    of having a "Manager" job for the Northeast restaurant group and a
    "Manager" job for the Southeast restaurant group, which would both appear
    as "Manager" in the Job Title table, you can use
    names like "Manager - NE" and "Manager - SE" to distinguish them.

