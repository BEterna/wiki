# How To: Create PDD-GI report

This topic provides country/region-specific information about personal tax reporting in accordance with the Macedonian legislative requirements. 

## Setup 

### General ledger parameters 

1. Open General ledger – Ledger setup – General ledger parameters.
2. To be able to preview and export personal tax report, it is necessary to select electronic reporting formats for PDD-GI. 

### Income types  

1. Open Tax – Setup – Adriatic – Personal tax – Income types.
2. It is necessary to set up income types for reporting purposes. Using button “New” entry with income type and description is created. Income type is constructed in format: “income type.subincome.paymenttype”. 

### Non cash type 

1. Accounts payable – Non cash personal receivables – Non cash type.
2. Create non-cash types for reporting non-cash personal receivables. Define default sales tax group and sales tax item group, select offset account, and define whether tax is included for each of the types.  

### Sales tax authorities 

1. Open Tax – Indirect taxes – Sales tax – Sales tax authorities 
2. Additional tax authority needs to be created for purposes of Personal tax functionality. Value in field “Report layout” has to be “Default” since personal tax entries are not reported in VAT books). In field “Vendor account” vendor is selected (vendor who the entries for personal tax payments in vendor payment journal and liabilities for payments will be created). 

### Sales tax settlement periods 

1. Open Tax – Indirect taxes – Sales tax – Sales tax settlement periods.
2. New sales tax settlement period should be created for personal tax purposes. 

Tax authority, created earlier, should be selected in field “Authority”. We will be using “Monthly” period interval unit with interval duration “1”. Since the same functionality is being used for VAT and personal tax, it is necessary to define Period type value as “Personal tax”. This setup enables that upon closing the period only entries for personal tax will be considered in calculation (period type “Personal tax” prevents the generation of VAT report and settlement of VAT entries).  

### Ledger posting groups 

1. Open Tax – Setup – Sales tax – Ledger posting groups.
2. New ledger posting group is opened for ledger posting. According to our business practice, we open as much ledger posting groups as there are different ledger accounts we want to post liabilities to. 

If vendor account is defined on tax authority, there is no need to set up Settlement account since closing the period will post personal tax entries to vendor, defined as tax authority on sales tax settlement period for personal tax.  

### Sales tax codes 

1. Open Tax – Indirect taxes – Sales tax – Sales tax codes.
2. Personal tax income type is defined on sales tax code. For every income type there are sales tax codes with personal tax setup. 
3. Under General, settlement period and ledger posting group, created for personal tax purposes, and currency are defined.  

Sales tax codes are created for deductions, calculated from gross amount. For correct calculation of deductions from gross the functionality of negative tax is used on those sales tax codes that define deductions from gross. Enabling field “Allow negative sales tax percentage” allows entry of negative sales tax code value.  

Sales tax code percentage is entered in form Values. When entering value for income tax it is important to enter also potential personal exemption, tax allowances, and contributions that reduce the basis for calculation.  There are additional fields in form Value (“Personal tax” part) that are considered for the calculation for income tax percentage. Percentage of sales tax code value is automatically updated after entering.  

#### Setup for personal tax reporting 

1. Setup in Adacta localization tab on sales tax codes needs to be correctly populated for personal tax reporting to work. 

Personal tax reporting: PDD-GI 

Income type: selected from Tax – Setup – Adriatic – Personal tax – Income types 

#### Payment setup 

Payment section of Adacta localization tab on sales tax codes enables entry of payment data, such as Vendor account, Bank account to which the payment of personal tax will be executed, Payment ID, and Central bank purpose code. Entered data are transferred to vendor journal payment line using Payment proposal. 

### Sales tax groups 

1. Open Tax – Indirect taxes – Sales tax – Sales tax groups.
2. Add adequate sales tax codes to sales tax groups. 

### Item sales tax groups 

1. Open Tax – Indirect taxes – Sales tax – Item sales tax groups.
Create item sales tax group for each personal tax income type and add adequate sales tax codes.  

### Procurement categories 

Top of Form 1 

Bottom of Form 1 

Procurement and sourcing – Procurement categories 

Create procurement category for each income type and define Item sales tax group.  

Procurement categories need adequate ledger account for posting – this setup is done in Inventory management – Setup – Posting – Posting.  

If the cost of contract work is posted via vendor invoice, ledger account setup is done under “Purchase expenditure for expense” transaction type. In case product receipts are used, posting setup also needs to be done in “Purchase expenditure, un-invoiced” section. 

## Personal tax transactions 

### Purchase order and/or Vendor invoice 

1. Enter Purchase order/Vendor invoice for each vendor by choosing adequate procurement category in document line (in case of using price lists, service item should be used). Entering multiple income types on one source document (multiple procurement categories on purchase order/vendor invoice) is also supported. Gross amounts are entered on purchase line. If entry of net amount is required, “Prices include sales tax” needs to be marked in document header, tab Setup. 
2. Item sales tax group (from procurement category) and sales tax group (from vendor) are automatically populated in line details – Setup.  
3. After posting vendor invoice, vendor transaction and tax transactions are created. 

#### Non-cash personal receivables 

