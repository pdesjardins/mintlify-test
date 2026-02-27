---
title: "Example configurations for enterprises"
id: adminExampleConfigurationForEnterprises
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminWorkingWithJobsAndEmployeesInEnterprisesOmitChunkFromSearchIndex.md
parentSectionTitle: "Jobs and employees in enterprises"
previousSectionFile: adminGuide-adminUnderstandingMenuEditingPermissionsForEnterprises.md
previousSectionTitle: "Understanding menu editing permissions for enterprises"
nextSectionFile: adminGuide-adminUsingReportsEnterprisesOmitChunkFromSearchIndex.md
nextSectionTitle: "Reports for enterprises"
excerpt: "While every enterprise has its own requirements for..."
keywords: ["example", "configurations", "enterprises"]
procedures: 0
codeExamples: 0
---

While every enterprise has its own requirements for employee, job, and permission configuration, this section provides a detailed example of a common approach. It includes the following types of employees:

- A *super user* that has full permissions at all locations in the restaurant group hierarchy. The super user can manage employees for the entire enterprise and edit their permissions. This user can also edit any entity in Toast Web, including menu entities [owned](adminGuide-ownersAndPermissions) by the corporate restaurant group.


- A *franchise manager* can manage employees for their franchise and edit their permissions. They can also edit menu entities that are owned by the franchise, or a location in the franchise, and view reports for all the locations in the franchise.


- A *location manager* can manage employees for their location and edit their permissions. They can also edit menu entities that are owned by their location and view reports for their location.


- A *server* that represents the kind of non-managerial employee you might create and specify permissions for.



To support these types of employees, you need the following jobs:

- A *super user* job that has every permission that can be assigned to an employee. Toast support creates this job and assigns it to someone in your enterprise. The super user can then create the other jobs described below.


- A *manager* job that has every permission that can be assigned to an employee except the following:

- Restaurant Admin &gt; Quick Edit Menu. This type of menu editing is not yet supported in enterprise environments and should not be used.


- Account Admin &gt; Financial Accounts. Restricting this permission prevents the manager from interacting with financial data that should be restricted to corporate employees.




- A *server* job that has POS Access permissions only.



The *manager* job is assigned to both franchise and location managers, however, you specify different locations where these managers' permissions apply. For example, a franchise manager's permissions apply only to locations in their franchise while a location manager's permissions apply only to the single location where they work.

## Understanding equivalent employees in the enterprise example

When adding employees, the manager who is logged in to Toast Web can add employees that have equivalent permissions and restaurant access to their own, or a subset of their own permissions and restaurant access. This means that the employees being added can have:

- The same jobs/permissions as the logged-in manager or a subset of those jobs/permissions.


- Access to the same locations as the logged-in manager or a subset of those locations.



In the enterprise example presented in this section, super users can add super users, franchise managers, location managers, and other non-managerial employees across the entire corporation. Franchise managers can add franchise managers, location managers and non-managerial employees to the their franchise. Location managers can add location managers and non-managerial employees to their location.

