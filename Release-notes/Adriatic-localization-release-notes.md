# Adriatic localization
[[_TOC_]]
____
## Release AdLocalization_#10.0.0.2023080701
### Localization core
|Area|Description|Type|
|---|---|---|
|Tax|Validation added when changing VAT date on Posted sales tax transactions. Only Changes from or to a date in an open ledger period are allowed.|Bug fix|
|Tax|Vat date and VAT payable date added to data entities: General journal line entry, VendInvoiceJournalLine, CustInvoiceJournalLine.|New feature|
|eInvoice|Updated Electronic report model in order to include Unite of measure external code only for code "eRacun" for project invoices.|Bug fix|

____
## Release AdLocalization_#10.0.0.2023070601
### Localization core
|Area|Description|Type|
|---|---|---|
|VAT reporting for Serbia|Individual VAT reporting xml data structure update according to changes made by RS Ministry of Finance|New feature|
|Main account statement (HR)|Totals for column Amount in accounting currency are added to the report|New feature|

____
## Release AdLocalization_#10.0.0.2023062601
### Localization core
|Area|Description|Type|
|---|---|---|
|Intrastat enhancements (SI,HR)|Country/region specifics for SI and HR removed on button Transfer in Intrastat form due to Microsoft change in version 10.0.34|Dependency update|
____
## Release AdLocalization_#10.0.0.2023060501
### Localization core
|Area|Description|Type|
|---|---|---|
|VAT reporting for Serbia|Individual VAT reporting xml data structure update according to changes made by RS Ministry of Finance|New feature|
____
## Release AdLocalization_#10.0.0.2023052501
### Localization core
|Area|Description|Type|
|---|---|---|
|VAT reporting for Serbia|Individual VAT reporting|New feature|
|Main account statement (HR)|Enabled the possibility to run report for periods larger than 31 days|New feature|
|VAT features|Fields related to VAT (VAT date, VAT payable date, Customer/Vendor, Address, Tax exempt number) can be defaulted on new lines when creating vendor invoice lines from Invoice register lines trough Vendor invoice approval form|New feature|
|eInvoice|Updated Electronic report model in order to include Unite of measure external code only for code "eRacun"|Bug fix|

### Localization Bank
|Area|Description|Type|
|---|---|---|
|Bank features|Added new restriction for accessing Bank localization fields in Method of payments form only for Adriatic legal entities|Bug fix|
____
## Release AdLocalization_10.0.0.2023041901
### Localization core
|Area|Description|Type|
|---|---|---|
|eInvoice RS|Changed position of GLN number in the exported xml file|Changed feature|
|OPZ STAT-1 HR|New data entity for updating/migrating original invoice amount and original VAT amount (Customer transactions (localization data))|New feature|

## Release AdLocalization_10.0_2023.04.07.1
### Localization core
|Area|Description|Type|
|---|---|---|
|VAT|Localization fields removed from data entity "Sales tax code values" and transferred to "Sales tax code values V2" due to removal of the entity "Sales tax code values" in version 10.0.32|Dependency update|
|VAT reporting for Croatia|Fixed IRA and URA reports for years previous to 2023 after tax rate 0% introduced|Bug fix|
|VAT reporting|Tax reporting number refresh on vendor invoice journal after changing vendor account on line|Bug fix|
|VAT reporting|Tax reporting fields initialized when using Open In Excel functionality with journals (Vendor invoice journal)|Bug fix|
|Security|Fixed Access level rights (replaced deprecated "Invoke" with "Delete")|Bug Fix|

### Localization Bank
|Area|Description|Type|
|---|---|---|
|Exchange rates (HR)|Fixed import exchange rates for a selected date range|Bug fix|
|Security|Fixed Access level rights (replaced deprecated "Invoke" with "Delete")|BugFix|

### Localization Fiscalization
|Area|Description|Type|
|---|---|---|
|Security|Fixed Access level rights (replaced deprecated "Invoke" with "Delete")|BugFix|

### Localization KEP
|Area|Description|Type|
|---|---|---|
|Security|Fixed Access level rights (replaced deprecated "Invoke" with "Delete")|BugFix|

### Localization Tax
|Area|Description|Type|
|---|---|---|
|Security|Fixed Access level rights (replaced deprecated "Invoke" with "Delete")|BugFix|

### Localization Cash register
|Area|Description|Type|
|---|---|---|
|Cash register|Additional specific Eastern Europe functionalities enabled for BA, HR, MK, RS and SI (Cash accounts - Cash report)|New Feature|
|Cash register|Cash order report: Fields Order number, Legal entity address and Created date time added to report|New Feature|
|Cash register|Cash report: Fields Legal entity address and Created date time added to report|New Feature|

____
## Release AdLocalization_10.0.0.2023031701
### Localization core
|Area|Description|Type|
|---|---|---|
|Advance invoice|Update of Prepayment reports|New feature|
|Personal tax reports - REK (SI)|REK-O updates|New feature|
|Statistical reports (SI)|Enabling updates of SFR Sector allocation through Open-In-Excel functionality s|New feature|
|Fiscalization (HR)|Location id and terminal id information extended to 20 characters|Bug fix|

### Localization Cash register
|Area|Description|Type|
|---|---|---|
|Cash register|Eastern Europe and Russia functionality for Petty cash enabled for SI, HR and SR|New feature|

