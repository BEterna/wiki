# Adriatic localization
[[_TOC_]]
____
## Release AdLocalization_10.0_2023.01.03.1
### Localization core
|Area|Description|type|
|---|---|---|
|eInvoice RS|eInvoice RS RegistrationID added to ER|New feature|

### Localization exchange rate providers
|Area|Description|type|
|---|---|---|
|HNB|Import ratio direction fix for HNB API V3|Bug fix|
____
## Release AdLocalization_10.0_2022.12.23.1

### Localization core
|Area|Description|type|
|---|---|---|
|eInvoice SI|Physical persons email support|New feature|
|REK|REK-O support|New feature|
|VAT|VAT payable date defaulting on invoice approval|New feature|
|Statistical reports SI|KRD and SFR usability improvements|New feature|
|eInvoice RS|Support for notes, unit of measure on prepayments and automatic generation for prepayments|New feature|
|Tax HR|Updated tax report layouts for EUR (PDV, PPO, IRA, URA), updated Electronic reporting formats (ZP, PDV-S); Added support for legacy HRK (layouts display HRK if company currency is HRK, new ER formats for HRK support)|New feature|

### Localization exchange rate providers
|Area|Description|type|
|---|---|---|
|HNB|New exchange rate provider - EUR support|New feature|
___
## Release AdLocalization_10.0_2022.12.05.1

### Localization Fiscalization
|Area|Description|type|
|---|---|---|
|Fiscalization|Profirma fiscalization fix|Bug fix|
____
## Release AdLocalization_10.0_2022.12.03.1

### Localization core
|Area|Description|type|
|---|---|---|
|eInvoice HR|Mapping of customer referenc in ER|New feature|
___

## Release AdLocalization_10.0_2022.11.30.1

### Localization core
|Area|Description|type|
|---|---|---|
|VAT|VAT date on Invoice approval not transfering|Bug fix|
|eInvoice HR|Update for business process|New feature|
|eInvoice RS|Advance invoice support|New feature|
|Tax BA|Payment method inupt error fix|Bug fix|
___

## Release AdLocalization_10.0.0.2022.11.09.01

### Localization core
|Area|Description|type|
|---|---|---|
|Taxable persons list|Added currently active description to Slovenian taxable persons form|New feature|
|BIH VAT report|Amounts with two decimals|New feature|
|SFR and KRD Report|Added Open in excel functionality for sector allocation and SFR/KRD codes buttons on Vendor and Customer master card|New feature|

### Localization extended
|Area|Description|type|
|---|---|---|
|Import taxable persons|Added address, street number, name, Tax exempt number on customer creation from Taxable persons list|New feature|


## Release AdLocalization_10.0_2022.10.12.1

### Localization core
|Area|Description|type|
|---|---|---|
|eInvoice|eInvoice HR - ER fix for business unit|Bug fix|
|Tax report|POPDV xml export - field 5.1 value fix|Bug fix|
___


## Release AdLocalization_10.0_2022.09.09.1

### Localization core
|Area|Description|type|
|---|---|---|
|Prepayments|Prepayment posting standard code reference fix|Bug fix|
|Accounts payable|Vendor invoice form Localizaiton license dependency fix|Bug fix|

### Dual currency (CRO)
**!!!**  *Breaking change - field rename **!!!**
|Area|Description|type|
|---|---|---|
|Dual currency (CRO)|Dual currency setup localization dependency fix|Bug fix|
|Dual currency (CRO)|*Added conversion of remaining amount for collaction letters (rename of Fee amount field in dataprovider)|New feature|
___

## Release AdLocalization_10.0_2022.08.25.1

### Localization core

|Area|Description|type|
|---|---|---|
|Prepayments|Extended description field on Prepayment journal line and on Advance invoice layout |New feature|
|Prepayments|Duplicate voucher fix|Bug fix|

### Fiscalization

|Area|Description|type|
|---|---|---|
|Fiscalization HR|Creation of reccuring invoice or with FTI template fix of termina|Bug fix|
___

## Release AdLocalization_10.0_2022.05.10.2

**!!!** *Important: 10.0.25 application depandency* **!!!**

### Localization core

|Area|Description|type|
|---|---|---|
|(RS) E-invoices|Support for Serbian E-invoices|New feature|
|Prepayments|Prepayment posting to GL with correct exchange rate on transaction date|Bug fix|
|Tax report (ADR)|10.0.25 dependency upgrade|Dependency update|
___