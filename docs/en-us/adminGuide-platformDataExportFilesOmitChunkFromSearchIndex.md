---
title: "Data export files"
id: platformDataExportFilesOmitChunkFromSearchIndex
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformIntegrationsOmitChunkFromSearchIndex.md
parentSectionTitle: "Chapter 12. Integrations"
previousSectionFile: adminGuide-platformIntegrationsOmitChunkFromSearchIndex.md
previousSectionTitle: "Chapter 12. Integrations"
nextSectionFile: adminGuide-adminSshKeys.md
nextSectionTitle: "SSH keys"
procedures: 0
codeExamples: 0
---

### Data export files overview

Toast data exports give you access to your Toast POS data. Data exports are configured to run automatically or can be downloaded manually, and can include the following data types:

**Sales/Finance**

- Order Details


- Payment Details


- Item Selection Details


- Modifier Selection Details


- Kitchen Details


- Cash Management


- Product Mix (All Items)



**Labor/Employee**

- Time Entries



**Accounting**

- Accounting



**Configuration**

- Menu



This information can also be downloaded manually from Toast Web or retrieved using a command line interface (CLI) or FTP service.

The Toast platform exports data after the closeout hour configured for a location or at 04:00 AM by default. Export files are generated within one hour, and include data for the previous business day. 



> **Note**
> 
> The Toast platform does not generate data export files for sites that are pending activation.