1. New tab “Personal tax” is added to purchase order and vendor invoice line details. Here, non-cash personal receivables can be defined. Select Yes for line to be marked as non-cash receivable, define non-cash type, and select the receiving worker.  
2. After the invoice is posted, non-cash receivables can be generated in Accounts payable – Non cash personal receivables – Non cash personal receivables. 
3. Use button New to create new document. 
4. Add date and select Non-cash type. Upon selecting non-cash type, sales tax group, item sales tax group, and offset account, defined on the type, are transferred to the document.  
5. Click “Import vendor invoice lines” to transfer invoice lines. Define dates From and To (period for posted vendor transaction).  
6. Upon confirming, non-cash personal receivable line is automatically (after Refresh) created with reference to vendor invoice.  
7. Post non-cash receivables with button Post. 
8. See chapter Other transactions on how to create personal tax payments for non-cash receivables. 

Expense report 

Personal tax transactions can also be created through expense report. Expenses need to be posted with sales tax codes for personal tax.  

 

If “Allow grouping of transactions via offset account” is active in Expense management parameters… 

 

… vendor transaction is summarized upon posting, whereas tax transactions are (separately) posted with expense report transaction dates. 

 

In this case, “Other transaction” option needs to be selected when creating personal tax payments, to correctly transfer all tax transactions to vendor payment journal. See chapter Other transactions on how to create personal tax payments. 

Payments 

Prepare vendor payment journal lines (e.g. through standard payment proposal functionality). Vendor transaction is transferred to payment journal line.   

Payment lines for personal tax payments are created through Functions – Create personal tax payments.  

 

Enter payment date and bank account to execute payments from. If bank account is left empty, the offset account transfers from method of payment of the vendor, selected on sales tax code. 

 

After confirming, payment lines are created, including detailed message about the created personal tax payments. 

 

At this stage, it is already possible to create personal tax report (navigate to chapter Personal tax report for details). Correcting or deleting payment journal lines is not possible while report exists, as lines are locked for editing. Correction is possible after deleting existent personal tax report. 

Include closed transactions 

Function “Create personal tax payments” in payment journal has been updated to allow creation of personal tax payments for transactions that have already been settled. Option “Include” personal tax payments for closed transaction has been added.  

 

In “Closed transactions” section mark field “Include” and enter “From date, To date” (date period of settlement of transactions). After confirming, personal tax payment lines are created in vendor payment journal.  

Other transactions 

Create personal tax payments for non-cash personal receivables or expense reports, where vendor transaction is summed by offset account but tax transactions are posted on dates from expense report, using Functions – Create personal tax payments à Include other transactions. Select Yes in field Include and define From/To dates for posted personal tax transactions. 

 

After confirmation, personal tax payments are created. 

Example for non-cash receivables: 

 

Example for expense report: 

 

## Personal tax report 

Personal tax report can be generated from posted or unposted vendor payment journals. 

Creating personal tax report can be done through Tax – Declarations – Macedonia – PDD-GI – PDD-GI reporting. 

 

Or through Tax – Declarations – Macedonia – PDD-GI – PDD-GI forms à button Read transactions. 

 

Personal tax reporting parameters: 

From date, To date: enter from/to payment dates for which to report personal tax transactions. 

Include transactions from unposted journals: enable if transactions from unposted vendor payment journal are also to be included in personal tax report. Otherwise, report will be created from posted payment journal. 

After confirming, infolog about created personal tax report is displayed. Generated reports by payment date and income type can be found in Tax – Declarations – Macedonia – PDD-GI – PDD-GI forms.  

 

By clicking on “Details”, reporting transactions for selected report are displayed. It is possible to manually edit fields First name, Last name, Bank account number, and Payment date. Bank account number transfers from Third-party bank account identification field from vendor payment journal; if it is not defined there, then it transfers from vendor’s default bank account.  

 

County transfers from party’s primary address. It is a mandatory field for reporting. 

 

 

Note: Correcting or deleting payment journal lines is not possible while report exists, as lines are locked for editing. Correction is possible only after deleting existing personal tax report. 

 

Export report by selecting “Export to Excel” or “Export to XML”. 

 

### Import transactions 

It is possible to import reporting transaction. Select “Import transactions” and select a file. 

 

## Personal tax payments  

Tax – Inquiries and reports – Withholding tax inquiries – Personal tax payments 

An overview of personal tax amounts is available in this form. Form is populated with data right after the vendor invoice has been posted. When the vendor payment journal is created, field Payment date is populated with value. 

## Closing tax settlement period 

1 Open Tax – Declarations – Sales tax – Report sales tax for settlement period.
2. Using this functionality, sales tax report is created, enabling user to check tax transactions for personal tax before posting them.  
3. Select settlement period for personal tax and define “From date” (any date in a month that needs to be settled). 
4. After confirming, another window is opened. Enable “Include details” if additional section of the report “Details” is to be displayed in sums for each sales tax code.  
5. Confirming generates sales tax report. 
6. Open Tax – Declarations – Settle and post sales tax.

Closing tax settlement period is executed once a month – after payment of all liabilities for selected period has been processed. Using tax settlement functionality, liability for personal tax payments is posted to vendor, defined in Sales tax authority which is chosen in Sales tax settlement period for personal tax).  

Enter settlement period for personal tax, first day of the month that needs to be closed, and date on which the transaction will be posted. After confirming, a window for generating sales tax report is opened.  

Ignore possible messages about Customer/Vendor name not specified. 

From accounts, defined in ledger posting groups for personal tax, amount is posted to vendor account. 

Process creates a payment liability in sum for the period to personal tax vendor.  

If vendor payment journals are already posted with bank statements, payments and liabilities need to be manually settled using “Settle transactions” functionality on vendor.  