## **Additional dates for VAT reporting purposes** ##
-----

For VAT reporting purposes following dates are added to several documents:

* VAT date
* VAT Payable date
* Document Receipt date
<br/><br/>

VAT date is also added to Tax transactions and is generated automatically when posting following documents with sales tax:

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



## **VAT Date change** ##
-----

VAT date can be manually changed on posted Sales tax transaction by using function “Change VAT date”. VAT date is then changed on both - Tax transaction and Invoice journal. VAT date change for the period that is closed for posting is not possible and will result in an error.
DETAILS: http://axweb/D365O%20Localization%20Documents/D365O%20LOC_VAT%20features.docx?Web=1