____
## Release AdLocalization_10.0.0.2023022301
### Localization core
|Area|Description|Type|
|---|---|---|
|eInvoice RS|Support for Customer reference and Customer requisition on prepayments|New feature|
### Localization Bank
|Area|Description|Type|
|---|---|---|
|Vendor payments|Validation for payment id with model HR04 fix|Bug fix|
____
## Release AdLocalization_10.0.0.2023020301
### Localization core
|Area|Description|Type|
|---|---|---|
|VAT reporting for Croatia|Extending reports for tax rate 0%|New feature|
____
## Release AdLocalization_10.0.0.2023013001
### Localization core
|Area|Description|Type|
|---|---|---|
|eInvoice RS|ER configuration updated with new fields (Recquisition date, Buyer reference Id) |New feature|
|eInvoice RS|IssueDate changed and allowance base amount divided with zero|Bug fix|
|VAT|VAT date not filled from Settlement date when using Conditional sales tax option|Bug fix|
|eInvoice SI|ER configuration update|Bug fix|
____
## Release AdLocalization_10.0_2023.01.03.1
### Localization core
|Area|Description|Type|
|---|---|---|
|eInvoice RS|eInvoice RS RegistrationID added to ER|New feature|

### Localization exchange rate providers
|Area|Description|Type|
|---|---|---|
|HNB|Import ratio direction fix for HNB API V3|Bug fix|
____
## Release AdLocalization_10.0_2022.12.23.1

### Localization core
|Area|Description|Type|
|---|---|---|
|eInvoice SI|Physical persons email support|New feature|
|REK|REK-O support|New feature|
|VAT|VAT payable date defaulting on invoice approval|New feature|
|Statistical reports SI|KRD and SFR usability improvements|New feature|
|eInvoice RS|Support for notes, unit of measure on prepayments and automatic generation for prepayments|New feature|
|Tax HR|Updated tax report layouts for EUR (PDV, PPO, IRA, URA), updated Electronic reporting formats (ZP, PDV-S); Added support for legacy HRK (layouts display HRK if company currency is HRK, new ER formats for HRK support)|New feature|

### Localization exchange rate providers
|Area|Description|Type|
|---|---|---|
|HNB|New exchange rate provider - EUR support|New feature|
___
## Release AdLocalization_10.0_2022.12.05.1

### Localization Fiscalization
|Area|Description|Type|
|---|---|---|
|Fiscalization|Profirma fiscalization fix|Bug fix|
____
## Release AdLocalization_10.0_2022.12.03.1

### Localization core
|Area|Description|Type|
|---|---|---|
|eInvoice HR|Mapping of customer referenc in ER|New feature|
___

## Release AdLocalization_10.0_2022.11.30.1

### Localization core
|Area|Description|Type|
|---|---|---|
|VAT|VAT date on Invoice approval not transfering|Bug fix|
|eInvoice HR|Update for business process|New feature|
|eInvoice RS|Advance invoice support|New feature|
|Tax BA|Payment method inupt error fix|Bug fix|
___

## Release AdLocalization_10.0.0.2022.11.09.01

### Localization core
|Area|Description|Type|
|---|---|---|
|Taxable persons list|Added currently active description to Slovenian taxable persons form|New feature|
|BIH VAT report|Amounts with two decimals|New feature|
|SFR and KRD Report|Added Open in excel functionality for sector allocation and SFR/KRD codes buttons on Vendor and Customer master card|New feature|

### Localization extended
|Area|Description|Type|
|---|---|---|
|Import taxable persons|Added address, street number, name, Tax exempt number on customer creation from Taxable persons list|New feature|


## Release AdLocalization_10.0_2022.10.12.1

### Localization core
|Area|Description|Type|
|---|---|---|
|eInvoice|eInvoice HR - ER fix for business unit|Bug fix|
|Tax report|POPDV xml export - field 5.1 value fix|Bug fix|
___


## Release AdLocalization_10.0_2022.09.09.1

### Localization core
|Area|Description|Type|
|---|---|---|
|Prepayments|Prepayment posting standard code reference fix|Bug fix|
|Accounts payable|Vendor invoice form Localizaiton license dependency fix|Bug fix|

### Dual currency (CRO)
**!!!**  *Breaking change - field rename **!!!**
|Area|Description|Type|
|---|---|---|
|Dual currency (CRO)|Dual currency setup localization dependency fix|Bug fix|
|Dual currency (CRO)|*Added conversion of remaining amount for collaction letters (rename of Fee amount field in dataprovider)|New feature|
___

## Release AdLocalization_10.0_2022.08.25.1

### Localization core

|Area|Description|Type|
|---|---|---|
|Prepayments|Extended description field on Prepayment journal line and on Advance invoice layout |New feature|
|Prepayments|Duplicate voucher fix|Bug fix|

### Fiscalization

|Area|Description|Type|
|---|---|---|
|Fiscalization HR|Creation of reccuring invoice or with FTI template fix of termina|Bug fix|
___

## Release AdLocalization_10.0_2022.05.10.2

**!!!** *Important: 10.0.25 application depandency* **!!!**

### Localization core

|Area|Description|Type|
|---|---|---|
|(RS) E-invoices|Support for Serbian E-invoices|New feature|
|Prepayments|Prepayment posting to GL with correct exchange rate on transaction date|Bug fix|
|Tax report (ADR)|10.0.25 dependency upgrade|Dependency update|
___