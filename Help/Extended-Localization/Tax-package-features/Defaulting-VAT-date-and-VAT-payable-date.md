# How To: Set default VAT date and VAT payable date

As part of the localization package VAT date is added to some documents (for more details check Localization features) and can be entered manually. With tax package, user is able to setup defaulting rules for VAT date calculations. It is possible to set up a VAT date and VAT payable date defaulting. 



For VAT reporting purposes following dates are added:
-	VAT date
-	VAT Payable date
-	Document Receipt date
VAT date is also added on Tax transactions and is generated automatically when posting following documents with sales tax:
1.	Pending Vendor Invoices (VAT date, VAT Payable date, Document Receipt date)
2.	Invoice Journal (VAT date, VAT Payable date, Document Receipt date)
3.	Free Text Invoice (VAT date)
4.	Sales Invoice (VAT date)
5.	Project Invoice (VAT date)
6.	Intercompany Invoice (VAT date)
7.	General Journal (VAT date, VAT Payable date)
8.	Collection letter (fee with sales tax)
9.	Interest letter (interests with sales tax)
Additional setup is available for VAT date and VAT Payable date calculation. VAT date validation is added. If VAT date is missing, posting of such document is disabled.  
1.1	Defaulting VAT date and VAT payable date*
In order to facilitate the posting, there is a possibility to set up VAT date and VAT payable date defaulting. Options for defaulting are:
-	None: VAT date has to be entered manually
-	Posting date: VAT date defaults from posting date (field “Date” in journals and FTI, “Invoice date” on Sales invoice)
-	Document date: field “Invoice date” on vendor invoice 
-	Document receipt date: applicable only for inbound documents
VAT date defaulting setup is added to following modules: 
-	General Ledger  Setup  General Ledger Parameters  Adacta localization
 
VAT date defaulting from the setup above is applicable in General journal. If general journal entry has account type “Vendor” or “Customer”, setup from Accounts payable/Accounts receivable is active.
 
-	Accounts Payable  Setup  Accounts Payable Parameters  Adacta localization
VAT date defaulting from Accounts payable is implemented on Pending vendor invoice and Vendor invoice journal.
        
 
-	Accounts Receivable  Setup  Accounts Receivable parameters  Adacta localization
There is no “Default VAT payable date” setup at accounts receivable parameters and no “Document receipt date” option in the selection. 
 
VAT date defaulting from Accounts receivable is implemented on Sales invoice, Free text invoice, and Project invoice. 
