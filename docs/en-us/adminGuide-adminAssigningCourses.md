---
title: "Assigning courses"
id: adminAssigningCourses
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminCreatingYourMenuUsingTheBasicMenuBuilderOmitChunkFromSearchIndex.md
parentSectionTitle: "Menu builder"
previousSectionFile: adminGuide-adminAssigningPrepStationsMenuBuilder.md
previousSectionTitle: "Assigning prep stations"
nextSectionFile: adminGuide-adminAssigningSalesCategories.md
nextSectionTitle: "Assigning sales categories"
externalReferences: [https://central.toasttab.com/s/article/Course-Firing-Options]
excerpt: "You use courses to manage the firing of tickets to the kitchen for fulfillment."
keywords: ["assigning", "courses"]
procedures: 0
codeExamples: 0
---

You use courses to manage the firing of tickets to the kitchen for fulfillment.

You can set courses at the menu, menu group, subgroup, or menu item level. By default, menu groups inherit their course from their parent menus. Menu items and subgroups inherit their course from their parent menu groups. For more information on inheritance, see [Understanding inheritance](docs/en-us/adminGuide-platformUnderstandingInheritance).

To set the course for a menu, go to the Kitchen prep section of the menu's details page and select the course.

To override the inherited course for a menu group or subgroup, go to the Kitchen prep section of the group's details page, select the link icon next to Course to unlink the configuration, and then select the course from the list.

![Example of a menu group that does not inherit its course.](https://doc.toasttab.com/doc/media/menu-builder-menu-group-does-not-inherit-course.png)

To configure a menu group or subgroup so that it inherits its course, select the link icon next to Course so that the course setting is grayed out.

![Example of a menu group that inherits its course.](https://doc.toasttab.com/doc/media/menu-builder-menu-group-inherits-course.png)

To override the inherited course for a menu item, go to the Kitchen section on its details page, set its Inherit course? setting to No, and then select its course from the dropdown list. When you configure settings directly on a menu item, those settings apply *any time the menu item is ordered, from any menu path*.

![Example of a menu item that does not inherit its course.](https://doc.toasttab.com/doc/media/menu-builder-item-does-not-inherit-course.png)

To configure a menu item so that it inherits its course, set the Inherit course? setting to Yes.

If you do not have any courses configured yet, use the Manage courses link to go to the Courses page where you can create them. For more information on creating courses, see [Creating courses](docs/en-us/adminGuide-adminAssigningCourses#platformGuideCreatingCoursesMenuBuilder). For more information on using courses, see this [Toast Central article](https://central.toasttab.com/s/article/Course-Firing-Options).

## Creating courses

While you can assign courses in the menu builder, you must use the classic Courses page to create the courses themselves.

**Procedure 8.31. To create courses**

1. Go to the Courses page:

If you are viewing a menu item in the menu builder, select Kitchen. If you are viewing a menu, menu group, or subgroup in the menu builder, select Kitchen prep. In the Related settingssection, select Manage courses.

Alternatively, you can do the following:

- [Log in to Toast Web](docs/en-us/adminGuide-adminAccessToastAdminBackend).


- Switch to the restaurant you want to create courses for.


- Select Kitchen &gt; Pacing &gt; Courses.




2. Select + Add to add a row to the Courses table.


3. Enter a name for the course.


4. Repeat steps 2 and 3 for any additional courses you want to create.


5. Select Save.



