---
title: "Items database export"
id: platformItemsDatabaseExport
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platfomrItemsDatabaseOmitChunkFromSearchIndex.md
parentSectionTitle: "Items database"
previousSectionFile: adminGuide-platformItemsDatabaseOverview.md
previousSectionTitle: "Items database overview"
nextSectionFile: adminGuide-platformMenusBulkMenuImportOmitChunkFromSearchIndex.md
nextSectionTitle: "Bulk menu imports"
excerpt: "To export data from the Items database page, select the tab for the type of entity you want to export, and then select the export icon."
keywords: ["items", "database", "export"]
procedures: 0
codeExamples: 1
---

To export data from the Items database page, select the tab for the type of entity you want to export, and then select the export icon.

All data is exported for all entities of the type you selected, regardless of the searching and filtering you have done on the Items database page. For example, if you are viewing the Items tab, all of the items in your menu are exported along with all of their data, even if you used the search field or the Show/hide columns option to limit what you see on the Items database page.

Depending on your browser and its settings, the browser may save the file to its default download location or you may be asked to specify the location for the CSV file. 

![The location of the export icon on the Items database page](https://doc.toasttab.com/doc/media/items-database-export-icon.png)

If your menu entities have names that begin with any of the following special characters, see [Special characters in items database export](adminGuide-platformItemsDatabaseExport#platformSpecialCharactersInItemsDatabaseExport) for additional important information:

```
+ (plus)
= (equal)
- (minus)
@ (at)
```

## Special characters in items database export

Restaurant employees who export menu data from the Items database page to a CSV file often import that file into a spreadsheet application for further editing.

Spreadsheet applications treat names that begin with certain special characters as formulas, not names, causing them to appear incorrectly in the spreadsheet application. Those special characters are:

```
+ (plus)
= (equal)
- (minus)
@ (at)
```

To avoid this problem, the Toast platform modifies the menu entity names during the export so that they don't appear as formulas to spreadsheet applications (this is known as *escaping*the special characters).

When it modifies a name with a special character, the Toast platform inserts a single quote (') before the special character itself and double-quotes (") at the beginning and end of the name. For example, the Toast platform modifies the name of a modifier called `+
      Chicken` like this:

```
"'+ Chicken"
```

If you open the CSV file in a text editor, you see the additional single and double quotes.

When importing the CSV file, spreadsheet applications handle the additional single and double quotes according to their own rules:

- Google Sheets™ ignores the single and double quotes, so the name of our example modifier appears as:

```
+ Chicken
```

Because the single and double quotes have both been ignored, no additional manual editing is necessary when you open the CSV file in Google Sheets.


- Microsoft® Excel® and Apple® Numbers® ignores the double quotes but it does not ignore the single quote, so our example modifier name appears as:

```
'+ Chicken
```

You need to manually remove the single quote from the name.


- Other spreadsheet applications may retain both the single and double quotes during the CSV import. For these applications, you must manually remove both the single and double quotes.



