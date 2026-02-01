---
title: "Job-based access overview"
id: platformJobBasedAccessOverview
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformJobBasedAccessOmitChunkFromSearchIndex.md
parentSectionTitle: "Job-based access"
previousSectionFile: adminGuide-platformJobBasedAccessOmitChunkFromSearchIndex.md
previousSectionTitle: "Job-based access"
nextSectionFile: adminGuide-platformManageJobBasedAccess.md
nextSectionTitle: "Managing job-based access"
excerpt: "The..."
keywords: ["jobbased", "access", "overview"]
procedures: 0
codeExamples: 0
---

### Job-based access overview

The job-based access setting allows you to configure an employee’s permissions based on their clocked-in job. This ensures the correct level of permissions for your employee even if they are assigned multiple jobs. For example, if you have an employee that is assigned both a server job and a manager job, if they clock in as a server, they will only be granted the permissions associated with the server job.

For employees with manager jobs, permissions are granted depending on if they are either salary or hourly. For employees with salary manager jobs, permissions are granted even when the employee is clocked out. Meaning, salaried managers have 24/7 manager permissions. For employees with hourly manager jobs, permissions are only granted for the time the employee is clocked in. If the hourly manager is clocked in under a different job or not clocked in at all, they are not granted manager permissions.

