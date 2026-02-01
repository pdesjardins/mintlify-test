---
title: "Assigning restaurant group-level permissions"
id: adminAssigningRestaurantGroupLevelPermissions
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminWorkingWithJobsAndEmployeesInEnterprisesOmitChunkFromSearchIndex.md
parentSectionTitle: "Jobs and employees in enterprises"
previousSectionFile: adminGuide-adminUnderstandingTheJobsAndPermissionsTabInEnterpriseEnvironments.md
previousSectionTitle: "Understanding the Jobs and Permissions tab in enterprise environments"
nextSectionFile: adminGuide-adminEditingEmployeeInformationJobsAndPermissionsInEnterprises.md
nextSectionTitle: "Editing employee information, jobs, and permissions in enterprises"
excerpt: "Restaurant group-level permissions are required for any employee that needs to:"
keywords: [assigning,restaurant,grouplevel,permissions]
procedures: 2
codeExamples: 0
---

### Assigning restaurant group-level permissions

Restaurant group-level permissions are required for any employee that needs to:

- View reports for groups of restaurants.


- Edit configuration entities (menus, menu items, prep stations, void reasons, and so on) in Toast Web that are owned by a restaurant group. For example, assuming the restaurant group hierarchy below, an employee would need group-level permissions to the Corporate restaurant group to edit an entity owned by the Corporate restaurant group. Similarly, an employee would need group-level permissions to the Northeast restaurant group, or one of of the Northeast group's ancestors (Franchise Owner 1 or Corporate), to edit a configuration entity owned by the Northeast restaurant group.

![Image](https://doc.toasttab.com/doc/media/mjm-restaurant-group-level-permissions.png)



The specific permissions you have to a restaurant group determine what you can do with that restaurant group. For example, if you have the Restaurant Admin > Sales Report permission for a restaurant group, you can view sales reports for the group as a whole as well as for any of the individual locations within the group. Similarly, an employee with the Restaurant Admin > Edit Full Menu permission to a restaurant group can edit all aspects of a menu item owned by that restaurant group, while an employee with the Restaurant Admin > Local Menu Edit permission is restricted to tasks like providing a location-specific price for a menu item, or adding a menu item to or removing it from a menu group. (See [Understanding menu editing permissions for enterprises](adminUnderstandingMenuEditingPermissionsForEnterprises.html) for more information on menu editing permissions.)

Employees inherit restaurant group-level permissions at all of the locations in the group they have access to. For example, if you gave an employee the Restaurant Admin > Sales Reportspermission to the Franchise Owner 1 group above, the employee would have the Restaurant Admin > Sales Reports permission to the Boston and NYC locations, too (assuming the employee has restaurant access to the Boston and NYC locations).

You can give an employee permissions to a restaurant group without giving the employee restaurant access to the group's child locations. For example, you may have a corporate employee that needs to review sales reports for the locations in a restaurant group but does not need to log into the Toast POS devices at those locations. In this case, you can give the employee the Restaurant Admin > Sales Reportspermission to the restaurant group and ignore the Restaurant Access tab.

The procedures below describe how to give and remove restaurant group-level permissions. To perform these procedures, you must have the proper permissions yourself, as described in [Editing an employee's permissions](adminEditingEmployeeInformationJobsAndPermissionsInEnterprises.html#adminEditingAnEmployeesPermissions).

**Procedure 5.20. To give an employee restaurant group-level permissions**

1. [Log in to Toast Web](adminAccessToastAdminBackend.html).


2. If necessary, switch to a location where the employee has access.


3. Choose Employees > Employee management > Employees to open the Employeespage.


4. Click the pencil for the employee you want to edit.


5. Click the Jobs and Permissions tab.


6. Click the Add Group/Restaurant Permissionsbutton. You see the Add Group Permissionsmodal.


7. Select the restaurant group you want to add permissions for and click Add. An entry is added to the Access Permissions area for the restaurant group.


8. Click the entry to see the permissions the employee has to the restaurant group. By default, the employee is given the permissions associated with their assigned jobs. You can make adjustments if necessary.


9. Click Save.



**Procedure 5.21. To remove an employee's restaurant group-level permissions**

1. [Log in to Toast Web](adminAccessToastAdminBackend.html).


2. If necessary, switch to a location where the employee has access.


3. Choose Employees > Employee management > Employees to open the Employeespage.


4. Click the pencil for the employee you want to edit.


5. Click the Jobs and Permissions tab.


6. Click the trash can for the restaurant group entry whose permissions you want to remove.


7. Click Save.



