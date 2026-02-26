---
title: "Downloading data export files"
id: downloading-data-export-files
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformDataExportFilesOmitChunkFromSearchIndex.md
parentSectionTitle: "Data export files"
previousSectionFile: adminGuide-configuringExports.md
previousSectionTitle: "Configuring exports"
nextSectionFile: adminGuide-adminDataExportSecurity.md
nextSectionTitle: "Security"
externalReferences: [https://central.toasttab.com/s/article/Automated-Nightly-Data-Export-1492723819691]
excerpt: "The Toast platform stores data export files for seven days, and then they are deleted. When data exports are enabled for your restaurant, the following items are needed to retrieve your files: SFTP..."
procedures: 0
codeExamples: 0
---

The Toast platform stores data export files for seven days, and then they are deleted. When data exports are enabled for your restaurant, the following items are needed to retrieve your files: 

- SFTP User name: This is provided by Toast support.


- SSH key: For more information about generating an SSH key, and where to enter this in Toast Web, see [SSH keys](adminGuide-adminSshKeys).


- Server URL: To locate the appropriate Server URL, navigate to Reports &gt; Settings &gt; SSH Keys from the Toast Web. Locate your SFTP username and find the Server URL.



Export IDs can also be obtained from Toast Web. Navigate to Reports &gt; Settings &gt; Data Exports and click the link in the banner at the top of the screen, view restaurant # mapping to export a file that includes an Export ID column which includes the ID for each restaurant.

![Image](https://doc.toasttab.com/doc/media/export_ids_data_export.png)



Prior to downloading data export files, ensure that you have [added an SSH key](adminGuide-adminSshKeys) to Toast Web. The following examples describe how to connect to your SFTP directory for use with the macOS™ terminal and Windows™ command prompt. For information about how to export files using a third party FTP solution see this [Toast Central article.](https://central.toasttab.com/s/article/Automated-Nightly-Data-Export-1492723819691)

## Accessing your SFTP directory using macOS terminal

1. **Connect to your SFTP directory**

To access your restaurant's SFTP directory using terminal use the following command:


```
sftp \ 
      -i ~/`{SSH_key_filepath}` \
      -r `{sftp_username}`@s-9b0f88558b264dfda.server.transfer.us-east-1.amazonaws.com:`{export_id}`/`{YYYYMMDD}`/*
```

Replace the *`{sftp_username}`* and *`{export_id}`* placeholders with the details you received from Toast support. Change *`{YYYYMMDD}`* to the business date of the desired export within the last seven days and the *`{SSH_key_filepath}`* to the location of your SSH key on your machine.



> **Note**
> 
> The *`{filepath}`* used will be the export directory for your restaurant files.



2. **Exporting files using terminal**

Once you are connected to the SFTP directory use the **ls** command and press Return to display all files.

Export all files using the **get *** command or use **get *`{fileName}`*** to export a specific file.



## Accessing your SFTP directory using Windows command prompt

1. **Connect to your SFTP directory**

To access your restaurant's SFTP directory using command prompt use the following command:


```
sftp -i `{SSH_key_filepath}` -r `{sftp_username}`@s-9b0f88558b264dfda.server.transfer.us-east-1.amazonaws.com
```

Replace *`{SSH_key_filepath}`* with the location of your SSH key on your machine. Replace *`{export_username}`* with the export user name you received from Toast support.


2. **Exporting files using command prompt**

Once you are connected to the SFTP directory, use the **ls** command and press Enter to display all files.

To export a file for a specific location and date, use the following command:


```
get /`{export_id}`/`{YYYYMMDD}` `{download_location}`
```

Replace *`{export_id}`* with the export ID you received from Toast support. Change *`{YYYYMMDD}`* to the business date of the desired export within the last seven days. Replace *`{download_location}`* with the location on the local file system where you want the downloaded files to be stored.

To export all files, use the following command:


```
get * `{download_location}`
```



