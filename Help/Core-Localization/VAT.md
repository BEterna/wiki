This topic provides country/region-specific information about the localized VAT features, developed with a purpose to comply with the local legislation and tax authorities of Slovenia, Croatia, Serbia, and Northern Macedonia. According to the adequate local legislation (e.g. ZDDV-1 in case of Slovenia), a taxable event occurs when goods/services are received/delivered or when goods are imported in case of goods from other EU countries, while multiple exceptions exist. 

As part of standard D365FO tax transactions are posted and reported according to transaction posting date, which is not aligned with the local legal requirements, by which the VAT reporting date can be different from the Transaction date. Therefore, additional VAT features were added.



## **Additional dates for VAT reporting purposes** ##
-----

All VAT reporting for Slovenia, Croatia, and Serbia needs to be performed according to VAT date and not Transaction date (which is how standard functionality for Tax reporting works). For VAT reporting purposes following dates are added to several documents: 

* VAT date
* VAT Payable date
* Document Receipt date (used for defaulting VAT date)
<br/><br/>

VAT date and VAT Payable date (when populated) are transferred to a VAT date field (additional localized field) on Tax transaction as a result of document posting. This date is then used for VAT calculation and reporting.

List of documents where additional VAT date fields are enabled:

1.	_Pending Vendor Invoice_:  VAT date, VAT Payable date, Document Receipt date
2.	_Invoice Journal_:   VAT date, VAT Payable date, Document Receipt date
3.	_Free Text Invoice_:  VAT date
4.	_Sales Invoice_:  VAT date
5.	_Project Invoice_:  VAT date
6.	_Intercompany Invoice_:  VAT date
7.	_General Journal_:  VAT date, VAT Payable date
8.	_Collection letter_:  fee with sales tax
9.	_Interest letter_:  interests with sales tax


Additional setup is available for VAT date and VAT Payable date calculation. VAT date validation is also added. If the VAT date is missing, posting such a document will result in an error.

[Detailed documentation](/Help/Core-Localization/VAT/Additional-dates-for-VAT-reporting-purposes)

<!-- [Detailed documentation](https://adacta.sharepoint.com/:w:/r/sites/ERP-Product-Development/Shared%20Documents/D365FO%20Localization%20documentation/D365O%20LOC_VAT%20features.docx?d=w42e2c5023dca417b9b1c9c691af0e3bf&csf=1&e=91Mb4E) 
 -->

## **VAT Date change** ##
-----

VAT date can be manually changed on posted Sales tax transactions by using the function “Change VAT date”. VAT date is then changed on both - Tax transaction and Invoice journal. VAT date change for the period that is closed for posting is not possible and will result in an error.

[Detailed documentation](/Help/Core-Localization/VAT/VAT-date-change)


## **Reporting Tab on Tax transaction** ##
-----
As part of localization, an additional “Reporting” tab is added to Tax transactions. It displays information, such as Customer/Vendor, Address, Tax exempt number, Document, Document date and Document receipt date. This information is used on VAT reports. 

[Detailed documentation](/Help/Core-Localization/VAT/Reporting-Tab-on-Tax-transaction)

## **Informative VAT calculation** ##
-----

An option to calculate informative VAT is added. It is used in cases when VAT value is zero, but informative VAT value need to be calculated and later added to invoice printout or other documents.

[Detailed documentation](/Help/Core-Localization/VAT/Informative-VAT-calculation)

## **DDV-O (Obračun DDV) (Slovenia)** ##
-----

is a Slovenian sales tax return report. Every taxable person identified for VAT purposes in Slovenia is obliged to submit a VAT return to the Slovenian tax authority. DDV-O should include all the required VAT return settings, with the information needed to calculate the sales tax  and applicable deduction to be made including the total value of transactions relating to such tax and deductions. Additionally, the value of any exempt transactions should be included. Taxable entities have to submit the tax return to the tax authority by the last business day of the month, which follows  the expiry of the tax period, while Slovenian laws also allows multiple exceptions. VAT tax return (DDV-O) needs to be submitted electronically via the eDavki portal of the Slovenian tax authority (FURS).

DDV-O is prepared based on Tax transactions and according to VAT date. DDV-O can also be previewed (html) and exported to XML file.

[Detailed documentation](/Help/Core-Localization/Slovenian-Localization-Functionalities/DDV-O-\(Obračun-DDV\))

## **List of incoming (PR) and outgoing (IR) invoices (Slovenia)** ##
-----

A taxable person filing a VAT return (DDV-O) for the first time must attach a list of the incoming (PR) and outgoing (IR) invoices that served as the basis for preparing the VAT return. These two lists must also be available to be sent to the Slovenian tax authority if required directly by the authority and therefore need to be available to be extracted from the ERP.

IR and PR reports are prepared based on Tax transactions amd according to VAT date. Both reports can be exported to various format (e.g. Word, PDF or Excel). A special export in the format, required by the Slovenian tax authority (FURS) is also available for IR and PR. All reports are prepared using Slovenian sales tax reporting codes.

[Detailed documentation](/Help/Core-Localization/Slovenian-Localization-Functionalities/List-of-incoming-\(PR\)-and-outgoing-\(IR\)-invoices)

## **PDO (Poročilo o dobavah) (Slovenia)** ##
----- 

is a report required by the Slovenian tax authority regarding the supply of goods and services for which the recipient (and not the provider of goods or services) is a VAT payer according to the 76.a Article of the Slovenian sales tax law (ZDDV-1), where specific services for which this is applicable is also defined – e.g. construction work related services. Slovenian taxable persons, which perform these activities, must notice the Slovenian tax authority about their activities within 30 days of their occurrence. PDO report needs to be submitted electronically until the last day of the following month after deliveries of such goods or services occurred. Reporting is done through eDavki portal of the Slovenian tax authority (FURS).

PDO reports sums transactions based on tax exempt numbers. Report consists of A (information about the deliveries for current period) and B part (information about the corrections for previous periods). PDO report can be previewed (html) and exported as XML file, using the adequate model for reporting to the Slovenian tax authority (FURS) portal eDavki.

[Detailed documentation](/Help/Core-Localization/Slovenian-Localization-Functionalities/PDO-Report)

## **VIES (recapitulative report) (Slovenia)** ##
-----

 is a report in which taxable entities, identified for VAT purposes in Slovenia are obliged to report the supplies of goods and services that are delivered to entities, identified for VAT in the other Member States of the European Union during the reporting period (the calendar month). VIES report needs to be submitted to Slovenian tax authority (FURS) till the 20th in the following month after the occurrence of the reporting events.

VIES (recapitulative report) processes the transactions, considered as intra-community trade transactions based on the delivery address of the documents (Sales invoices, Free text invoices, Project invoices, Vendor invoices) if country code from that address is specified for the EU trade. Selected transactions are then transferred to EU sales list journal, if they meet the predetermined criterion. Additional localized information are available to be added to these transactions (e.g. Customs procedure 42 or 63). In contrary to the standard, localized feature reports transactions based on the VAT (and not transaction) date. VIES report can be exported either to Excel file (standard) or to an adequate XML file format (localization), accepted by the Slovenian tax authority (FURS) portal eDavki and previewed prior to export. After generating an EU Sales list report for a specific period, it is also possible to mark the records that are included in the report by setting the Reporting status value to Reported and Closed when for example tax authorities have accepted the report.

[Detailed documentation](/Help/Core-Localization/Slovenian-Localization-Functionalities/VIES-\(recapitulative-report\))
