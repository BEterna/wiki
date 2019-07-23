This topic provides country/region-specific information about the localized VAT features, developed with a purpose to comply with the local legislation and tax authorities of Slovenia, Croatia, Serbia and Northern Macedonia. According to the adequate local legislation (e.g. ZDDV-1 in case of Slovenia), a taxable event occurs when goods/services are received/delivered or when goods are imported in case of goods from other EU countries, while multiple exceptions exist. 

As part of standard D365FO tax transactions are posted and reported according to transaction posting date, which is not aligned with the local legal requirements, by which VAT reporting date can be different from Transaction date. Therefore, additional VAT features were added.



## **Additional dates for VAT reporting purposes** ##
-----

All VAT reporting for Slovenia, Croatia and Serbia needs to be performed according to VAT date and not Transaction date (which is how standard functionality for Tax reporting works). For VAT reporting purposes following dates are added to several documents: 

* VAT date
* VAT Payable date
* Document Receipt date (used for defaulting VAT date)
<br/><br/>

VAT date and VAT Payable date (when populated) are transferred to VAT date field (additional localized field) on Tax transaction as result of document posting. 

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

[Detailed documentation](http://axweb/D365O%20Localization%20Documents/D365O%20LOC_VAT%20features.docx?Web=1)

## **VAT Date change** ##
-----

VAT date can be manually changed on posted Sales tax transaction by using function “Change VAT date”. VAT date is then changed on both - Tax transaction and Invoice journal. VAT date change for the period that is closed for posting is not possible and will result in an error.

[Detailed documentation](http://axweb/D365O%20Localization%20Documents/D365O%20LOC_VAT%20features.docx?Web=1)

## **Postponed VAT on Sales Credit Memo (HR, RS)** ##
-----

Localization functionality allows posting Sales credit memos without VAT date in order be compliant with Croatian and Serbian legislation. If the feature is enabled, VAT date on tax transaction is left empty, and these documents are not included in any VAT reports. Later, when Credit note is confirmed by Customer, VAT date can be added manually, directly to Tax transaction, using VAT date change feature. 

[Detailed documentation](http://axweb/D365O%20Localization%20Documents/D365O%20LOC_HR_Postponed%20VAT%20on%20Sales%20credit%20memo.docx?Web=1)


## **Informative VAT calculation** ##
-----

An option to calculate informative VAT is added. It is used in cases when VAT value is zero, but informative VAT value need to be calculated and later added to invoice printout or other documents.


## **Taxable persons list** ##
-----

A taxable persons list is added in scope of Slovenian and Croatian localization. Slovenian lists stores information, such as: tax registration number, company registration number, taxable person type, name, address and special handling (e.g. 76.a ZDDV-1) checkmark, while Croatian lists stores the following information: OIB, identification number, type and name.

