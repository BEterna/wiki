# Adriatic localization
[[_TOC_]]

____
## Release AdLocalization_#*10.0.20240909.01
**!!! Important: 10.0.39 application dependency !!!**
### Localization Core
|Area|Description|Type|
|---|---|---|
|VAT reporting for MK| Reporting tax codes 1260, 1121 and 1131 were updated so that now are included also in Book of customer invoices report.| Update feature|
|VAT reporting for HR|New reporting code 3080 was created for field III.15 in PDV report.|Updated feature|
|VAT reporting for HR|New reporting codes 30111, 30121, 30131 were created for Croation URA report.|Updated feature|
|VAT reporting|A new field check has been added for vendor and customer data during tax reporting data refresh. This includes additional validation to retrieve data from the customer or vendor when the journal field is empty.|Updated feature|
|eInvoice|A new feature is available for importing vendor eInvoices ([Detail information](/Help/Core-Localization/eInvoice/eInvoice-for-Croatia)). It extends the existing eInvoice configuration with new parameters. However, currently only eInvoice format for Croatia is supported (UBL).| New feature|
|Row version change tracking|Added row version change tracking for localization tables. The change si not introducing any new localization features or alter existing functionality, but complies with Microsoft change track functionality option known as [row version change tracking](https://learn.microsoft.com/en-us/dynamics365/fin-ops-core/dev-itpro/data-entities/rowversion-change-track).|Dependency update|

### Localization KEP (RS)
|Area|Description|Type|
|---|---|---|
|KEP (RS)|Mandatory "From date" and "To date" fields have been added to the report header for the KEP form.|Updated feature|
|Row version change tracking|Added row version change tracking for localization tables. The change si not introducing any new localization features or alter existing functionality, but complies with Microsoft change track functionality option known as [row version change tracking](https://learn.microsoft.com/en-us/dynamics365/fin-ops-core/dev-itpro/data-entities/rowversion-change-track).|Dependency update|

### Localization Bank
|Area|Description|Type|
|---|---|---|
|Row version change tracking|Added row version change tracking for localization tables. The change si not introducing any new localization features or alter existing functionality, but complies with Microsoft change track functionality option known as [row version change tracking](https://learn.microsoft.com/en-us/dynamics365/fin-ops-core/dev-itpro/data-entities/rowversion-change-track).|Dependency update|

### Localization Fiscalization
|Area|Description|Type|
|---|---|---|
|Row version change tracking |Added row version change tracking for localization tables. The change si not introducing any new localization features or alter existing functionality, but complies with Microsoft change track functionality option known as [row version change tracking](https://learn.microsoft.com/en-us/dynamics365/fin-ops-core/dev-itpro/data-entities/rowversion-change-track)|Dependency update|

### Localization Cash register
|Area|Description|Type|
|---|---|---|
|Cash register|Removed obsolete country region restrictions for BA, HR, MK, RS and SI in accordance with Microsoft D365 Petty Cash functionality being available as a global feature for all countries and regions. To be able to continue using the Petty cash some mandatory configuration is required:<br><ul>- In Feature management, enable the Petty cash feature.<br>- Go to Cash and bank management parameters > Cash, and select the Enable petty cash option.</ul>Petty cash remains part of BE-terna extended localization as it enables some specific Petty cash functionalities that otherwise remain restricted to Eastern Europe countries. |Dependency update|

### Localization Exchange rates
|Area|Description|Type|
|---|---|---|
|Exchange rates|Version number increased due to dependency update.| Dependency update|

### Localization General ledger features
|Area|Description|Type|
|---|---|---|
|General ledger features|Version number increased due to dependency update.| Dependency update|

### Localization Tax package features
|Area|Description|Type|
|---|---|---|
|Tax package features|Version number increased due to dependency update.| Dependency update|

____
## Release AdLocalization_#10.0.20240809.01
### Localization Core
|Area|Description|Type|
|---|---|---|
|VAT reporting for SI|Changed Evidenca IR report and Evidenca PR report to preprocessed reports. Also, exporting of VAT payable and receivable CSV is fixed.|Updated feature|
|Tax| Validation for VAT number duplicates on empty data on customers and vendors was fixed.|Bug fix|

### Localization Bank - Exchange rates
|Area|Description|Type|
|---|---|---|
|Exchange rates (MKD)|New web service was implemented for National bank of the Republic of Macedonia for importing exchange rates| Updated feature|

____
## Release AdLocalization_#10.0.20240717.01
### Localization Core
|Area|Description|Type|
|---|---|---|
|Tax| Additional validation was implemented that prevents user from creating circular referencing of ledger posting groups on prepayment setup| Bug fix|
|OPZ STAT-1 (HR)| When including Worker name data in the report, Worker's Name history is taken into account.| Bug fix|
|VAT reporting (HR)| When including Worker name data in the reports PPO, PDV S and ZP, Worker's Name history is taken into account.| Bug fix|
|Intrastat enhancements (SI.HR)| When including Worker name data in the report EU Sales list, Worker's Name history is taken into account.| Bug fix|
|VAT reporting for SI| When generating PDO report, corrections for previous periods are generated as only as corrections and are not included in current period transactions.|Bug fix|
|VAT reporting for MKD| Changes in amount formatting made in the VAT report, presenting amount values with thousands separator. Additionally, checkbox (x) in column H, line 31 was added when Total amount in line 31, column J is negative.| Updated feature|

____
## Release AdLocalization_#10.0.20240612.01
### Localization Core
|Area|Description|Type|
|---|---|---|
|OPZ STAT-1 (HR)| Users with specific roles (Accountant, AR clerk and AR manager) are able to maintain fields on open customer transactions that are relevant for the OPZ-STAT report. |Bug fix|
|VAT features (SI,HR)|Improved validation of Tax number when creating/updating Customers and using the Taxable persons list feature.|Updated feature|

### Localization Bank
|Area|Description|Type|
|---|---|---|
|Vendor payments HR |Updated SEPA ER format for HR by adding the Vendor payment journal number as part if the MsgId information.|Updated feature|

### Localization General ledger 
|Area|Description|Type|
|---|---|---|
|Year end procedure enhancements| Within Propose balancing general ledger functionality new parameter was added - Posting date. Posting date on the journal lines generated by Propose balancing general ledger functionality is defaulted from this new parameter.| New feature|

____
## Release AdLocalization_#10.0.20240509.01
### Localization Core
|Area|Description|Type|
|---|---|---|
|Intrastat enchancements| Changed the label of the menu in the Intrastat form that allows users to view compressed transactions. The old label "Intrastat archive" was changed to "Uncompressed archive". The functionality behind remains the same.|Updated feature|
|Advance invoice| When prepayment invoice is reversed, user gets an info log that new reversal journal was created (with number of new invoice and journal).| New feature|
|Advance invoice| New validation feature prevents circular references between ledger posting groups and Ledger posting group for tax in prepayments. In this way cases when a ledger posting group has a reference to itself in the field Ledger posting group for tax in prepayments, or cases a ledger posting group has a reference to a second ledger posting group in the field Ledger posting group for tax in prepayments, but the second ledger posting group has a reference to the initial ledger posting group in the field Ledger posting group for tax in prepayments, are not possible any more.| New feature|
|Advance invoice|Fixed the issue that prevented creation of records in TaxTransGeneralJournalAccountEntry table when posting general journal with sales tax code related to ledger posting groups for prepayment invoices.| Bug fix|
|Statistical reports (SI)|Added missing privileges that prevented users with role accountant to use the buttons NEW and DELETE in forms: KRD sector codes, BST setup and BST excluded posting types.|Bug fix|
____
## Release AdLocalization_#10.0.2024041201
### Localization core
|Area|Description|Type|
|---|---|---|
|VAT reporting for SI| When generating PDO report, also corrections for previous periods are created automatically and added to the report.|Updated feature|
|VAT reporting for RS, BIH|In KIF and KUF reports the description and report template were corrected. |Bug fix|

### Localization Bank
|Area|Description|Type|
|---|---|---|
|Vendor payments HR |New SEPA ER format for HR available according to new legislation requirements.|Updated feature|

### Localization Tax
|Area|Description|Type|
|---|---|---|
|Tax|Extension point enabling CoC on closed Sales tax periods provided. These changes are internal and do not introduce any new features or alter existing functionality|/|

____
## Release AdLocalization_#10.0.20240305.01
### Localization core
|Area|Description|Type|
|---|---|---|
|Localization license|According to the [platform deprecated support for SHA-1](https://learn.microsoft.com/en-us/dynamics365/fin-ops-core/fin-ops/get-started/removed-deprecated-features-platform-updates#isv-licenses-generated-using-sha1-algorithm-signature-version-1) signed licenses package now includes SHA256 signed license (supported from 10.0.11).|Updated license|
|Personal tax reports|Increased number of decimal places for social contributions value in Sales tax code value configuration form.|Changed feature|
|eInvoice SI|Two new parameters (debtor agent and debtor account) added to eInvoice parameters for Physical persons email support that are included in the Envelope XML export.|Changed feature|
|Personal tax reports SI|Changed calculation of NormExpenses in the REK 2 Electronig format due to legislation change.|Changed feature|
|VAT reporting for SI|Fixed PDO report for cases where base amount is so small that tax amount is rounded to zero.|Bug fix|
|VAT reporting HR|New IRA and URA report form available for detail analyse of receivable and payable tax transactions including also non-taxable information.|New feature|

## Release AdLocalization_##10.0.20240125.01
### Localization core
|Area|Description|Type|
|---|---|---|
|eInvoice (RS)|eInvoice xml export for RS fixed to include multiple references when Credit note is sattled with multip0le invoices. |Bug fix|
|Intrastat enchancements|Issue with weight change on product receipt not being taken into account when using Item arrival journal fix.|Bug fix|
|Personal tax reports|Additinal logic added to all personal tax reports except REK when searching for tax identification number. It allows finding also  tax identification numbers registered for a residence foreign county/reagion. |Bug fix|
|Advance invoice|Issue with manual reversing a customer prepayment invoise that generated a revesed invoice with the wrong account type is fixed.|Bug fix|
|Advance invoice|Missing Customer/vendor account and name were added to the general ledger transaction that is generated with prepayment invoice posting.|Bug fix|

____
## Release AdLocalization_#10.0.20231219.01
### Localization core
|Area|Description|Type|
|---|---|---|
|Exports using ER|Refactoring code to improve user experience when exporting data through Electronic reporting (ER) .|Changed feature|

____
## Release AdLocalization_#10.0.20231204.01
### Localization core
|Area|Description|Type|
|---|---|---|
|VAT reporting for BIH|Updated version of the ER format for export KIF and KUF into csv.|Bug fix|
|Export General ledger to file|Refactoring code for running Electronic reporting.|Changed feature|

### Localization Tax
|Area|Description|Type|
|---|---|---|
|Tax|Fixed the defaulting logic for VAT date and VAT Payable date in entity General journal line entry.|Bug fix|

____
## Release AdLocalization_#10.0.20231116.01
### Localization core
|Area|Description|Type|
|---|---|---|
|Core Localization|SalesCalcTax issue fix due to Microsoft breaking change (reference: https://www.yammer.com/dynamicsaxfeedbackprograms/#/Threads/show?threadId=2504117393334272)|Updated feature|
|VAT reporting for BIH|New version of the ER format for export KIF and KUF into csv are available according to new technical requirements issued by Indirect taxation authority BIH.|Changed feature|
|VAT reporting for BIH|KIF/KUF report preview is available for viewing KIF and KUF data in MS Excel.|New feature|
|Advance invoice|A new validation is added when creating settlements between customer/vendor transactions with a prepayment that require the selction of only one option: Settlement posting date= Latest date and no other.|New feature|
|Advance invoice|When a reversal of an Advanced invoice is created, VAT date on the generated sales tax transaction must be the same as on the reversed Advance invoice.|Bug fix|

____
## Release AdLocalization_#10.0.20231027.02
### Localization core
|Area|Description|Type|
|---|---|---|
|Export General ledger to file|Updated the name of the generated export file, including From/To date information from the filter defined when triggering the export, or current date time information when no dates are defined in the filter for generating the export file.|Changed feature|
|Personal tax reports (SI)|Rek-2 (REK-O) ER format updated by including the field A052b.|Bug fix|

### Localization Tax
|Area|Description|Type|
|---|---|---|
|Tax|Fixed to current date defaulting logic for VAT date and VAT Payable date.|Bug fix|

____
## Release AdLocalization_#10.0.0.2023092901
### Localization core
|Area|Description|Type|
|---|---|---|
|Advance invoice|Footer text from print management setup enabled in the prepayment report when using the Print management option. Report label Tax value enabled for translation.|Bug fix|
|Advance invoice| Correction option enabled when a Prepayment transaction is reversed enabling the presentation of the amount on the Debit/Credit side according to the corrections setup.|Changed feature|
|Advance invoice| Filter enabled in Posted prepayment vendor invoices form showing only records related to vendor prepayments. Filter enabled in Posted prepayment customer invoices form showing only records related to custo0mer  prepayments.|Bug fix|
|Advance invoices| Sales tax amount displayed in an accounting currency instead of in a transaction currency for prepayments: In the reversal of prepayments in a currency different than the currency of the legal entity, the Sales tax amount was presented in the accounting currency instead of in the transaction currency. The new release includes a fix of such behavior and an upgrade procedure for updating the wrongly presented Sales tax amounts on records in the past.|Bug fix|
|VAT reporting for Serbia| Individual VAT reporting xml data structure update according to changes made by RS Ministry of Finance (additional condition for Turnover amount).|New feature|
|Intrastat|Translations enabled in the intrastat IR002A (HR) ER format.| New feature|

### Localization Bank
|Area|Description|Type|
|---|---|---|
|Bank features| Features related to bank statement import for Serbia (Bank statement formats form - Halcom RS field) marked as obsolete in order to be removed in future releases. (Feature transferred to Stand alone solution for Advanced banking)|Obsolete feature|

### Localization Cash register
|Area|Description|Type|
|---|---|---|
|Cash register|Cash report labels enabled for translations.|Bug fix|
____
## Release AdLocalization_#10.0.0.2023091901
### Localization core
|Area|Description|Type|
|---|---|---|
|Tax|Validation logic extended to enable changing a blank VAT date on Posted sales tax transactions to a valid date value.|Bug fix|

____
## Release AdLocalization_#10.0.0.2023082301
### Localization core
|Area|Description|Type|
|---|---|---|
|Tax|Fixed error with Vat date and VAT payable date in data entity: General journal line entry, when using the entity in legal entities without Adriatic localization.|Bug fix|

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
|Exchange rates (H)|Fixed import exchange rates for a selected date range|Bug fix|
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
|eInvoice CRO|Update for business process|New feature|
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

### Dual currency (HR)
**!!!**  *Breaking change - field rename **!!!**
|Area|Description|Type|
|---|---|---|
|Dual currency (HR)|Dual currency setup localization dependency fix|Bug fix|
|Dual currency (HR)|*Added conversion of remaining amount for collaction letters (rename of Fee amount field in dataprovider)|New feature|
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