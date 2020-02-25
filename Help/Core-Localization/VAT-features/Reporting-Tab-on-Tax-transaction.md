# How To: Reporting Tab on Tax transactions

As part of localization, an additional “Reporting” tab is added to Tax transactions. It displays information, such as Customer/Vendor, Address, Tax exempt number, Document, Document date, and Document receipt date. This information is used for VAT reporting.

## Reporting Tab data sources
----

Following information, needed for VAT reporting purposes is added to the tab:

**Customer/Vendor** 
- Transaction is generated using Vendor Invoice, Sales Invoice, Free text invoice, and Project Invoice: data is populated from Vendor/Customer in the document header.
 - Transaction is generated using Journal with Vendor/Customer line: data is populated from Customer/Vendor field on journal line.

 **Address** 
 - Transaction is generated using Vendor Invoice, Sales Invoice, Free text invoice, and Project Invoice: data is populated from Vendor/Customer in the document header. 
 - Transaction is generated using Journal with Vendor/Customer line: data is populated from Address field on journal line.
 - Tax exempt number: 
 - Transaction is generated using Vendor Invoice, Sales Invoice, Free text invoice, and Project Invoice: data is populated from Tax exempt number from the original document. 
 - Transaction is generated using Journal with Vendor/Customer line: data is populated from Tax exempt number field on journal line.

**Document** 
  - Transaction is generated using Vendor Invoice, Sales Invoice, Free text invoice, and Project Invoice: data is populated original document. 
  - Transaction is generated using Journal with Vendor/Customer line: 
       - data is populated from Document field if fields Invoice and Document are populated fields on the journal line.
       - data is populated from the Invoice field if only field Invoice is populated on the journal line.

 **Document date** 
 -    Transaction is generated using Vendor Invoice, Sales Invoice, Free text invoice, and Project Invoice: data is populated from Invoice date on the original document. 
-    Transaction is generated using Journal with Vendor/Customer line: data is populated from the Invoice date field on journal line.

**Document receipt date** 
-    Transaction is generated using Vendor Invoice (not relevant for outgoing documents): data is populated from the Document receipt date on the original document. 
-    Transaction is generated using Journal with Vendor/Customer line: data is populated from Document receipt field on journal line.
