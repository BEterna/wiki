This topic provides country/region-specific information about how to set up and create the sales tax declaration for legal entities in Slovenia only. In order to comply with the Slovenian legislation, adequate reports regarding the sales tax need are for Slovenia in terms of this localization feature and are further described below.

Sales tax reporting codes for Slovenia are added as par of Slovenian report Layout and used for reports listed below.

## **DDV-O (Obračun DDV)** ##
-----


is a Slovenian sales tax return report. Every taxable person identified for VAT purposes in Slovenia is obliged to submit a VAT return to the Slovenian tax authority. DDV-O should include all the required VAT return settings, with the information needed to calculate the sales tax  and applicable deduction to be made including the total value of transactions relating to such tax and deductions. Additionally, the value of any exempt transactions should be included. Taxable entities have to submit the tax return to the tax authority by the last business day of the month, which follows  the expiry of the tax period, while Slovenian laws also allows multiple exceptions. VAT tax return (DDV-O) needs to be submitted electronically via the eDavki portal of the Slovenian tax authority (FURS).

DDV-O is prepared based on Tax transactions and according to VAT date. DDV-O can also be previewed (html) and exported to XML file



## **List of incoming (PR) and outgoing (IR) invoices** ##
-----

A taxable person filing a VAT return (DDV-O) for the first time must attach a list of the incoming (PR) and outgoing (IR) invoices that served as the basis for preparing the VAT return. These two lists must also be available to be sent to the Slovenian tax authority if required directly by the authority and therefore need to be available to be extracted from the ERP.

IR and PR reports are prepared based on Tax transactions amd according to VAT date. Both reports can be exported to various format (e.g. Word, PDF or Excel). A special export in the format, required by the Slovenian tax authority (FURS) is also available for IR and PR. All reports are prepared using Slovenian sales tax reporting codes.


## **PDO (Poročilo o dobavah)** ##
----- 

is a report required by the Slovenian tax authority regarding the supply of goods and services for which the recipient (and not the provider of goods or services) is a VAT payer according to the 76.a Article of the Slovenian sales tax law (ZDDV-1), where specific services for which this is applicable is also defined – e.g. construction work related services. Slovenian taxable persons, which perform these activities, must notice the Slovenian tax authority about their activities within 30 days of their occurrence. PDO report needs to be submitted electronically until the last day of the following month after deliveries of such goods or services occurred. Reporting is done through eDavki portal of the Slovenian tax authority (FURS).

PDO reports sums transactions based on tax exempt numbers. Report consists of A (information about the deliveries for current period) and B part (information about the corrections for previous periods). PDO report can be previewed (html) and exported as XML file, using the adequate model for reporting to the Slovenian tax authority (FURS) portal eDavki.


## **VIES (recapitulative report)** ##
-----

 is a report in which taxable entities, identified for VAT purposes in Slovenia are obliged to report the supplies of goods and services that are delivered to entities, identified for VAT in the other Member States of the European Union during the reporting period (the calendar month). VIES report needs to be submitted to Slovenian tax authority (FURS) till the 20th in the following month after the occurrence of the reporting events.

VIES (recapitulative report) processes the transactions, considered as intra-community trade transactions based on the delivery address of the documents (Sales invoices, Free text invoices, Project invoices, Vendor invoices) if country code from that address is specified for the EU trade. Selected transactions are then transferred to EU sales list journal, if they meet the predetermined criterion. Additional localized information are available to be added to these transactions (e.g. Customs procedure 42 or 63). In contrary to the standard, localized feature reports transactions based on the VAT (and not transaction) date. VIES report can be exported either to Excel file (standard) or to an adequate XML file format (localization), accepted by the Slovenian tax authority (FURS) portal eDavki and previewed prior to export. After generating an EU Sales list report for a specific period, it is also possible to mark the records that are included in the report by setting the Reporting status value to Reported and Closed when for example tax authorities have accepted the report.


[Detailed documentation](http://axweb/D365O%20Localization%20Documents/D365O%20LOC_SI%20VAT%20Reports%20SI%20docx.docx?Web=1)
	
