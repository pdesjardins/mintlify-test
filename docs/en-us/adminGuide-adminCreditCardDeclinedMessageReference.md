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

When a card payment cannot be processed, the Toast POS device shows a message from the card network. These response messages can be difficult to interpret. The following table shows the response messages received most frequently on Toast POS devices with descriptions for why that message might appear.



> **Note**
> 
> The messages and the descriptions shown in the following tables are produced by the card processor, not by Toast. The information provided in these tables is intended for reference only, and is subject to change without notice by the card network.



<table>
  <thead>
    <tr>
      <th>Response Message</th>
      <th>Descriptions</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>*REQUEST DENIED*</td>
      <td>Do not honor</td>
    </tr>
    <tr>
      <td>AUTH DECLINED</td>
      <td>Do not honor<br/>Transaction not permitted to issuer/cardholder<br/>Exceeds withdrawal limit<br/>Domain Restriction Controls Fail<br/>Declined-transaction in violation of law<br/>Declined PIN attempts</td>
    </tr>
    <tr>
      <td>AUTH TRN NO AL'W</td>
      <td>Auth transaction not allowed for this payment</td>
    </tr>
    <tr>
      <td>CALL OPER</td>
      <td>Refer to card issuer<br/>Refer to call center</td>
    </tr>
    <tr>
      <td>CALL VOICE OPER</td>
      <td>Refer to card issuer<br/>Re-enter transaction</td>
    </tr>
    <tr>
      <td>CARD EXPIRED</td>
      <td>Expiration date check failed<br/>Expired card<br/>Card expiry date less than current date</td>
    </tr>
    <tr>
      <td>CARDHLDR DECLINE</td>
      <td>Declined per cardholder request</td>
    </tr>
    <tr>
      <td>CVD ERROR</td>
      <td>Do not honor</td>
    </tr>
    <tr>
      <td>DECLINED</td>
      <td>Declined by user<br/>Invalid effective date on card</td>
    </tr>
    <tr>
      <td>ERR PROC FIELD</td>
      <td>Format error, invalid value in message</td>
    </tr>
    <tr>
      <td>HOLD - CALL</td>
      <td>Pick up</td>
    </tr>
    <tr>
      <td>INV CARD NUMBER</td>
      <td>Invalid cardholder account<br/>Account number not found in BIN table</td>
    </tr>
    <tr>
      <td>INVALID AMOUNT</td>
      <td>Invalid amount</td>
    </tr>
    <tr>
      <td>INVALID CARD</td>
      <td>Invalid card number</td>
    </tr>
    <tr>
      <td>INVALID CARD NO</td>
      <td>Invalid card number</td>
    </tr>
    <tr>
      <td>INVALID EXP DATE</td>
      <td>Invalid expiry date</td>
    </tr>
    <tr>
      <td>INVALID FUNCTION </td>
      <td>Transaction not permitted to terminal </td>
    </tr>
    <tr>
      <td>INVALID MERC NO </td>
      <td>Invalid merchant or terminal </td>
    </tr>
    <tr>
      <td>INVALID PIN </td>
      <td>Invalid pin </td>
    </tr>
    <tr>
      <td>LOST/STOLEN CARD</td>
      <td>Lost or stolen card</td>
    </tr>
    <tr>
      <td>NO CHECKING ACCT</td>
      <td>Error</td>
    </tr>
    <tr>
      <td>PICK UP CARD </td>
      <td>Pick up card <br/>Decline - pick up card<br/>Pick up card - No Fraud<br/>Pick up card (Special Condition)<br/>Pick up card (Special Condition)(Fraud Account)<br/>Lost card - pick up<br/>Stolen card - pick up</td>
    </tr>
    <tr>
      <td>PIN TRIES EXCEED</td>
      <td>Re-enter transaction</td>
    </tr>
    <tr>
      <td>PROC ERROR 13</td>
      <td>System error</td>
    </tr>
    <tr>
      <td>SECURITY VIOLATION</td>
      <td>Security violation</td>
    </tr>
    <tr>
      <td>TRAN NOT ALLOWED</td>
      <td>Transaction not permitted to terminal</td>
    </tr>
    <tr>
      <td>TRANS DENIED</td>
      <td>Do not honor<br/>Invalid cardholder account<br/>Unable to locate record<br/>Insufficient funds<br/>Restricted card<br/>Security violation<br/>Account activity limit exceeded<br/>Allowable number of PIN entry tries exceeded<br/>One or more errors in message<br/>File is unavailable<br/>No credit account<br/>Fraudulent activity detected</td>
    </tr>
    <tr>
      <td>TRANS NOT ALLOW</td>
      <td>Transactions not allowed to cardholder<br/>Transactions not allowed to terminal<br/>Illegal transaction - violation of law<br/>Capture transactions not allowed for this payment type<br/>Capture transaction on authorization only terminal<br/>Private label transaction not allowed for terminal<br/>Store reporting transactions not allowed</td>
    </tr>
  </tbody>
</table>

