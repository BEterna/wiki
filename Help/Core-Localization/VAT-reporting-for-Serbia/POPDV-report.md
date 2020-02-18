# How To: Create POPDV report

VAT taxpayer is obliged to, pursuant to Article 46, paragraph 1 of the Law on VAT, and in order to properly calculate and pay VAT, keeps records in a way that allows you to control the calculation and payment of VAT in each tax period. In that records are required to provide records of transactions, activities, respectively other business changes, in particular data relating to the circulation of goods and the service performed by the VAT taxpayer, that is, which was provided to him, by invoices or other documents which serve as invoices in accordance with the Law, respectively
documents confirming a business change (e.g., insurance contract, lease agreement concluded with a natural person, copyright contract, contract on the part, etc.), as well as other information relevant to the correct calculation of VAT.

## Setup

In order to be able to generate POPDV form mandatory setup have to be completed.

### POPDV format

1. On the path Tax > Setup > Parameters > General ledger parameters > tab Adacta localization, POPDV format should be assigned.

### Reporting codes

Reporting codes are used to direct amounts in appropriate columns of the report. List of all available reporting codes opens on the following path Modules > Tax > Setup > Sales tax > Sales tax reporting codes.
 
NOTE: Reporting codes used for POPDV report should have Serbian report layout assigned.

###  Sales tax authorities setup

In order to enable Serbian VAT reports layouts, this report needs to be defined on Tax authority.  

### Sales tax code setup

Each transaction which should be shown in the report should have appropriate sales tax setup assigned. Setup that defines in which column of the report amounts will be shown are od the Report setup (for amounts with positive sign) and Report setup – Credit note (for amounts with negative sign) tabs.
 
NOTE: Automatically reversed transactions will go in the same column as original transaction.
Mapping between reporting codes and POPDV form is in the file:
 
## Generating report

1. New VAT report is generated on the following path Modules > Tax > Declarations > Sales tax > Report sales tax for settlement period.
2. In order to run the report, parameters should be set as follows:
  - Settlement period – choose the one related to new VAT setup
  - From date – enter starting date of VAT period
  - Sales tax payment version – choose Original option
  - Print report – turn this parameter to Yes if PPPDV the report should be printed
  - With POPDV – turn this parameter to Yes in order to create POPDV form lines
3. After click OK and PPPDV form will be displayed:
 
Besides creating PPPDV report, new lines in POPDV form for selected VAT period will also be created. All POPDV forms are listed Modules > Tax > Declarations > Serbia > PDV > POPDV forms

## Detailed transactions
 
Detailed list of all transactions included in report will be displayed after click on Transactions button.
 
All transactions are grouped in sections in accordance with official form of POPDV report. Inside of each section are listed transactions with all necessary details (Document number, Voucher, Document date, VAT date, Vendor/Customer name, VAT number and amounts).

## Summary form – POPDV

Summary data in the form of POPDV data are shown when you click on Summary button from the list of all POPDV forms.

## Export to XML

Function for export the data into XML format in order to be able to upload it to web portal of Tax administration office is available on the header of POPDV report list.
 
On the bottom of the screen following dialog will appear:
 
In order to Save the file on the location on your computer, click Save button. If you want to get only preview of the file, click Open.
 


