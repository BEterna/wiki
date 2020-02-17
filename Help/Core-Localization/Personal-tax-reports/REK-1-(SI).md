# How To: Prepare REK-1 report

REK-1 is a Slovenian personal tax report, which legal entities or natural persons who perform business activities are obliged to report to the Slovenian tax authority (FURS) if they pay incomes from employment. Report layout and the required conditions are based on paragraph 8, Article 58 of the Tax Procedure Act - ZDavP-2.

Since salaries are standardly not calculated in D365, the Slovenian REK-1 reporting feature enables only the generation of the legally required reporting in terms of employee travel expenses. Transactions for REK-1 reporting are generated automatically from expense reports and invoices for travel expenses, but they can also be manually added. Export (XML) in the format, required by the Slovenian tax authorities and a preview (HTML) of the REK-1 report are also part of this localized feature.

## Setup

### General ledger parameters

1. Open General ledger – Ledger setup – General ledger parameters.
2. To define the export format, navigate to Adacta localization and section Electronic reporting. Select “REK1 report” in the field “REK 1 electronic reporting format".
 
### Income type

For REK-1 reporting it is necessary to create income types. Income types define which field on iREK will the transaction be recorded in. Create as many income types as there are reporting fields (the naming in the Income type field is optional). 
By selecting the appropriate value in the field "iREK field B", the amount of the transaction (that carries the information about income type) will be displayed inadequate fields on REK-1 report.

1. Open Tax – Setup – Adriatic – Expenses -  Income types.
2. “REK Income Type” value is entered in Tax – Setup – Slovenia – Withholding tax – REK Income Types.
 
### Income type for cash advances

NOTE: Deprecated with version 8.1!

1. Open Expense management – Setup – General – Expense management parameters.
2. Income type for cash advances needs to be defined in the “Adacta” section. This ensures that cash advances are also generated in REK-1 transactions and reported. 
 
### Payment methods

1. Open Expense management – Setup – General – Payment methods.
2. For each of the payment methods it is required to define the moment when the transaction becomes relevant for reporting by choosing Income reporting mode:
   - At settlement: expense transaction becomes a candidate for reporting when it is settled (paid)
   - At expense posting: expense transaction is included in the list of candidates for REK-1 after expense cost is posted
   - No reporting: it is not included in REK-1 reporting

     If income reporting mode “At settlement” or “At expense posting” is chosen, it is necessary to define Income type, created for REK-1.

3. Trigger for reporting is the payment to the worker (reimbursement). In case of credit card there are two options:
   - Business trip cost, paid with a credit card, can be reported from expense report if payment method has income reporting mode “At expense posting”; such transaction will become a candidate for REK reporting right after the expense report is posted. In this case, the REK reporting field “For worker” on vendor invoice for credit card expense should be left empty, otherwise, the transaction would be reported twice (first, after posting expense report, and second, after vendor invoice for credit card expenses is paid).
   - Travel expense, paid with a credit card, can also be reported from vendor invoice which carries information about worker (more in chapter Purchase document entry). In this case, expense-paid with a credit card, if it is entered on the expense report, should have income reporting mode “No reporting”. This way, the transaction from the expense report will not become a candidate for REK reporting – expense will be reported from the vendor invoice. 

### Expense categories

1. Open Expense management – Setup – General – Expense categories.
2. The default value in the “Options for REK-1” field is “Default” for newly created entries. 
3. Select adequate income types for each of the expense categories that need to be reported. Categories need to be created in such a way that one category fits one income type (can be reported in one “B06” field). 
 
Expense transactions that should not be reported in the REK-1 report, should have "Always exclude" setup on expense category and no Income type.
 
Information about Income type is recorded on vendor transaction upon expense posting and transferred to vendor payments using payment proposal – but only if Payment attribute “Income type” is marked in Methods of payment.

4. Open Accounts payable – Payment setup – Methods of payment.
 
If transactions to vendor payment journal are transferred using “Settle transactions”, information about Income type is not transferred from transaction to vendor payment journal line. Attempt to post such payment journal line results in error – it is necessary to manually choose Income type in tab Payment before posting.
 
## Purchase document entry

Vendor invoice or Purchase order line details allow reporting of the business trip cost for a worker in tab Personal tax. Select adequate Income type and Worker in the REK-1 section. 
 
Creating a vendor invoice, linked to purchase order, transfers information for REK-1 reporting from purchase order to invoice Line details. 
The transaction that was posted from vendor invoice with information about worker does not carry Income type information (VendTrans Income type field is empty) but is always included in the list of candidates for REK-1 after it has been paid.

## Generating REK-1 transactions

1. Open Tax – Declarations – Slovenia – REK reporting – REK-1 – Personal tax transactions.
2. Transactions to report need to be collected in Personal tax transactions form first. Only entries generated in this form can be reported in REK-1. Use button “Generate transactions” to define the date period for transferring REK-1 transactions. 
3. Transactions are generated from three sources (when which transaction is generated – after posting, after settlement – depends on setup on payment methods):
   - Expense lines: from posted expense reports when the method of payment’s income reporting mode is “At expense posting”.
   - Posted vendor invoice lines: from paid vendor invoices with a link to the worker (after vendor invoice, with link to the worker, is settled, it becomes a candidate for REK-1 reporting).
   - Vendor transactions: from paid reimbursement to work when the method of payment’s income reporting mode is “At settlement”.
