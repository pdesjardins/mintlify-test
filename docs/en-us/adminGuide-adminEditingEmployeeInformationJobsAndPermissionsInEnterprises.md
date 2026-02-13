---
title: "Editing employee information, jobs, and permissions in enterprises"
id: adminEditingEmployeeInformationJobsAndPermissionsInEnterprises
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminWorkingWithJobsAndEmployeesInEnterprisesOmitChunkFromSearchIndex.md
parentSectionTitle: "Jobs and employees in enterprises"
previousSectionFile: adminGuide-adminAssigningRestaurantGroupLevelPermissions.md
previousSectionTitle: "Assigning restaurant group-level permissions"
nextSectionFile: adminGuide-adminUnderstandingMenuEditingPermissionsForEnterprises.md
nextSectionTitle: "Understanding menu editing permissions for enterprises"
excerpt: "For..."
keywords: ["editing", "employee", "information", "jobs", "permissions", "enterprises"]
procedures: 0
codeExamples: 0
---

For enterprises with multiple locations, it is common that one employee may need to make changes to another employee's permissions, basic information, or jobs and wages at another location. The Toast platform has a set of rules it uses to determine what changes you can make to other employees. This section describes those rules.

## Minimum permission configuration for enterprises

Toast support recommends that enterprises have at least one *super user* at the corporate level. A super user has access to all Toast permissions for the entire corporation. A Toast employee grants this level of access to the super user. The super user must then choose a minimum of one manager user at each individual location that also has access to most, if not all, permissions.

The permissions granted to the managers at individual locations are at the discretion of the super user and the super user may choose not to give certain Account Admin permissions that are related to financial data such as Financial Accounts to individual managers. However, at a minimum, individual managers should have the following permissions:

- Restaurant Admin &gt; Employee Info: Allows to the manager to edit basic employee information including first and last name, phone number, and passcode. See [Editing an employee's basic information](adminGuide-adminEditingEmployeeInformationJobsAndPermissionsInEnterprises#adminEditingAnEmployeesBasicInformation).


- Restaurant Admin &gt; Employee Jobs & Wages: Allows the manager to assign jobs to an employee, remove jobs from an employee, and override the wages associated with an employee's assigned jobs. See [Editing an employee's jobs](adminGuide-adminEditingEmployeeInformationJobsAndPermissionsInEnterprises#adminEditingAnEmployeesJobs).


- Account Admin &gt; User Permissions: Allows the manager to override the permissions an employee has inherited from any assigned jobs. This gives the manager the ability to directly add permissions to or remove permissions from a specific employee. See [Editing an employee's permissions](adminGuide-adminEditingEmployeeInformationJobsAndPermissionsInEnterprises#adminEditingAnEmployeesPermissions).



Additionally, managers can modify an employee's credentials (email and passcode) if they have a superset of the employee's permissions at all of the locations the employee works at. See [Editing an employee's basic information](adminGuide-adminEditingEmployeeInformationJobsAndPermissionsInEnterprises#adminEditingAnEmployeesBasicInformation) for more details.

## Editing an employee's basic information

The Basic tab of the employee's details page contains core employee information such as first and last name, phone number, and email address:

![Image](https://doc.toasttab.com/doc/media/mjm-basic-tab.PNG)

To edit an employee's information (with the exception of email and POS access code, which have additional restrictions described below), you must have the Restaurant Admin &gt; Employee Info permission to at least one restaurant where the employee works. You log into one of those restaurants, edit the employee's information, and click Save. The employee's information gets updated at all locations where the employee works.

To edit an employee's email and POS access code, you must also have a superset of the permissions assigned to the employee you are trying to edit. To determine whether you have a superset of permissions, the Toast platform compares the permissions the employee has in each location (based on jobs assigned to the employee as well as any permission overrides the employee has) against the permissions you have in each location. If, in any location, you do not have at least the same permissions as the employee you are trying to edit, you do not have a superset of permissions and cannot edit the email or passcode for the employee. For example:

If an employee has:

- POS Access and Delivery Access permissions in Boston, and


- POS Access permissions in Burlington



Then you must, at a minimum, have POS Accessand Delivery Access permissions in Boston and POS Access permissions in Burlington in order to edit the employee's email and POS access code.

## Editing an employee's permissions

To give a permission to an employee for a given location, you must:

- Have the Account Admin &gt; User Permissions permission at the given location.


- Have the permission yourself at the given location. For example, to give an employee the Manager &gt; Discounts permission at the Boston location, you must have the Manager &gt; Discounts permission at the Boston location yourself.



The same is true for removing a permission from an employee.

## Editing an employee's jobs

To assign a job to an employee at a given location, you must:

- Have the Restaurant Admin &gt; Employee Jobs & Wages permission at the given location.


- Have all of the job's permissions at the given location. For example, consider a Server job that includes all of the POS Access permissions. In order to assign the Server job to an employee at the Boston location, you must have the POS Access permissions to the Boston location yourself. Note that you do not have to be explicitly assigned the Server job, but you do need to have the Server job's permissions.



The same is true for removing a job from an employee.

## Editing your own permissions

You cannot give yourself a permission in the Toast platform. Another user who has proper access permissions, according to the rules set out in the [Editing an employee's permissions](adminGuide-adminEditingEmployeeInformationJobsAndPermissionsInEnterprises#adminEditingAnEmployeesPermissions) section, must give it to you.

## Understanding how job permissions conflicts are resolved

If an employee is assigned multiple jobs at the same location that have conflicting permissions (one job gives a certain permission while another job does not), the Toast platform defaults to giving the employee all of the permissions for all the employee's assigned jobs any time that employee is logged in. For example, consider a scenario where an employee has both Assistant Manager and Server jobs, and the Assistant Manager job gives the permission for voiding checks while the Server job does not. When the employee logs into the Toast platform, regardless of the job they use when clocking in, they will have permission to void checks.

Note that this caveat only applies when the employee has conflicting jobs *at the same location*. If the employee has the Assistant Manager job at the Boston location and the Server job at the Burlington location, no job conflict exists. The employee will be able to void checks at the Boston location but not at the Burlington location.

