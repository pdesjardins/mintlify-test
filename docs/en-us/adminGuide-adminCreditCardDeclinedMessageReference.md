---
title: "Card declined message reference"
id: adminCreditCardDeclinedMessageReference
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminCreditCardsOmitChunkFromSearchIndex.md
parentSectionTitle: "Credit card payments"
previousSectionFile: adminGuide-adminCreditCardPayments.md
previousSectionTitle: "Credit card payments"
nextSectionFile: adminGuide-adminServiceChargesOmitChunkFromSearchIndex.md
nextSectionTitle: "Service charges"
excerpt: "When a card payment cannot be processed, the Toast POS device shows a..."
procedures: 0
codeExamples: 0
---

When a card payment cannot be processed, the Toast POS device shows
    a message from the card network. These response messages can be difficult
    to interpret. The following table shows the response messages received
    most frequently on Toast POS devices with descriptions for why that
    message might appear.



> **Note**
> 
> The messages and the descriptions shown in the following tables
      are produced by the card processor, not by Toast. The information
      provided in these tables is intended for reference only, and is subject
      to change without notice by the card network.


| Response Message | Descriptions | 
| --- | --- |
| *REQUEST DENIED* | Do not honor | 
| AUTH DECLINED | Do not honorTransaction not permitted to
            issuer/cardholderExceeds withdrawal
            limitDomain Restriction Controls
            FailDeclined-transaction in violation of
            lawDeclined PIN attempts | 
| AUTH TRN NO AL'W | Auth transaction not allowed for this
            payment | 
| CALL OPER | Refer to card issuerRefer to call
            center | 
| CALL VOICE OPER | Refer to card issuerRe-enter
            transaction | 
| CARD EXPIRED | Expiration date check failedExpired
            cardCard expiry date less than current
            date | 
| CARDHLDR DECLINE | Declined per cardholder request | 
| CVD ERROR | Do not honor | 
| DECLINED | Declined by userInvalid effective date
            on card | 
| ERR PROC FIELD | Format error, invalid value in message | 
| HOLD - CALL | Pick up | 
| INV CARD NUMBER | Invalid cardholder accountAccount number
            not found in BIN table | 
| INVALID AMOUNT | Invalid amount | 
| INVALID CARD | Invalid card number | 
| INVALID CARD NO | Invalid card number | 
| INVALID EXP DATE | Invalid expiry date | 
| INVALID FUNCTION  | Transaction not permitted to terminal  | 
| INVALID MERC NO  | Invalid merchant or terminal  | 
| INVALID PIN  | Invalid pin  | 
| LOST/STOLEN CARD | Lost or stolen card | 
| NO CHECKING ACCT | Error | 
| PICK UP CARD  | Pick up card Decline - pick up
            cardPick up card - No FraudPick up card
            (Special Condition)Pick up card (Special
            Condition)(Fraud Account)Lost card - pick
            upStolen card - pick up | 
| PIN TRIES EXCEED | Re-enter transaction | 
| PROC ERROR 13 | System error | 
| SECURITY VIOLATION | Security violation | 
| TRAN NOT ALLOWED | Transaction not permitted to terminal | 
| TRANS DENIED | Do not honorInvalid cardholder
            accountUnable to locate
            recordInsufficient fundsRestricted
            cardSecurity violationAccount activity
            limit exceededAllowable number of PIN entry tries
            exceededOne or more errors in
            messageFile is unavailableNo credit
            accountFraudulent activity detected | 
| TRANS NOT ALLOW | Transactions not allowed to
            cardholderTransactions not allowed to
            terminalIllegal transaction - violation of
            lawCapture transactions not allowed for this payment
            typeCapture transaction on authorization only
            terminalPrivate label transaction not allowed for
            terminalStore reporting transactions not
            allowed | 

