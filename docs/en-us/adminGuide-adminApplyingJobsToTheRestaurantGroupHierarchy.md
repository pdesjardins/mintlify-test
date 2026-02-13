---
title: "Applying jobs to the restaurant group hierarchy"
id: adminApplyingJobsToTheRestaurantGroupHierarchy
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminWorkingWithJobsAndEmployeesInEnterprisesOmitChunkFromSearchIndex.md
parentSectionTitle: "Jobs and employees in enterprises"
previousSectionFile: adminGuide-adminEnterpriseJobsAndEmployeesOverview.md
previousSectionTitle: "Enterprise jobs and employees overview"
nextSectionFile: adminGuide-adminAssigningRestaurantAccess.md
nextSectionTitle: "Assigning restaurant access"
excerpt: "Toast Web allows you to create jobs and then assign those jobs to your employees. When you create a job in an enterprise environment, you specify:"
keywords: ["applying", "jobs", "restaurant", "group", "hierarchy"]
procedures: 0
codeExamples: 0
---

Toast Web allows you to create jobs and then assign those jobs to
    your employees. When you create a job in an enterprise environment, you
    specify:

- A set of permissions associated with the job. These permissions
        are granted to employees that are assigned the job.


- The portion of the restaurant group hierarchy that the job
        applies to. This configuration determines which employees in your
        enterprise may be assigned the job and is described in more detail in
        [Creating an enterprise job](adminGuide-adminApplyingJobsToTheRestaurantGroupHierarchy#adminCreatingAnEnterpriseJob).



## Creating an enterprise job

Creating a job for an enterprise is essentially the same as
      creating a job for a single location. You give the job a title, provide
      some information about pay and job functions such as cashier or driver,
      and set the permissions for the job. There are, however, two additional
      caveats with enterprise jobs:

- You must use the Create New Job option on
          the Jobs page. Jobs created using the
          Quick Add Jobs option apply to the session
          restaurant only so that method for creating jobs cannot be used for
          an enterprise-level job.


- You use the Applies To menu to define
          which portion of your restaurant group hierarchy the job applies to.
          The Applies To setting for a job cannot be
          changed once the job is created, so be mindful when setting
          it.

![Image](https://doc.toasttab.com/doc/media/mjm-applies-to-menu.gif)



When you configure the Applies To setting for
      a job, you pick a restaurant group or an individual location. If you
      specify a restaurant group, the job can be assigned to employees at any
      location that is a descendant of the group in the restaurant group
      hierarchy. For example, in the illustration below, a job that applies to
      the Corporate restaurant group (that is, the top-level group) can be
      assigned to employees at any of the enterprise's locations, while a job
      that applies to the Franchise Owner 1 restaurant group may only be
      assigned to employees at the Boston, NYC, Burlington, Atlanta, or
      Charlotte locations and a job that applies to the Burlington location
      can only be assigned to Burlington employees.

![Image](https://doc.toasttab.com/doc/media/mjm-jobs-and-the-hierarchy.png)

When you select a restaurant group in the Applies
      To menu, all of that group's sub-groups and child locations
      are automatically selected. For example, selecting the Franchise Owner 1
      restaurant group in the following hierarchy also selects the Northeast
      and Southeast restaurant sub-groups and any locations within those
      sub-groups. You can assign a job with this Applies
      To configuration to employees at the Boston, Burlington, NYC,
      Atlanta and Charlotte locations.

![Image](https://doc.toasttab.com/doc/media/mjm-applies-to-menu-franchise-owner-1.PNG)

When you select individual locations, the job is available at
      those locations only. For example, the job in the illustration below is
      available at the NYC and Boston locations only.

![Image](https://doc.toasttab.com/doc/media/mjm-applies-to-menu-nyc-boston.PNG)

To de-select a restaurant group or location, click its name again
      to remove the check mark. When you de-select a restaurant group, its
      children are automatically de-selected, too.

Note that when you create an enterprise job on the
      Create Job page, you can configure that job to
      apply to any portion of your restaurant group hierarchy, regardless of
      which location you are currently logged into (also known as the [session
      restaurant](adminGuide-sessionRestaurant)). However, you should be aware that, if you configure
      the job to apply to a portion of the hierarchy that does not include the
      session restaurant, then you will not see that job on the
      Jobs page you get redirected to immediately after
      creating the job. For example, if you are current logged into the Boston
      location and you create a job that applies to the Southeast portion of
      the restaurant group hierarchy shown below, the job will be created but
      you will not see it in the list of jobs on the Jobs
      page while you are logged into the Boston location. To see this job, you
      must log into the Atlanta or Charlotte location (that is, one of the
      locations that the job applies to).

![Image](https://doc.toasttab.com/doc/media/mjm-applies-to-menu-deselecting.PNG)

## Understanding the Applies To setting from the employee
      perspective

When an employee is assigned a job, the employee inherits the
      permissions associated with that job. In an enterprise configuration,
      because of the Applies To setting, the inheritance
      rules are slightly more complex. Specifically, the employee inherits a
      job's permissions only at locations that the job applies to and to which
      the employee has access. For example, consider a franchise manager,
      Megan Manager, who has access to all of the locations in the Franchise
      Owner 1 restaurant group shown in the illustration below (Boston,
      Burlington, NYC, Atlanta, and Charlotte).

![Image](https://doc.toasttab.com/doc/media/mjm-megan-mgr-restaurant-access.PNG)

Megan Manager is assigned a job that applies to the Boston and
      Burlington locations only and includes the Account Admin >
      User Permissions permission. In this scenario, Megan Manager
      will have the User Permissions permission for the
      Boston and Burlington locations but not for the NYC, Atlanta, and
      Charlotte locations.

## Assigning an enterprise job

You assign one or more jobs to an employee on the employee details
      page:

![Image](https://doc.toasttab.com/doc/media/mjm-jobs-and-permissions-tab.PNG)

In an enterprise environment, the jobs you can assign on the
      employee details page are restricted by the session restaurant you are
      currently logged into. If a job does not apply to the session
      restaurant, you cannot assign it to an employee of the session
      restaurant. For example, in the following illustration, when you are
      logged into the Boston, Burlington, or NYC locations, you can assign an
      employee the Server-Corp job or the Manager-NE job. When you are logged
      into the Atlanta or Charlotte locations, you can assign an employee the
      Server-Corp job or the Manager-SE job.

![Image](https://doc.toasttab.com/doc/media/mjm-jobs-limited-by-session-restaurant.png)

It is a common practice, when you create a job for an enterprise,
      to set it to apply to the top-level corporate group, so that it can be
      assigned to anyone in the enterprise. This is the approach taken in the
      enterprise jobs example described in [Example configurations for enterprises](adminGuide-adminExampleConfigurationForEnterprises).