Message details upon generating displays number of lines that have been added from each source.
4. REK-1 transactions form can be filtered by “Open” transactions (not yet reported), “Reported”, and “All”. Fields displayed in the form are the following ones:
   - Date: payment date (if income reporting mode is “At settlement” or in case of vendor invoice transaction) or transaction date (when income reporting mode is “At expense posting”).
   - Worker: worker for whom the business trip cost will be reported.
   - Amount: transaction amount (in case of vendor invoice amount reported is base + VAT).
   - Income type: income type of the transaction
   - Linked: source from which each entry was generated (options are: Vendor invoice line, Expense line, Vendor transaction; manually added lines have value “Not linked”).
   - Reporting number: number of created REK-1 report that contains this transaction; once a line has a reporting number, it cannot be edited anymore.
     - If REK-1 report has not yet been generated, such transaction will have an empty value in field Reporting number;
     - If the REK-1 report is deleted, information about the reporting number is automatically deleted.
   - Generated: marked with a checkmark are those transactions that are created through “Generate transactions” functionality; manually added entries do not have a checkmark in this field.
   - Description: displays additional information about the transferred line; for manually added lines this is a free text field. 
5. Button “Open source” displays source document for the selected transaction (Expense report for expense line, for vendor invoice line Invoice journal, is displayed, and Vendor transaction is opened for vendor transaction for the worker).
 
It is possible to manually adjust the Amount of the lines that have not yet been reported. Information about the original amount remains in the Description. The adjusted amount is reported to REK-1.
 
### Manually adding transactions

Manually adding transactions to REK-1 transactions form is enabled because of all cases that cannot be covered by automation (cancellations, prepayments, partial payments of vendor invoices…). 

1. Create a new entry using the button “New”. 
2. Define date, select worker, and entry cost amount. The manually added line has the value “Not linked” in column Linked and no checkmark in field Generated. 
3. Enter any text in the Description field.
 
## Creating REK-1

1. Open Tax – Declarations – Slovenia – REK-1 reporting or Tax – Declarations – Slovenia – REK-1 forms - button REK-1 reporting.
2. Enter any date in a month to report transactions of that month that have not yet been reported (by entering a date in February, all entries from REK-1 transactions in February that do not have reporting number, will be reported). After confirming, the REK-1 report is generated. Multiple reports can be generated in one month.
3. Clicking on button “REK-1 transactions” will display only those entries that are included in the selected REK-1 report.
4. Click on Preview to check the report.
5. The report is opened in an individual tab. Field B06 is populated with the amount.
6. Use “Export to XML” to export the report to the XML format for eDavki. 
 
## Test cases

  - [Transactions with different income reporting modes on the expense report](Test-Scenario-REK1.zip): 
REK-1 transactions are generated according to the setup of income reporting mode on payment methods. Only transactions from REK-1 transactions form are reported in the REK-1 report.
   - [Always exclude transaction from REK-1 reporting](Test-Scenario-REK1.zip):
Transactions from Expense report that have set up on expense category "Always exclude" are not included in REK-1 transactions and therefore, not reported.
   - [Transaction with income reporting mode No reporting](Test-Scenario-REK1.zip): Transactions from Expense report that have payment method with "No reporting" income reporting mode are not included in REK-1 transactions and therefore, not reported.
   - [Cash advance for worker](Test-Scenario-REK1.zip): Deprecated with version 8.1
   - [Reporting reimbursements of business trip costs for worker](Test-Scenario-REK1.zip): According to setup on payment methods, REK-1 transactions are reported after being paid to the worker.
   - [Partial reimbursement (in installments) of business trip costs for worker](Test-Scenario-REK1.zip): Deprecated with version 8.1<br>
If the amount to be paid to the worker is paid in installments, it is possible to generate each installment respectively in the form of the REK-1 transaction.
   - [One vendor invoice for one worker](Test-Scenario-REK1.zip): It is possible to connect the vendor invoices with the worker who the cost is paid for.
   - [One vendor invoice for multiple workers](Test-Scenario-REK1.zip): It is possible to connect the vendor invoices with multiple workers who the cost is paid for by dividing the cost to as many vendor invoice lines as there are workers.
   - [Payment of vendor invoice in installments](Test-Scenario-REK1.zip): In case of paying vendor invoice in installments, REK transaction for the first installment is generated in the full amount of vendor liability. Before reporting, it is necessary to manually adjust the value to the amount paid by installment. The following installments have to be manually entered in REK transactions.
   - [Manual correction of REK-1 transaction](Test-Scenario-REK1.zip): It is possible to manually correct the amount to be reported or add another entry to the list of transactions to be reported.
 

<!--
[Detailed documentation](https://adacta.sharepoint.com/:w:/r/sites/ERP-Product-Development/Shared%20Documents/D365FO%20Localization%20documentation/D365O%20LOC_SI%20REK-1.docx?d=w03f44baa02f34a5aa5de364e26dcd17c&csf=1&e=UYOfAy)
-->