![Image](https://doc.toasttab.com/doc/media/mjm-adding-employees-in-an-enterprise.png)

## Adding jobs and employees to the enterprise example

Use the procedures below to add the manager and server jobs described in this enterprise example and also add employees for each job type. Prior to following these procedures, a Toast employee must create the super user job for you and assign it to at least one person in your enterprise.

### Adding jobs to the enterprise example

The instructions below describe how to create the manager and server jobs for the enterprise example. You must be a super user to create these jobs.

**Procedure 5.22. To create the manager job**

1. [Log in to Toast Web](adminGuide-adminAccessToastAdminBackend) using your super user credentials.


2. Choose Employees &gt; Employee management &gt; Jobs to open the Jobs page.


3. Click the Add Job button and select Create New Job.


4. From the Applies To menu, choose the top-level restaurant group (so that all locations have a checkmark next to them).



> **Important**
> 
> Be careful to choose the top-level restaurant group. You cannot change the Applies To setting after a job has been created.



5. For the Job Title, enter **`Manager`**.


6. For Pay Basis, choose salary.


7. Enable all permissions except:

- Restaurant Admin &gt; Quick Edit Menu. This type of menu editing is not yet supported in enterprise environments and should not be used.


- Account Admin &gt; Financial Accounts. Restricting this permission prevents the manager from interacting with financial data that should be restricted to corporate employees.



You can click a permission header row to quickly select all its child permissions. For example, click the POS Access header row to select all its children.


8. Save and publish your changes.



**Procedure 5.23. To create the server job**

1. [Log in to Toast Web](adminGuide-adminAccessToastAdminBackend) using your super user credentials.


2. Choose Employees &gt; Employee management &gt; Jobs to open the Jobs page.


3. Click the Add Job button and select Create New Job.


4. From the Applies To menu, choose the top-level restaurant group (so that all locations have a checkmark next to them).



> **Important**
> 
> Be careful to choose the top-level restaurant group. You cannot change the Applies To setting after a job has been created.



5. For the Job Title, enter **`Server`**.


6. For Pay Basis, choose hourly.


7. Enter a value for Default Pay.


8. For the Tipped property, choose Yes. This employee must enter cash tips at closing.


9. For the Cashier property, choose Yes.


10. In the Default User Permissionssection, click the POS Access header row to select it and all its children.


11. Save and publish your changes.



### Adding employees to the enterprise example

In this enterprise example, any type of manager can add a non-managerial employee, although franchise and location managers are restricted to adding employees to their own franchises or locations. To add a manager-level employee, you must be either a super user or an equivalent manager yourself. See [Understanding equivalent employees in the enterprise example](adminGuide-adminExampleConfigurationForEnterprises#adminUnderstandingEquivalentEmployeesInTheEnterpriseExample)for details.

**Procedure 5.24. To add a franchise or location manager**

1. [Log in to Toast Web](adminGuide-adminAccessToastAdminBackend).


2. Switch to a location where the new manager should have access. If you are creating a franchise manager, go to one of the locations in the franchise. If you are creating a location manager, go to the location.



> **Note**
> 
> In Toast Web, it is possible to create an employee that does not have access to the session restaurant you are currently logged into. If you inadvertently do this, the employee will be created but you will not be able to see the employee on the Employees page until you switch to a location where the employee has access. To avoid this problem, log in to a location that the employee should have access to *before* creating the employee.



3. Choose Employees &gt; Employee management &gt; Employees to open the Employeespage.


4. Click the Add New Employeebutton.


5. Toggle the Invite to create accountsetting to Yes.


6. Enter the manager's details and click Add. The manager is added to the employees table.


7. Click the edit (pencil) icon for the manager you just added.


8. Click the Restaurant Access tab.


9. Select the portions of the restaurant group hierarchy that the manager should have access to and click Save.


10. Click the Jobs and Permissionstab.


11. Select the **`Manager`** job.


12. At this point, the Access Permissionsarea contains entries for the locations you chose in step 9 and the manager inherits the permissions associated with their assigned job at each location. This means the manager can access the POS devices at these locations, edit any entities in Toast Web that are owned by these locations, and view reports for these locations. For a location manager, this configuration is sufficient. For a franchise manager, you must also add restaurant group-level permissions so that the manager can edit entities [owned](adminGuide-ownersAndPermissions) by the franchise's restaurant group and view reports for the franchise group. To enable this ability for the manager, do the following:

- Click the Add Group/Restaurant Permissions button. You see the Add Group Permissions modal.


- Click the franchise's restaurant group, then click Add.




13. Click Save.



**Procedure 5.25. To add a server employee**

1. [Log in to Toast Web](adminGuide-adminAccessToastAdminBackend).


2. Switch to a location where the new employee should have access.



> **Note**
> 
> In Toast Web, it is possible to create an employee that does not have access to the session restaurant you are currently logged into. If you inadvertently do this, the employee will be created but you will not be able to see the employee on the Employees page until you switch to a location where the employee has access. To avoid this problem, log in to a location that the employee should have access to *before* creating the employee.



3. Choose Employees &gt; Employee management &gt; Employees to open the Employeespage.


4. Click the Add New Employeebutton.


5. Leave the Invite to create accountsetting on No.


6. Enter the employee's details and click Add. The employee is added to the employees table.


7. Click the edit (pencil) icon for the employee you just added.


8. Click the Restaurant Access tab.


9. Select the portions of the restaurant group hierarchy that the employee should have access to and click Save.


10. Click the Jobs and Permissionstab.


11. Select the **`Server`** job to assign it to this employee.


12. Click Save.



