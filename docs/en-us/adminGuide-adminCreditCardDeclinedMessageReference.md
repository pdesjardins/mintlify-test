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



<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className="">Response Message</th>
      <th className="">Descriptions</th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="">*REQUEST DENIED*</td>
      <td className="">Do not honor</td>
    </tr>
    <tr className="">
      <td className="">AUTH DECLINED</td>
      <td className="">Do not honor <br/> Transaction not permitted to issuer/cardholder <br/> Exceeds withdrawal limit <br/> Domain Restriction Controls Fail <br/> Declined-transaction in violation of law <br/> Declined PIN attempts</td>
    </tr>
    <tr className="">
      <td className="">AUTH TRN NO AL'W</td>
      <td className="">Auth transaction not allowed for this payment</td>
    </tr>
    <tr className="">
      <td className="">CALL OPER</td>
      <td className="">Refer to card issuer <br/> Refer to call center</td>
    </tr>
    <tr className="">
      <td className="">CALL VOICE OPER</td>
      <td className="">Refer to card issuer <br/> Re-enter transaction</td>
    </tr>
    <tr className="">
      <td className="">CARD EXPIRED</td>
      <td className="">Expiration date check failed <br/> Expired card <br/> Card expiry date less than current date</td>
    </tr>
    <tr className="">
      <td className="">CARDHLDR DECLINE</td>
      <td className="">Declined per cardholder request</td>
    </tr>
    <tr className="">
      <td className="">CVD ERROR</td>
      <td className="">Do not honor</td>
    </tr>
    <tr className="">
      <td className="">DECLINED</td>
      <td className="">Declined by user <br/> Invalid effective date on card</td>
    </tr>
    <tr className="">
      <td className="">ERR PROC FIELD</td>
      <td className="">Format error, invalid value in message</td>
    </tr>
    <tr className="">
      <td className="">HOLD - CALL</td>
      <td className="">Pick up</td>
    </tr>
    <tr className="">
      <td className="">INV CARD NUMBER</td>
      <td className="">Invalid cardholder account <br/> Account number not found in BIN table</td>
    </tr>
    <tr className="">
      <td className="">INVALID AMOUNT</td>
      <td className="">Invalid amount</td>
    </tr>
    <tr className="">
      <td className="">INVALID CARD</td>
      <td className="">Invalid card number</td>
    </tr>
    <tr className="">
      <td className="">INVALID CARD NO</td>
      <td className="">Invalid card number</td>
    </tr>
    <tr className="">
      <td className="">INVALID EXP DATE</td>
      <td className="">Invalid expiry date</td>
    </tr>
    <tr className="">
      <td className="">INVALID FUNCTION </td>
      <td className="">Transaction not permitted to terminal </td>
    </tr>
    <tr className="">
      <td className="">INVALID MERC NO </td>
      <td className="">Invalid merchant or terminal </td>
    </tr>
    <tr className="">
      <td className="">INVALID PIN </td>
      <td className="">Invalid pin </td>
    </tr>
    <tr className="">
      <td className="">LOST/STOLEN CARD</td>
      <td className="">Lost or stolen card</td>
    </tr>
    <tr className="">
      <td className="">NO CHECKING ACCT</td>
      <td className="">Error</td>
    </tr>
    <tr className="">
      <td className="">PICK UP CARD </td>
      <td className="">Pick up card  <br/> Decline - pick up card <br/> Pick up card - No Fraud <br/> Pick up card (Special Condition) <br/> Pick up card (Special Condition)(Fraud Account) <br/> Lost card - pick up <br/> Stolen card - pick up</td>
    </tr>
    <tr className="">
      <td className="">PIN TRIES EXCEED</td>
      <td className="">Re-enter transaction</td>
    </tr>
    <tr className="">
      <td className="">PROC ERROR 13</td>
      <td className="">System error</td>
    </tr>
    <tr className="">
      <td className="">SECURITY VIOLATION</td>
      <td className="">Security violation</td>
    </tr>
    <tr className="">
      <td className="">TRAN NOT ALLOWED</td>
      <td className="">Transaction not permitted to terminal</td>
    </tr>
    <tr className="">
      <td className="">TRANS DENIED</td>
      <td className="">Do not honor <br/> Invalid cardholder account <br/> Unable to locate record <br/> Insufficient funds <br/> Restricted card <br/> Security violation <br/> Account activity limit exceeded <br/> Allowable number of PIN entry tries exceeded <br/> One or more errors in message <br/> File is unavailable <br/> No credit account <br/> Fraudulent activity detected</td>
    </tr>
    <tr className="">
      <td className="">TRANS NOT ALLOW</td>
      <td className="">Transactions not allowed to cardholder <br/> Transactions not allowed to terminal <br/> Illegal transaction - violation of law <br/> Capture transactions not allowed for this payment type <br/> Capture transaction on authorization only terminal <br/> Private label transaction not allowed for terminal <br/> Store reporting transactions not allowed</td>
    </tr>
  </tbody>
</table>
</div>

