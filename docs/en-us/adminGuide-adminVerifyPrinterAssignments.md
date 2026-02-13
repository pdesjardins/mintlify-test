---
title: "Verify printer assignments"
id: adminVerifyPrinterAssignments
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminTroubleshootPrepStationsOmitChunkFromSearchIndex.md
parentSectionTitle: "Troubleshooting the preparation workflow"
previousSectionFile: adminGuide-adminVerifyDeviceSetup.md
previousSectionTitle: "Verify device setup"
nextSectionFile: adminGuide-adminVerifyAutomatedItemFiring.md
nextSectionTitle: "Verify automated item firing and prep times"
excerpt: "If a kitchen printer is printing two sets of tickets for every order, two prep stations or both a prep station and expediter seat might be configured to use the same printer."
keywords: ["verify", "printer", "assignments"]
procedures: 1
codeExamples: 0
---

If a kitchen printer is printing two sets of tickets for every
    order, two prep stations or both a prep station and expediter seat might
    be configured to use the same printer.

To verify that your kitchen printers are assigned correctly, follow
    these steps.

1. [Access Toast Web
        ](adminGuide-adminAccessToastAdminBackend).


2. Choose Kitchen > Kitchen stations > Prep
        stations. An interactive grid with rows for each prep
        station appears.


3. Review the Ticket Printer assignment for
        each prep station. If you assign the same printer to multiple prep
        stations, that printer will produce tickets for all of those prep
        stations.


4. Save any changes.


5. Choose Kitchen > Printers, tickets, & KDS
        devices > Kitchen. 


6. In the Expediter section, review the
        Expediter Printer(s) setting. If you assign the
        same printer to both the expediter and a prep station, that printer
        will produce tickets for both the prep station and the
        expediter.


7. Update printer assignments for your expediter and prep stations
        as needed.


8. Save and publish your changes.



**Next steps**

- [Routing with prep stations](adminGuide-adminRoutingToPrepStations)


- [Using a KDS expediter screen](adminGuide-adminUsingExpo)



