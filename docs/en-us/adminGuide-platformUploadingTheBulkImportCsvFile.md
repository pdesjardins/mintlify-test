---
title: "Uploading the bulk import CSV file"
id: platformUploadingTheBulkImportCsvFile
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformMenusBulkMenuImportOmitChunkFromSearchIndex.md
parentSectionTitle: "Bulk menu imports"
previousSectionFile: adminGuide-platformButtonColors.md
previousSectionTitle: "Button colors"
nextSectionFile: adminGuide-platformFixingImportFailures.md
nextSectionTitle: "Fixing import failures"
excerpt: "Once you have filled out your copy of a bulk import spreadsheet and downloaded it as a CSV file, you can upload..."
keywords: ["uploading", "bulk", "import", "file"]
procedures: 1
codeExamples: 0
---

Once you have filled out your copy of a bulk import spreadsheet and downloaded it as a CSV file, you can upload the CSV file into the Toast platform. This section provides instructions for uploading the CSV file. *It is important to note that changes made using the bulk menu import tool are not reversible*.

It is possible that some rows in a bulk menu import file have validation issues and cannot be imported. This does not cause the entire import process to fail. Instead, the Toast platform imports rows that have no validation issues and notifies you of rows that need to be fixed. For more information, see [Fixing import failures](docs/en-us/adminGuide-platformFixingImportFailures).

**Procedure 8.145. To upload a bulk menu import .csv file**

1. Log in to Toast Web.


2. Choose Menus &gt; Bulk management &gt; Bulk import tool.


3. Select Start new import. You see the Upload template page.


4. Select the Upload file button, locate and select the CSV file you've prepared, and select Open. Alternatively, you can drag and drop the CSV file to the box with the dashed outline on the Upload template page.


5. Select the Yes! I agree to upload with file with [X] changes to my menu that cannot be undone box.


6. Select Submit.

If all rows in the spreadsheet were imported successfully, you are redirected to the Import history tab and you see a "Your import was successful message". A new entry is also added to the Complete imports table for the import you just completed.

If you see the Errors found in import filepage instead of the Import history tab, it means that the import file has data validation failures. In this case, the entire import file has failed and no rows were imported.

If you see the Incomplete import page instead, it means that some of the rows in the import file were imported successfully but other rows had import operation failures.

For more information about resolving data validation and import operation failures, see [Fixing import failures](docs/en-us/adminGuide-platformFixingImportFailures).



