---
title: "Credit card payments"
id: adminCreditCardPayments
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminCreditCardsOmitChunkFromSearchIndex.md
parentSectionTitle: "Credit card payments"
previousSectionFile: adminGuide-adminCreditCardsOmitChunkFromSearchIndex.md
previousSectionTitle: "Credit card payments"
nextSectionFile: adminGuide-adminCreditCardDeclinedMessageReference.md
nextSectionTitle: "Card declined message reference"
keywords: ["credit", "card", "payments"]
procedures: 0
codeExamples: 0
---

#### Prepaid credit cards

You can accept prepaid credit cards as a form of payment in the Toast platform. The way that you accept prepaid credit cards is similar to accepting traditional credit cards. It is common for restaurant employees to swipe a prepaid credit card without realizing that it is not a traditional credit card. Because prepaid credit cards have a limited available balance, there are important differences in the way the Toast platform processes prepaid credit card payments.

The holder of a prepaid credit card might be able to load money into the card account or a prepaid credit card might be a gift card with a fixed initial amount of money available. Purchases made using the card deduct money from the remaining balance. Prepaid credit cards are branded and supported by major credit card processing networks.

You select Credit and swipe or enter a prepaid credit card to accept it as a form of payment, but prepaid credit cards behave differently than traditional credit cards. The following list describes some differences:

- If you apply a prepaid credit card to a guest's check and the available balance on the card is less than the amount of the check, the Toast platform will perform a partial authorization for the amount that is available on the card. The restaurant guest must provide an additional form of payment for the remaining check amount.

Unlike a prepaid credit card, a traditional credit card is declined if the available credit is less than the amount of the check.


- Prepaid credit card accounts do not pay additional amounts after all funds are deducted from the account. For example, if a tip adjustment exceeds the available balance on a prepaid credit card, the card provider will not pay the additional tip amount.

Unlike a prepaid credit card, a traditional credit card might pay a tip amount that exceeds the available credit on the card account (depending on the credit card company's policies). The credit card company might charge the card holder fees and require that the card holder repay the additional amount.



A partial authorization for a check payment allows a restaurant guest to use the remaining balance on a prepaid credit card, even if that balance is not enough to pay the entire check amount. After the Toast platform applies the partial authorization amount to the check, the check remains open, with the remaining amount that is due.

The following example shows Toast POS device screens during a check payment using a partial authorization for a prepaid credit card. The first image shows the payment screen with a check balance due.

**Example 6.1. Initial payment screen**

![A Toast POS device screen showing the payment screen with a $12.10 balance due.](https://doc.toasttab.com/doc/media/prepaid-cards-amount-due.png)

  
The following image shows the authorization screen for a prepaid credit card transaction.

**Example 6.2. Initial payment authorization screen**

![A Toast POS device screen showing the authorization, or signature, screen for a prepaid credit card payment. The screen includes controls for selecting a tip amount.](https://doc.toasttab.com/doc/media/prepaid-credit-card-first-tip-screen.png)

  
The following image shows the dialog box that alerts restaurant employees that the prepaid credit card has been partially authorized, and that an additional payment amount is still due. After you acknowledge this message, you return to the payment screen.

**Example 6.3. Partial authorization message**

![A Toast POS device screen showing the partial authorization screen.](https://doc.toasttab.com/doc/media/prepaid-cards-partial-authorization.png)

  
The following image shows the payment screen with the partial authorization for a prepaid credit card payment.

**Example 6.4. Payment screen with partial authorization**

![A Toast POS device screen showing the balance due for a check. The partial authorization for a prepaid credit card is shown. The remaining balance is shown.](https://doc.toasttab.com/doc/media/prepaid-remaining-balance-due.png)

  
The following image shows the payment screen for a transaction that includes the remaining balance due for a prepaid credit card payment.

**Example 6.5. Remaining balance paid**

![A Toast POS device screen showing the remaining balance paid.](https://doc.toasttab.com/doc/media/prepaid-remaining-balance-paid.png)

  
