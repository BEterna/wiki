This section summarizes VAT features, developed in scope of the LOC_TAX extended localization packet.

-----

#Defaulting VAT date and VAT payable date

According to the local legislation, a taxable event occurs when goods/services are received/delivered or when goods are imported in case of goods from other EU countries, while multiple exceptions exist. Hence, the obligation to report the calculated VAT occurs with the taxable event. By standard D365O posts tax transactions on the transaction posting date, which is not in line with the local legal requirements. Therefore, to post, settle and report VAT according to the local legal requirements, additional VAT date (VAT date, VAT Payable date and Document receipt date) fields were added to sales and purchase documents from where they are transferred to tax transactions.

In scope of this extended localization functionality, in order to facilitate the posting, there is a possibility to set up VAT date and VAT payable date defaulting. Options for defaulting are:
-	None: VAT date has to be entered manually
-	Posting date: VAT date defaults from posting date (field “Date” in journals and FTI, “Invoice date” on Sales invoice)
-	Document date: field “Invoice date” on vendor invoice
-	Document receipt date: applicable only for inbound documents

This additional setup for defaulting VAT dates exists in the parameters of the following modules: General ledger, Accounts Payable and Accounts Receivable.

[Detailed documentation](http://axweb/D365O%20Localization%20Documents/D365O%20LOC_VAT%20features.docx?Web=1) (chapter 1.1)

-----

#Import of Slovenian taxable persons (SI)