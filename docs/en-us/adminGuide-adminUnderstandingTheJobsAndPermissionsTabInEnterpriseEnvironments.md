---
title: "Understanding the Jobs and Permissions tab in enterprise environments"
id: adminUnderstandingTheJobsAndPermissionsTabInEnterpriseEnvironments
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminWorkingWithJobsAndEmployeesInEnterprisesOmitChunkFromSearchIndex.md
parentSectionTitle: "Jobs and employees in enterprises"
previousSectionFile: adminGuide-adminAssigningRestaurantAccess.md
previousSectionTitle: "Assigning restaurant access"
nextSectionFile: adminGuide-adminAssigningRestaurantGroupLevelPermissions.md
nextSectionTitle: "Assigning restaurant group-level permissions"
excerpt: "The Jobs and Permissions tab on the employee details page has two sections, the Jobs section and the Access Permissions section. These two sections are closely related to one another but behave..."
keywords: ["understanding", "jobs", "permissions", "enterprise", "environments"]
procedures: 0
codeExamples: 0
---

### Understanding the Jobs and Permissions tab in enterprise environments

The Jobs and Permissions tab on the employee details page has two sections, the Jobs section and the Access Permissions section. These two sections are closely related to one another but behave somewhat differently with respect to enterprise environments.

![Image](https://doc.toasttab.com/doc/media/mjm-jobs-and-permissions-tab.PNG)

The Jobs portion of the tab shows the jobs that can be, and have been, assigned to the employee whose details you are viewing. This list is limited to jobs that are applicable *to the session restaurant*. For example, if you are logged into the Boston location, this list contains jobs whose Apply To property is set to the Boston location or one of its ancestors in the restaurant group hierarchy. The Apply To setting is described in detail in [Applying jobs to the restaurant group hierarchy](adminApplyingJobsToTheRestaurantGroupHierarchy.html).

By contrast, the Access Permissions area reflects the employee's permissions *across the entire enterprise*. This means that you may see permissions in the Access Permissions entries that reflect jobs that are not listed in the Jobs area. For example, consider the following scenario.

The Rider's Grill enterprise has these jobs:

- Server, applies to the entire corporation, gives the seventeen permissions in the the POS Access section.


- Key Employee - Boston, applies to the Boston location only, gives the Void Items/Orders permission and Void Refund/Payments permissions.


- Key Employee - Burlington, applies to the Burlington location only, gives the Discounts permission.



Rider's Grill has an employee, Samuel Server, with these characteristics:

- Samuel Server has [restaurant access](adminAssigningRestaurantAccess.html)to both the Boston and Burlington locations.


- At the Boston location, Samuel Server is assigned the Server job and the Key Employee - Boston job.


- At the Burlington location, Samuel Server is assigned the Server job and the Key Employee - Burlington job.



When you log into the Boston location in Toast Web and view Samuel Server's employee details, you see that he is assigned the Server and Key Employee - Boston jobs. There is no evidence of the Key Employee - Burlington job assignment in the Jobs area because you are logged into the Boston location.

When you look at Samuel Server's access permissions, however, you see entries for the Boston and Burlington locations. If you expand the Boston access permissions entry, you see that Samuel Server has the seventeen POS Access permissions from the Server job and the Void Items/Orders permission and Void Refund/Payments permissions from the Key Employee - Boston job. If you expand the Burlington access permissions entry, you see that Samuel Server has the seventeen POS Access permissions from the Server job and the Discounts permission from the Key Employee - Burlington job.

