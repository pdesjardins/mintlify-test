---
title: "Adding a kitchen printer"
id: adminAddKitchenPrinter
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformKitchenConfigurationOmitChunkFromSearchIndex.md
parentSectionTitle: "Kitchen configuration"
previousSectionFile: adminGuide-platformKDSCreatingAssemblyLines.md
previousSectionTitle: "Creating an assembly line"
nextSectionFile: adminGuide-adminAssignPrepStationKDS.md
nextSectionTitle: "Assigning a KDS device to a prep station"
excerpt: "Every restaurant that uses the Toast platform has at least one kitchen printer."
keywords: ["adding", "kitchen", "printer"]
procedures: 0
codeExamples: 0
---

Every restaurant that uses the Toast platform has at least one
    kitchen printer.

- In a restaurant that primarily uses kitchen printers, there are
        usually at least two printers. Each printer acts as the backup for the
        other.


- In a restaurant that primarily uses KDS devices, you add a
        kitchen printer to act as the backup when the system is in
        *offline mode*. For more information about KDS
        devices in offline mode, see [KDS devices](adminGuide-platformOfflineKDSDevices).


- You can route items that do not require tickets for fulfillment
        to a ["no print" prep station](adminGuide-adminPreventingTicketsFromPrinting#adminNoPrintPrepStation)
        that does not have an associated printer.


- In a restaurant that adds labels to items for off-premise
        dining, you can add an Epson L90 or TLP400 printer to print item
        labels.



Before you add a printer to the system, you must know the printer's
    IP address. Each printer shipped by the Toast configuration center is
    labeled with its configured IP address. IP addresses are formatted as a
    series of four numbers separated by periods, such as 192.168.1.171.

There are two methods to adding a new kitchen printer to your
    kitchen setup: through Toast Web or your Toast POS device. Toast support
    recommends adding kitchen printers through your Toast POS device to follow
    the setup workflow.



> **Important**
> 
> To add a kitchen printer, you must have the 6. Web Setup
      > 6.10 Printer and Cash Drawer Setup access
      permission.


Repeat these steps to add other kitchen printers, or to update the
    information for a printer by adding its backup printer. After you set up
    your printers, you can assign them to your prep stations.

## To add a printer on the Toast POS app

1. Navigate to the Toast POS app home screen.


2. In the Setup section, select
          Printer Setup.



> **Note**
> 
> If this is the first printer added to your restaurant, move
            to [step 5](adminGuide-adminAddKitchenPrinter#AddPrinterOnPOSAppStep).



3. Select + Add or replace printer.


4. Select Install a new printer and then
          Continue.


5. Select Wired or
          Wireless depending on your printer
          model.


6. Follow the workflow on the Toast POS app to find your
          printer.


7. Once found, select the printer model and then
          Continue.


8. Select the primary function for the printer. For kitchen
          printers, this is typically Kitchen Tickets,
          Both (Guest Receipts and Kitchen Tickets), or
          Item Labels.



> **Note**
> 
> This step is skipped if you are using a TLP400 printer.
            TLP400 uses Item Labels automatically.



9. If you selected Item Labels as the
          primary function for the printer, or use a TLP400 printer:



> **Note**
> 
> The following steps are available only to Epson L90 and
            TLP400 printers.


1. Select the label size you want to use. The options
              are:

- Small - Vertical : A 1.5 by 3
                  inch ticket. This label is printed sideways to optimize
                  paper usage.


- Small - Horizontal : A 3 by 1.5
                  inch ticket.


- Medium - Horizontal : A 3 by 2
                  inch ticket.


- Large - Square : A 3 by 3 inch
                  ticket.



Small and medium-sized tickets do not include custom logos
              or footers and summarize the number of modifiers not visible on
              the ticket (for example, "+2 modifiers").

For the Epson L90 printer, small vertical, small
              horizontal, and medium horizontal label sizes **must** use existing 76-80mm label printer
              paper.

For the TLP400 printer, small vertical and small
              horizontal label sizes **must** use
              3 inch by 1.5 inch label printer paper, and medium horizontal
              label sizes **must** use 3 inch by
              2 inch label printer paper.


2. Select either the guest name or ticket number to be
              displayed prominently at the top of the label and then
              Continue.



> **Note**
> 
> This configuration is only available for small and
                medium item label sizes.





10. Select the prep stations that will use the printer and then
          Continue.


11. Print a test ticket and continue the printer setup
          workflow.


12. Return to the Printer Setup screen, select the printer you
          added.


13. Select Printer Name, update the printer
          name, and select Save Changes. As a best
          practices, use the following naming convention for kitchen
          printers:

- Prep station name


- KP


- (Last number in the IP address)



For example, "Cold Station KP (171)" or "Backup KP
          (170)".


14. Select Backup Printer, choose a backup
          printer, and select Save Changes. If printing
          fails at this printer, the system redirects tickets to the backup
          printer.



## To add a printer on Toast Web

1. [Access Toast Web
          ](adminGuide-adminAccessToastAdminBackend).


2. Choose Payments > Checks & receipt setup >
          Printers and cash drawers.


3. Select the + Add button and then enter an
          identifying name for the kitchen printer. As a best practice, use
          the following naming convention for kitchen printers.

- Prep station name


- KP


- (Last number in the IP address)



For example, "Cold Station KP (171)" or "Backup KP
          (170)".


4. Specify the printer's model. For example, Epson
          U220.



> **Note**
> 
> The configuration options are specific to the printer
            model.



5. Enter the printer's IP address.


6. Depending on the printer make and model you may also have the
          following configurations:



> **Note**
> 
> Label configurations are only available for item label
            printers Epson L90 and TLP400.


- Ticket Type : Configures the type of
              ticket that the printer is printing, either Kitchen
              ticket or Item label.


- Label Size : Configures the size of
              the ticket for Item label ticket types. The
              ticket size options are:

- Small Vertical : A 1.5 by 3 inch
                  ticket. This label is printed sideways to optimize paper
                  usage.


- Small Horizontal : A 3 by 1.5
                  inch ticket.


- Medium Horizontal : A 3 by 2 inch
                  ticket.


- Large Square : A 3 by 3 inch
                  ticket.



Small and medium-sized tickets do not include custom logos
              or footers and summarize the number of modifiers not visible on
              the ticket (for example, "+2 modifiers").

For the Epson L90 printer, small vertical, small
              horizontal, and medium horizontal label sizes **must** use existing 76-80mm label printer
              paper.

For the TLP400 printer, small vertical and small
              horizontal label sizes **must** use
              3 inch by 1.5 inch label printer paper, and medium horizontal
              label sizes **must** use 3 inch by
              2 inch label printer paper.


- Label Format : Places either the
              Guest Name or Ticket
              Number at the top of the ticket. This is only
              available for small and medium item label sizes.


- Custom footer : Adds a custom footer
              to the end of the printed ticket.




7. Set the Kitchen Ticket Font Size.

The Customer Receipt Font Size does not
          apply to kitchen-only printers and can be left at the default
          setting.


8. Verify that the paper width is set to
          Wide.

The Narrow setting applies only to legacy
          printer models that Toast no longer supplies.



> **Important**
> 
> Item labels only use the Wide paper
            width.



9. To print kitchen tickets in English, set the
          Character Set to
          Western.

Currently, the only other character set that Toast supports is
          Chinese, for Toast TLP400, Epson U220 -
          Chinese, and Epson L90 printers. Note that if you use a Chinese
          printer, you must translate and enter all menu names and kitchen
          names into Chinese characters.


10. After you identify at least one printer, you can specify
          another printer as its Backup. If printing
          fails at this printer, the system redirects tickets to the
          backup.


11. Verify that the Cash Drawer option is set
          correctly. Typically, you set prep stations other than bar stations
          to No Cash Drawer.


12. Save and publish your changes.



