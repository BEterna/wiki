# Hmport bank statement

This topic includes information about the bank statement transformations, used for mapping D365 fields with the information from bank statements. Transformations for the bank statement files, which are used by the majority of the local (Slovenian, Croatian, Serbian and North Macedonian) electronic banking systems are added in the scope of this extended localization feature.

The bank statement import process is part of standard Dynamics 365 for Operations solution, only transformations are part of localization. Transformations for following bank formats are part of this extended localization feature:
   - Slovenia – ISO 20022
   - Croatia – FINA
   - Serbia – Assecco (Pexim) and HalcomRS

After import, bank statements can be processed using standard D365 features.


## **Setup**
---

### Data management setup

#### Source data format

1. Open System administration – Workspaces – Data management – Configure data source.
2. It is necessary to create a new Source data format with regional settings for each of the Adriatic localizations (SI, HR, and RS). The setup below is shown for SI localization (the setup for remaining localizations is basically the same, the only difference is the Language locale value). 
3. After entering Source name and Description, the value “XML” should be chosen for cases when a bank statement is in XML format. XML Style should have value “Element”. In the Regional setting part, adequate language for the country is chosen together with an adequate time zone.
 
### Import parameters

1. Open System administration – Workspaces – Data management – Import.
2. Import parameters are set up here. Each localization needs its own setup.
3. After entering the name of the processing group, the Source data format (which was created above) should be chosen. 
4. Choose a sample file for upload. The file attached below is the same for all localizations.
5. After upload, entity mapping is automatically generated and data project is created. The next step is clicking the “View map” on the data project icon.
6. Form with entities is opened. Clicking “View map” on BankStatementDocumentEntity opens mapping visualization.
7. Transformation file(s) should be uploaded to the tab “Transformation”.
8. Clicking on “New” creates entry where transformation file(s) can be uploaded. Note: each format has its own transformation(s).
9. Transformations for the supported formats can be found on this link. Select an adequate XSLT file and confirm. In the case of more than one transformation file, the order of the transformations is very important.
10. After upload, transforms should be applied by clicking on “Apply transforms”. 
 
### Bank statement format

1. Open Cash and bank management – Setup – Advanced bank reconciliation – Bank statement format.
2. Bank statement format entry should be created for each format of the Adriatic localization countries. Supported formats: 
   - SI: ISO 20022
   - HR: FINA
   - RS: Assecco (Pexim), HalcomRS
3. After choosing the processing group (each format has its own processing group) checkmark in field “XML file” is set for those that receive bank statements in XML form. 
 
There is an additional column “Halcom RS” which is a specialty of Serbian bank statements import when Halcom format is used. Halcom_RS is special in a way that generates two files for one bank statement which is then imported in .zip file. For that purpose, Halcom_RS has a checkmark in the field “Halcom RS”.

### Bank account setup

Import is enabled only for bank accounts that have a checkmark in field “Advanced bank reconciliation”.
 
Once this option is enabled on a bank account it cannot be reversed (button turns inactive, grey). The optional setup is the definition of Statement format. 

## **Import**
---

1. Bank Statement is imported in Cash and Bank management – Bank statement reconciliation – Bank statements -> Import statement.

For Serbia, bank statement files should be zipped before import. 
 
2. Mandatory information at import is Statement format. Upon choosing the Bank account that has defined Statement format, the Statement format field is automatically populated. During import, the system will recognize bank account based on IBAN number if it is not defined in parameters.
3. After choosing the import file, it is necessary to upload it by clicking “Upload”. After that, the button “OK” is activated which triggers the import.
4. Bank Statement is imported when it is shown in the list of bank statements. Despite not defining the bank upon import, the system has recognized this statement to be from Unicredit bank (based on account number).
5. After import, the bank statement can be validated and reconciled. 

Check **[Test Scenario](Bank-statement-import.xlsx)** for Slovenian bank statement import.
 
