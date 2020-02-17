KRD stands for the SKV part of the report on short-term receivables and liabilities from doing business with non-residents according to the financial instruments specified by the Bank of Slovenia. Legal entities obliged by report are informed about the obligation by the Bank of Slovenian based on the importance of their business activities with the non-residents. If obliged to report, legal entities must submit the report until the 20th day in current month for the past month, electronically in an adequate XML format.
This localization feature enables the preparation and export of the report to the adequate localized XML file format. Report can be prepared for transactions within the specified period. Transactions are summed up by the ISO numeric code of each country and currency.


Setup 

Electronic reporting 

Workspaces – Electronic reporting à Reporting configurations 

 

Choose Exchange à Load XML file on any configuration. Based on file content it will automatically upload to correct configuration. 

 

Files for upload are attached below. Before upload, check the latest version of these files with developer. 

   

Click “Browse” and choose attached files (be sure to upload ERKRDKIPOModel.xml first because the format file is dependent on it). After the file has loaded, click OK to upload it to configuration. 

 

Search for configuration “KRD/KIPO” and expand it to find KRD report. Check for status “Completed” in tab Versions. 

 

General ledger parameters 

General ledger – Ledger setup – General ledger parameters 

Navigate to Adacta localization, tab Electronic reporting, and select KRD report in field “KRD electronic reporting format”. 

 

Country/region setup for KRD report 

Country/region code at partner’s address. 

 

ISO and numeric ISO country code in Organization administration – Global address book – Addresses – Address setup. 

 

Financial instruments for KRD report 

General ledger – Inquiries and reports – Slovenia – KRD report 

 

General ledger – Inquiries and reports – Slovenia – KRD report à Settings à Financial instruments 

Enter the list of financial instruments. The financial instrument "T" will be linked to the KRD groups in order to generate report in the (former) SKV range, while other financial instruments serve to manually add report lines. 

 

Groups 

General ledger – Inquiries and reports – Slovenia – KRD report à Settings à Groups 

Navigate to Action Pane, tab General, section Settings, and button Groups to set up groups.  

Enter group name and a description of the capital relationship between the debtor and the creditor. In the FI Code field, add the financial instrument "T", which allows the automatic transfer of relevant transactions to the report. As mentioned earlier, do not link other financial instruments with groups because they serve for manual creation of report lines. 

 

Enter Customer and Vednor criteria through buttons “Customer/Vendor criteria”.  

 

Sector codes 

General ledger – Inquiries and reports – Slovenia – KRD report à Settings à Sector codes 

Navigate to Action Pane, tab General, section Settings, and button Sector codes to define sectors. This table allows you to enter the sector code and its description, and below, allocate the code to the individual customer, vendor. 

 

It is possible to allocate sector code directly on Customer/Vendor card. 

 

Generate KRD report 

Create new reporting period. Select either date from the calendar lookup or enter “Period start” in form month.year. “Period end” value is automatically populated. Enter the date of preparing the report in the field “Date”.  

 

Some of the “Reporter” tab fields are automatically populated after creation of the period: Reporter (legal entity’s name); in the "Report prepared by" section, the details of the worker who created the report and his contact details are filled in (if they exist on the worker's card). 

 

Report is generated through button “Read transactions”. In the "Transactions" section, all transactions within the period are recorded, while in the "Sums, data for printout" section they are summed up according to the ISO numeric code of the country and currency. Through connection with the group, "FI code" is set to "T" for all totals. The final state of the previous report (column "Sum") is considered as the Opening balance of the report for the next month. 

 

It is possible to manually correct and update values in the “Sums” area fields. If you correct the data only in the report, but not at the source, the manually edited values will be reset each time the report is generated. 

 

It is also possible to manually add report lines (manually adding data for other financial instruments that are not included in automatic generation). Manually added line is automatically marked upon creation by a check mark in the field Manual, and will not be deleted when you re-generate the report. 

 

If fields "Principal other" or "Interest other" are populated, field “Note” must offer explanation for the entered amount.  

 

Validation if the Note exists for the value in fields Other is executed upon export to XML. 

 

 Navigate to “Export to XML file” to export report to XML form for Bank of Slovenia reporting. 

<!-- 
[Detailed documentation](https://adacta.sharepoint.com/:w:/r/sites/ERP-Product-Development/Shared%20Documents/D365FO%20Localization%20documentation/D365O%20LOC_SI%20Statistical%20reports.docx?d=w4c0af9b9e8dd42e7ac762e1d199fe4b3&csf=1&e=dyzs1o)
-->
