---
title: "Calculating expected cash deposits"
id: apiCalculatingExpectedCashDeposits
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiGettingCashManagementInformationOmitChunkFromSearchIndex.md
parentSectionTitle: "Getting cash management information"
previousSectionFile: apiDevGuide-apiGetCashDeposits.md
previousSectionTitle: "Getting cash deposit entries"
nextSectionFile: apiDevGuide-portalWebhooksOmitChunkFromSearchIndex.md
nextSectionTitle: "Chapter 9. Webhooks"
externalReferences: [https://stedolan.github.io/jq/]
excerpt: "The expected cash deposit for a restaurant is the currency amount of cash that should be available to be removed from a restaurant and deposited in a bank or other financial institution for a..."
keywords: ["calculating", "expected", "cash", "deposits", "CASH", "CashEntry", "CASH_COLLECTED", "TIP_OUT", "Undo Tip Out", "get_payment"]
procedures: 1
codeExamples: 3
---

The expected cash deposit for a restaurant is the currency amount of cash that should be available to be removed from a restaurant and deposited in a bank or other financial institution for a business day. You can calculate the expected deposit for a business day using information about cash transactions that you get from the orders API and information about cash collected and cash payments that you get from the cash management API. For more information about the orders API, see [Orders API overview](apiDevGuide-portalOrdersApiOverview).

The following lists describe the components of the expected cash deposit for a Toast POS restaurant.

**Cash Included in the Expected Deposit**

- Cash payments for checks (cash drawer transactions).


- Cash collected from restaurant employees (for example, at the end of their shifts).


- Cash added to a restaurant cash drawer in a cash in operation. This is not a part of routine Toast POS operation.



**Cash Deducted from the Expected Deposit**

- Cash removed from a restaurant cash drawer to pay for a pre-configured expense in a pay out operation.


- Cash removed from a restaurant cash drawer to pay employee gratuities in a tip out operation.


- Cash removed from a restaurant cash drawer in a cash out operation. This is not part of routine Toast POS operation.



The following procedure explains how to calculate the expected deposit for one restaurant business day.

**Procedure 8.1. Calculating the Expected Deposit for One Business Day**

1. Get the list of payment GUIDs for the business day by sending a `GET` request to the `payments`endpoint of the orders API. Include the *`paidBusinessDate`* parameter to specify the business day.


2. Get detailed information about each payment by sending a GET request to the `payments/<em>\{guid\}</em>` endpoint of the orders API.


3. Calculate the sum of the `amount` values for each payment that has the `type``CASH`. The following example shows the `amount` and `type` values for a payment.

```
\{
  "entityType": "OrderPayment",

    [contents omitted]

  "amount": 26.51,

    [contents omitted]

  "type": "CASH",

    [contents omitted]
\}
```


4. Get detailed information about each cash entry for the business day by sending a `GET` request to the `entries` endpoint of the cash management API. Include the *`businessDate`* parameter to specify the business day. The `entries` endpoint returns a JSON array of `CashEntry` objects.


5. Calculate the sum of the `amount` values for each cash entry that has any `type` value other than `CASH_COLLECTED`. Pay out, tip out, and cash out entries have negative amounts. The following example shows the `amount` and `type` values for a cash entry.

```
[
  \{
    "entityType": "CashEntry",

      [contents omitted]

    "amount": -50.75,

      [contents omitted]

    "type": "PAY_OUT"
  \}
]

```



> **Note**
> 
> The only exception to omitting cash entries of `type``CASH_COLLECTED` is an undone `TIP_OUT`. When a restaurant employee undoes a `TIP_OUT` cash entry, the system posts a `CASH_COLLECTED` cash entry for the same amount and a `reason` value of `Undo Tip Out`. You should include undone tip outs in your calculations of your expected cash deposits.



6. Calculate the sum of the total cash payments (see [Step 3](apiDevGuide-apiCalculatingExpectedCashDeposits#apiProcCalculateTotalCashPayments)) and the total non-payment cash entries (see [Step 5](apiDevGuide-apiCalculatingExpectedCashDeposits#apiProcCalculateTotalCashEntries)). The result is the expected cash deposit for the business day.



The following example shell script calculates the expected cash deposit for one restaurant on one business day. The script uses the **jq** utility to get information from Toast API JSON response data. For more information about the **jq**utility, see the [jq web site](https://stedolan.github.io/jq/). This example script is intended as an illustration of the procedure for calculating expected deposits and is not suitable for production use.

**Example 8.5. Shell script to calculate the expected cash deposit for one business day**

```
#!/bin/bash

# Set parameters for Toast API requests.
SERVER="https://`[toast-api-hostname]`"
CLIENT_ID="`my-client`"
CLIENT_SECRET="`tbKr17l*!dMUE1hU3a3F`" # Must be URL encoded
RESTAURANT_GUID="`B42C2273-B35A-42E4-9D9E-B0538312E18B`"
BUSINESS_DATE="`20250422`"
# Hold the authentication token and reuse it.
AUTHENTICATION_TOKEN=""

# Define functions for this example script.

authenticate () \{
    # Get an authentication token for Toast API requests.
    curl -X POST \
    -H "Content-Type: application/json" \
    -d "\{\"clientId\":\"$\{CLIENT_ID}\",\"clientSecret\":\"$\{CLIENT_SECRET}\",\"userAccessType\":\"TOAST_MACHINE_CLIENT\"}" \
    -s -o authentication-response~ \
    $\{SERVER}/authentication/v1/authentication/login
    # Hold the authentication token and reuse it.
    AUTHENTICATION_TOKEN=`jq -r '.token.accessToken' authentication-response~`    
}

get_payments () \{
    # Get a list of the payment transactions for a business day.
    curl -X GET \
    -H "Authorization: Bearer $\{AUTHENTICATION_TOKEN}" \
    -H "Toast-Restaurant-External-ID: $\{RESTAURANT_GUID}" \
    -s -o my-payments~ \
    "$\{SERVER}/orders/v2/payments?paidBusinessDate=$\{BUSINESS_DATE\}"

    # Find the number of payment record GUIDs in the JSON array
    # returned by the payments endpoint.
    NUMBER_OF_PAYMENTS=`jq '. | length' my-payments~`

    # Get detailed information about each payment.
    PAYMENT_NUMBER=0
    while [[ "$\{PAYMENT_NUMBER}" -lt "$\{NUMBER_OF_PAYMENTS\}" ]]
    do
      PAYMENT_GUID=`jq -r .[$\{PAYMENT_NUMBER\}] my-payments~`
      # Run the get_payment function. Pass one payment GUID as an argument.
      get_payment $\{PAYMENT_GUID\}
      PAYMENT_NUMBER=$(($\{PAYMENT_NUMBER\}+1))
    done
}

get_payment () \{
    # Get detailed information about one payment transaction.
    curl -X GET \
    -H "Authorization: Bearer $\{AUTHENTICATION_TOKEN}" \
    -H "Toast-Restaurant-External-ID: $\{RESTAURANT_GUID}" \
    -s -o my-payment~ \
    "$\{SERVER}/orders/v2/payments/$\{1\}"

    # If the type of the payment is CASH, add its amount to the total
    # cash transactions for the business day.
    TRANSACTION_TYPE=`jq -r .type my-payment~`
    PAYMENT_STATUS=`jq -r .paymentStatus my-payment~`
    if [[ "$\{TRANSACTION_TYPE}" == "CASH" ]] && [[ "$\{PAYMENT_STATUS\}" != "VOIDED" ]];
    then
      NUMBER_CASH_TRANSACTIONS=$(($\{NUMBER_CASH_TRANSACTIONS\}+1))
      # Find the currency amount of the cash transaction.
      CURRENT_TRANSACTION=`jq -r .amount my-payment~`
      # Add the current transaction amount to the total for the business day.
      TOTAL_CASH_TRANSACTIONS=`echo \
        "$\{TOTAL_CASH_TRANSACTIONS}+$\{CURRENT_TRANSACTION\}" | bc`
    fi
}

get_entries () \{
    # Get an array of the cash entries for the business day.
    curl -X GET \
    -H "Authorization: Bearer $\{AUTHENTICATION_TOKEN}" \
    -H "Toast-Restaurant-External-ID: $\{RESTAURANT_GUID}" \
    -s -o my-cash-entries~ \
    "$\{SERVER}/cashmgmt/v1/entries?businessDate=$\{BUSINESS_DATE\}"

    # Calculate the total of all entries except for the CASH_COLLECTED type.
    for CASH_ENTRY_AMOUNT in `jq '.[] | \
      select(.type!="CASH_COLLECTED") | .amount'  my-cash-entries~`
    do
      TOTAL_CASH_ENTRY_ADJUSTMENTS=`echo \
        "$\{TOTAL_CASH_ENTRY_ADJUSTMENTS}+$\{CASH_ENTRY_AMOUNT\}" | bc`
    done
\}

# Run functions in this example script.

# Run the authenticate function in this example script to get an
# authentication token for API requests.
authenticate

# Run the get_payments function in this example script to get the
# total cash payments (cash collected from customers)for the business day.
NUMBER_CASH_TRANSACTIONS=0
TOTAL_CASH_TRANSACTIONS=0
get_payments

# Run the get_entries function in this example script to get the total
# cash entries for the business day, excluding cash collected.
# This is typically a negative number.
TOTAL_CASH_ENTRY_ADJUSTMENTS=0
get_entries

# Calculate the total expected cash deposit by summing the cash collected
# and the total of the cash entries (typically negative).
EXPECTED_CASH_DEPOSIT=`echo \
  "$\{TOTAL_CASH_TRANSACTIONS}+$\{TOTAL_CASH_ENTRY_ADJUSTMENTS\}" | bc`

# Report the totals.
echo "Number cash transactions:     $\{NUMBER_CASH_TRANSACTIONS\}"
echo "Total cash transactions:      $\{TOTAL_CASH_TRANSACTIONS}"
echo "Total cash entry adjustments: $\{TOTAL_CASH_ENTRY_ADJUSTMENTS}"
echo "Expected cash deposit:        $\{EXPECTED_CASH_DEPOSIT\}"
```



(1) These parameters hold values that you need to get an authentication token and make Toast API requests. For more information, see Authentication and restaurant access.

(2) Send a GET request to the user management API to get an authentication token. For more information, see Authentication and restaurant access. Store the authentication token string in a script variable so that other example functions can use it.

(3) Send a GET request to the orders API to get a list of the GUIDs of each payment made during a business day. For each payment GUID, run another example shell script function to get detailed information about the payment.

(4) Specify the business day of the payments in the paidBusinessDate query parameter.

(5) Count the number of payment GUIDs for the business day.

(6) Run a separate function to get detailed payment information for each of the payment GUIDs for the business day.

(7) Get one GUID from the list.

(8) Run the example get_payment function and pass the payment GUID as an argument.

(9) Increment a counter variable to move on to the next payment GUID.

(10) Send a GET request to the orders API to get detailed information about one payment. Check the transaction type of the payment. If the payment type is CASH, add the payment amount to the total of cash payments for the business day.

(11) The get_payments function passes a payment GUID as an argument to this function.

(12) Get the type value for the payment.

(13) Only include CASH payments in the total. Exclude voided payments.

(14) Get the currency amount of the payment.

(15) Add the amount of the payment to the total amount of the cash payments for the business day.

(16) Send a GET request to the cash management API to get detailed information about all cash entries for the business day. Calculate the cumulative amounts of each cash entry, excluding entries that have the typevalue CASH_COLLECTED.

(17) Specify the business day of the cash entries in the businessDate query parameter.

(18) Get a list of the amounts of the entries that do not have the typeCASH_COLLECTED.

(19) Add each amount to the total cash entries for the business day. The amount values are negative or positive depending on whether the cash entry removes or adds cash to a restaurant cash drawer.

(20) Set the total of cash payments to zero and run the function that gets payments for the business day.

(21) Set the total of cash entries to zero and run the function that gets cash entries for the business day.

(22) Calculate the sum of total cash payments and total cash entries for the business day to get the expected cash deposit.

(23) Number of non-voided cash transactions.

  
