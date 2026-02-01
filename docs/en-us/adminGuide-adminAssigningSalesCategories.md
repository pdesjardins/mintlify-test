---
title: "Assigning sales categories"
id: adminAssigningSalesCategories
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminCreatingYourMenuUsingTheBasicMenuBuilderOmitChunkFromSearchIndex.md
parentSectionTitle: "Menu builder"
previousSectionFile: adminGuide-adminAssigningCourses.md
previousSectionTitle: "Assigning courses"
nextSectionFile: adminGuide-adminAssigningTaxRatesInMenuBuilder.md
nextSectionTitle: "Assigning tax rates and tax behavior"
externalReferences: [https://central.toasttab.com/s/article/Sales-Reports-Overview, https://central.toasttab.com/s/article/Menu-Report-Overview-1492794696577]
excerpt: "The Sales Summary and other Toast reports use sales categories to create a breakdown of your sales, organized by sales category, for example, Food, Drinks, Retail, and so on."
keywords: ["assigning", "sales", "categories"]
procedures: 0
codeExamples: 0
---

### Assigning sales categories

The Sales Summary and other Toast reports use sales categories to create a breakdown of your sales, organized by sales category, for example, Food, Drinks, Retail, and so on.

Some points to keep in mind when using sales categories:

- If you change the sales category for a menu entity, those changes are reflected in future sales reports but existing reports remain unchanged.


- While highly recommended for a better reporting experience, sales categories are optional. If you select None selected from the Sales categorymenu, no sales category is applied to the menu entity.



For information about the reports that use sales categories, see these Toast Central articles:

- [Sales Reports Overview](https://central.toasttab.com/s/article/Sales-Reports-Overview)


- [Menu Reports Overview](https://central.toasttab.com/s/article/Menu-Report-Overview-1492794696577)



You can set sales categories at the menu, menu group, subgroup, or menu item level. By default, menu groups inherit their sales category from their parent menus. Menu items and subgroups inherit their sales category from their parent menu groups. For more information on inheritance, see [Understanding inheritance](platformUnderstandingInheritance.html).

To set the sales category for a menu, go to the Reporting section of the menu's details page and select the category from the Sales category dropdown list.

To override the inherited sales category for a menu group or subgroup, go to the Reporting section of the group's details page, select the link icon next to Sales category to unlink the configuration, and then select the sales category from the list.

![Example of a menu group that does not inherit its sales category.](https://doc.toasttab.com/doc/media/menu-builder-menu-group-does-not-inherit-sales-category.png)

To configure a menu group or subgroup so that it inherits its sales category, select the link icon next to Sales categoryso that the course setting is grayed out.

![Example of a menu group that inherits its sales category.](https://doc.toasttab.com/doc/media/menu-builder-menu-group-inherits-sales-category.png)

To override the inherited sales category for a menu item, go to the Reporting section on its details page, set its Inherit sales category? setting to No, and then select its sales category from the dropdown list. When you configure settings directly on a menu item, those settings apply *any time the menu item is ordered, from any menu path*.

![Example of a menu item that does not inherit its sales category.](https://doc.toasttab.com/doc/media/menu-builder-item-does-not-inherit-sales-category.png)

To configure a menu item so that it inherits its sales category, set the Inherit sales category? setting to Yes.

If you do not have any sales categories configured yet, use the Manage sales categories link to go to the Sales categories page where you can create them. For more information on creating sales categories, see [Creating sales categories](adminAssigningSalesCategories.html#platformCreatingSalesCategoriesMenuBuilder).

#### Creating sales categories

While you can assign sales categories in the menu builder, you must use the classic Sales Categories page to create the sales categories themselves.

**Procedure 8.32. To create sales categories**

1. Do one of the following to navigate to the Sales categories page:

On the details page for a menu, menu group, or menu item, select Reporting. In the Related settings section, select Manage sales categories.

Alternatively, you can:

- [Log in to Toast Web](adminAccessToastAdminBackend.html).


- Switch to the restaurant you want to create courses for.


- Select Menus \> Settings \> Sales categories.




2. Select + Add to add a row to the Sales Categories table.


3. Enter a name and a description for the sales category.


4. Repeat steps 2 and 3 for any additional sales categories you want to create.


5. Select Save.



