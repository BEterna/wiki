This topic includes information about the bank statement transformations, used for mapping D365 fields with the information from bank statements. Transformations for the bank statement files, which are used by the majority of the local (Slovenian, Croatian, Serbian and North Macedonian) electronic banking system are added in scope of this extended localization feature.

Bank statement import process is part of standard Dynamics 365 for Operations solution, only transformations are part of localization. Transformations for following bank formats are part of this extended localization feature:

-	Slovenia – ISO 20022
-	Croatia – FINA
-	Serbia – Assecco (Pexim) and HalcomRS

After import, bank statements can be processed using standard D365 features.

[Detailed documentation](https://adacta.sharepoint.com/:w:/r/sites/ERP-Product-Development/Shared%20Documents/D365FO%20Localization%20documentation/D365%20ext%20LOC_Bank%20Statement%20Import.docx?d=w85dc8c93d1ee4bef85b868ed853a3eee&csf=1&e=QYHl62)

1	General
Bank statement import process is part of standard Dynamics 365 for Operations solution, only transformations are part of localization. Transformations for following bank formats are part of localization pack: 
1.	SI: ISO 20022
2.	HR: FINA
3.	RS: Assecco (Pexim), HalcomRS
2	Setup
2.1	Data management setup
2.1.1	Source data format
System administration – Workspaces – Data management – Configure data source 
 
It is necessary to create new Source data format with regional settings for each of the Adriatic localizations (SI, HR, and RS). Setup below is shown for SI localization (the setup for remaining localizations is basically the same, the only difference is the Language locale value). 
 
After entering Source name and Description, value “XML” should be chosen for cases when bank statement is in XML format. XML Style should have value “Element”. In Regional setting part, the adequate language for the country is chosen together with adequate time zone.
 
2.1.2	Import parameters
System administration – Workspaces – Data management – Import 
Import parameters are set up here. Each localization needs its own setup.
 
After entering name of the processing group, Source data format (which was created above) should be chosen. 
 
Choose sample file for upload. File attached below is the same for all localizations.
 
 
After upload, entity mapping is automatically generated and data project is created. Next step is clicking “View map” on data project icon.
 
Form with entities is opened. Clicking “View map” on BankStatementDocumentEntity opens mapping visualization.
 
Transformation file(s) should be uploaded to tab “Transformation”.
 
Clicking on “New” creates entry where transformation file(s) can be uploaded. Note: each format has its own transformation(s).
 
Transformations for the supported formats can be found on this link. Select adequate XSLT file and confirm.
 
In case of more than one transformation files, the order of the transformations is very important.
 
After upload, transforms should be applied by clicking on “Apply transforms”. 
 
2.2	Bank statement format
Cash and bank management – Setup – Advanced bank reconciliation – Bank statement format
Bank statement format entry should be created for each format of the Adriatic localization countries. 
Supported formats: 
1.	SI: ISO 20022
2.	HR: FINA
3.	RS: Assecco (Pexim), HalcomRS
 
After choosing processing group (each format has its own processing group) checkmark in field “XML file” is set for those that receive bank statements in XML form. 
 
There is additional column “Halcom RS” which is a specialty of Serbian bank statements import when Halcom format is used. Halcom_RS is special in a way that generates two files for one bank statement which is then imported in .zip file. For that purpose, Halcom_RS has a checkmark in field “Halcom RS”.
2.3	Bank account setup
Import is enabled only for bank accounts that have checkmark in field “Advanced bank reconciliation”.
 
Once this option is enabled on bank account it cannot be reversed (button turns inactive, grey). Optional setup is definition of Statement format. 
3	Import
Bank Statement is imported in Cash and Bank management – Bank statement reconciliation – Bank statements  Import statement.
For Serbia, bank statement files should be zipped before import. 


 
Mandatory information at import is Statement format. Upon choosing Bank account that has defined Statement format, Statement format field is automatically populated. During import, system will recognize bank account based on IBAN number if it is not defined in parameters.
After choosing the import file, it is necessary to upload it by clicking “Upload”. After that, button “OK” is activated which triggers the import.
 
Bank Statement is imported when it is shown in the list of bank statements. Despite not defining the bank upon import, system has recognized this statement to be from Unicredit bank (based on account number).
 
After import, bank statement can be validated and reconciled. 
4	Test case: Slovenian bank statement import
 
