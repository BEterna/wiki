This topic provides country/region-specific information about the localized VAT features, developed with a purpose to comply with the local legislation and tax authorities of Slovenia, Croatia, Serbia and Northern Macedonia. According to the adequate local legislation (e.g. ZDDV-1 in case of Slovenia), a taxable event occurs when goods/services are received/delivered or when goods are imported in case of goods from other EU countries, while multiple exceptions exist. 

As part of standard D365FO tax transactions are posted and reported according to transaction posting date, which is not aligned with the local legal requirements, by which VAT reporting date can be different from Transaction date. Therefore, additional VAT features were added.



## **Additional dates for VAT reporting purposes** ##
-----

All VAT reporting for Slovenia, Croatia and Serbia needs to be performed according to VAT date and not Transaction date (which is how standard functionality for Tax reporting works). For VAT reporting purposes following dates are added to several documents: 

* VAT date
* VAT Payable date
* Document Receipt date (used for defaulting VAT date)
<br/><br/>

VAT date and VAT Payable date (when populated) are transferred to VAT date field (additional localized field) on Tax transaction as result of document posting. This date is then used for VAT calculation and reporting.

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


Additional setup is available for VAT date and VAT Payable date calculation. VAT date validation is also added. If VAT date is missing, posting of such document will result in error.

[Detailed documentation](https://adacta.sharepoint.com/:w:/r/sites/ERP-Product-Development/Shared%20Documents/D365FO%20Localization%20documentation/D365O%20LOC_VAT%20features.docx?d=w42e2c5023dca417b9b1c9c691af0e3bf&csf=1&e=91Mb4E)
## **VAT Date change** ##
-----

VAT date can be manually changed on posted Sales tax transaction by using function “Change VAT date”. VAT date is then changed on both - Tax transaction and Invoice journal. VAT date change for the period that is closed for posting is not possible and will result in an error.

[Detailed documentation](https://adacta.sharepoint.com/:w:/r/sites/ERP-Product-Development/Shared%20Documents/D365FO%20Localization%20documentation/D365O%20LOC_VAT%20features.docx?d=w42e2c5023dca417b9b1c9c691af0e3bf&csf=1&e=91Mb4E)


## **Reporting Tab on Tax transaction** ##
-----
As part of localization, additional “Reporting” tab is added to Tax transactions. It displays information, such as Customer/Vendor, Address, Tax exempt number, Document, Document date and Document receipt date. This information is used on VAT reports. 

[Detailed documentation](https://adacta.sharepoint.com/:w:/r/sites/ERP-Product-Development/Shared%20Documents/D365FO%20Localization%20documentation/D365O%20LOC_VAT%20features.docx?d=w42e2c5023dca417b9b1c9c691af0e3bf&csf=1&e=91Mb4E)

## **Informative VAT calculation** ##
-----

An option to calculate informative VAT is added. It is used in cases when VAT value is zero, but informative VAT value need to be calculated and later added to invoice printout or other documents.

[Detailed documentation](https://adacta.sharepoint.com/:w:/r/sites/ERP-Product-Development/Shared%20Documents/D365FO%20Localization%20documentation/D365O%20LOC_VAT%20features.docx?d=w42e2c5023dca417b9b1c9c691af0e3bf&csf=1&e=91Mb4E)
