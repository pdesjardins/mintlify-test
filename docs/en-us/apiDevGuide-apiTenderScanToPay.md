---
title: "Scan-to-pay"
id: apiTenderScanToPay
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiBuildingATenderProviderIntegrationOmitChunkFromSearchIndex.md
parentSectionTitle: "Tender provider integrations"
previousSectionFile: apiDevGuide-apiTenderPmsIntegration.md
previousSectionTitle: "Hotel property management system integration"
nextSectionFile: apiDevGuide-apiAnalyticsOmitChunkFromSearchIndex.md
nextSectionTitle: "Chapter 11. Analytics"
excerpt: "The Toast tender API scan-to-pay feature..."
keywords: ["scantopay"]
procedures: 0
codeExamples: 0
---

The Toast tender API scan-to-pay feature allows the Toast platform to automatically identify a guest account. After recognizing a guest, a transaction can be closed to the appropriate location, such as a guest room, without the need to look up a guest’s account.

You can use scan-to-pay in the following ways: 

- Scan a QR code: The guest presents a QR code that, once scanned, directs a Toast transaction to the guest’s account.


- Enter a guest's unique identifier: On the Toast POS app, enter the guest’s unique identifier to charge their transaction to their account.



Before you can use scan-to-pay, you must be a Toast integration partner or subscribe to an integration that supports the tender API scan-to-pay feature. To become an integration partner, see the [Integration partnership process](integrationDevProcess.html).

The following sections describe the Toast platform processes that take place during a scan-to-pay transaction, how to process a scan-to-pay transaction using a QR code, and how to process a scan-to-pay transaction with a guest's unique identifier.

### Tender API scan-to-pay transactions

The tender API scan-to-pay transactions use the same transactions as other tender API communications. These transactions include: 

- `retrieveDiscounts`


- `retrievePayments`


- `redeem`


- `gratuity`


- `reverse`



For more information about the tender API transactions, see [Transaction descriptions](apiTenderPmsIntegration.html#apiTenderTransactionDescriptionsPMS).

If you scan a QR code, or enter a guest's unique identifier, and the code is not recognized, you could receive an error. For information about how to respond to certain errors, see [Error handling](apiTenderProviderIntegrationsOverview.html#apiTenderErrorHandling).

### POS workflow

The following sections describe how to complete a transaction using a QR code or a guest's unique identifier.

#### Using a scan-to-pay QR code

The following procedure describes how to complete a scan-to-pay transaction using a QR code.

**Procedure 10.16. To complete a transaction with a scan-to-pay QR code**

1. On the Toast POS app payment terminal screen, select Other payments from the payment types on the right side of the screen. The Select alternate payment type dialog appears. You may need to scroll down to locate the Other paymentsbutton.

![Payment terminal screen with "Other payments" emphasized.](https://doc.toasttab.com/doc/media/hot_scan_to_pay_otherpaymentsbutton.png)


2. Select your scan-to-pay QR code payment type and then select Done. The name of your payment type may differ from the example below. 

![The "Select alternate payment type" dialog with the "Scan QR code" button emphasized.](https://doc.toasttab.com/doc/media/hot_scan_to_pay_SelectQRCode.png)


3. After you select your scan-to-pay payment type, your device’s camera or QR scanner is activated. Position the guest’s QR code in the area to be scanned by the Toast POS camera or barcode scanner.


4. After the QR code is scanned, the guest account has been identified and the payment workflow continues normally. For more information about payment workflows, see [Payment workflow overview](platformPwfOverview.html).



#### Using a unique guest identifier

Guests can be given a unique identifier to use at the POS during checkout. You can find the guest's unique identifier in the API JSON payload for a tender API transaction as the `tenderIdentifier`. For examples of the tender API JSON payload, see [Transaction descriptions](apiTenderPmsIntegration.html#apiTenderTransactionDescriptionsPMS).

The following procedure describes how to process a transaction using a guest’s unique identifier.

**Procedure 10.17. To complete a transaction with a unique guest identifier**

1. On the Toast POS app payment terminal screen, select Other payments from the available payment types on the right side of the screen. The Select alternate payment type dialog appears. You may need to scroll down to locate the Other paymentsbutton. 

![Payment terminal screen with "Other payments" emphasized.](https://doc.toasttab.com/doc/media/hot_scan_to_pay_otherpaymentsbutton.png)


2. Select your scan-to-pay guest identifier payment type and then select Done. The name of your payment type may differ from the example below. 

![Alternate payment type screen with "Guest ID" emphasized.](https://doc.toasttab.com/doc/media/hot_scan_to_pay_selectGuestId.png)


3. Enter your guest’s unique identifier and select Use Code.



> **Note**
> 
> You may select Scan With Camera to continue the payment process by scanning the guest’s QR code if available.


!["Enter code" dialog with "Use code" button emphasized.](https://doc.toasttab.com/doc/media/hot_scan_to_pay_enterGuestId.png)


4. After the guest's unique identifier is entered, the payment workflow continues normally. For more information about payment workflows, see [Payment workflow overview](platformPwfOverview.html).



