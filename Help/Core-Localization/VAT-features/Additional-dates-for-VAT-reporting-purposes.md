

All VAT reporting for Slovenia, Croatia, and Serbia needs to be performed according to VAT date and not Transaction date (which is how standard functionality for Tax reporting works). For VAT reporting purposes following dates are added to several documents: 

* VAT date
* VAT Payable date
* Document Receipt date (used for defaulting VAT date)

VAT date and VAT Payable date (when populated) are transferred to a VAT date field (additional localized field) on Tax transactions as a result of document posting. This date is then used for VAT calculation and reporting.

List of documents where additional VAT date fields are enabled:


|**Document**| **Available dates** |
|--|--|
|Pending Vendor Invoice |VAT date, VAT Payable date, Document Receipt date  |
|Invoice Journal |VAT date, VAT Payable date, Document Receipt date  |
|Free Text Invoice | VAT date  |
|Sales Invoice |VAT date  |
|Project Invoice | VAT date |
|Intercompany Invoice  |VAT date  |
|General Journal |VAT date, VAT Payable date  |
|Collection letter  | VAT date |
|Interest letter  |VAT date  |


VAT date validation is also added. If the VAT date is missing, posting such a document will result in an error.  

  
  

## Defaulting VAT date and VAT payable date*
----

In order to facilitate the posting, there is a possibility to set up VAT date and VAT payable date defaulting. Options for defaulting are:
   - None: VAT date has to be entered manually.
   - Posting date: VAT date defaults from posting date (field “Date” in journals and FTI, “Invoice date” on Sales invoice).
   - Document date: field “Invoice date” on the vendor invoice.
   - Document receipt date: applicable only for inbound documents.

VAT date defaulting setup is added to the following modules: 
   - General Ledger - Setup - General Ledger Parameters - Adacta localization:
      - VAT date defaulting from the setup above is applicable in the General journal. If general journal entry has account type “Vendor” or “Customer”, setup from Accounts payable/Accounts receivable is active.
      - Check Test Scenario for [VAT Date General](VAT-Date.zip).
   - Accounts Payable - Setup - Accounts Payable Parameters - Adacta localization: 
      - VAT date defaulting from Accounts payable is implemented on Pending vendor invoice and Vendor invoice journal.
      - Check Test Scenario for [VAT Date Vendor](VAT-Date.zip).
      - Check Test Scenario for [VAT Date Invoice](VAT-Date.zip).
   - Accounts Receivable - Setup - Accounts Receivable parameters - Adacta localization:
      - There is no “Default VAT payable date” setup at accounts receivable parameters and no “Document receipt date” option in the selection. 
      - VAT date defaulting from Accounts receivable is implemented on the Sales invoice, Free text invoice, and Project invoice. 
      - Check Test Scenario for [VAT Date FTI](VAT-Date.zip).
      - Check Test Scenario for [VAT Date Project](VAT-Date.zip).

*Enabled as part of a separate Tax package

## Closing VAT settlement period*
----

VAT settlement period can be closed using extended localization features. 

Field “Closed” is added to Period intervals. If the field is marked, the period is closed for VAT posting. This means that sales tax transactions can’t be posted in that period. The field can be un-marked whenever wanted. 

*Enabled as part of a separate Tax package
