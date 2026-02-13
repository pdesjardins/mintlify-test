---
title: "Labor report job exclusion"
id: adminJobExclusion
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformEmployeesOmitChunkFromSearchIndex.md
parentSectionTitle: "Chapter 4. Employees"
previousSectionFile: adminGuide-adminEffectOfAutoclockOutOnBreakEntries.md
previousSectionTitle: "Effect of auto-clock out on break entries"
nextSectionFile: adminGuide-platformEmployeesOfflineModeOmitChunkFromSearchIndex.md
nextSectionTitle: "Offline support"
excerpt: "Employee jobs are either hourly job roles or salaried job roles. By default, metrics for all hourly job roles are included in the Labor summary and Hourly sales report sections of the Employee..."
procedures: 1
codeExamples: 0
---

Employee jobs are either hourly job roles or salaried job roles. By
  default, metrics for all hourly job roles are included in the
  Labor summary and Hourly sales report
  sections of the Employee performance report,
  while salaried job roles are excluded.

However, you may want to exclude certain hourly job roles from these
  report metrics, as they may negatively impact the metrics. Two examples of
  hourly roles you may want to exclude are:

- Hourly roles that are actually considered as fixed labor costs,
      such as hourly managers.


- General logins that are used by multiple employees at the same
      time, and that you do not want factored in the hourly labor
      costs.



Excluding these jobs helps you correct your reporting for the
  following labor performance metrics:

- Labor cost as a percentage of net sales.


- Sales generated per labor hour worked.



As a manager, you can measure key labor metrics with only controlled
  labor factored in, in order to better assess your restaurant's labor
  performance and make informed scheduling decisions.

After excluding specific job roles, you can then run these reports and
  obtain metrics that do not have the excluded hourly jobs factored in:

- In the Reports > Employee performance > Labor
      summary page, excluded jobs are not factored in the
      Total Pay column, while excluded job pay is not
      factored in the Total Pay/Sales column and excluded
      job hours are not factored in the Total Sales/Employee
      Hour column.


- In the Reports > Employee performance > Hourly
      sales report page, excluded job hours are not factored in the
      Labor Hrs column and excluded job pay is not
      factored in the Labor $ and Labor
      $/Net columns.



**Procedure 4.23. To configure an hourly job to be excluded from the labor
    reports**

1. [Access Toast
      Web](adminGuide-adminAccessToastAdminBackend).


2. Open the Employees > Employee management >
      Jobs page.


3. Select an hourly job to be configured.


4. In the Reporting section of the
      Job page, select the Do not include hours
      and pay under this job in restaurant labor summary reporting
      button.

![Configuration option for excluding a job from the labor reports.](https://doc.toasttab.com/doc/media/employees-job-exclusion-config.png)

Note that the Reporting section is not
      available for salary jobs.


5. Save and publish the page.



