# Import bank statement

This topic includes information about the bank statement transformations, used for mapping D365 fields with the information from bank statements. Transformations for following bank statement formats are added as part of this package: 

   - Slovenia – ISO 20022 (HalcomSI)
   - Croatia – FINA
   - Serbia – Assecco (Pexim) and HalcomRS

After import, bank statements can be processed using standard D365 bank reconciliation feature or additional bank statement processing features that this package is offering.


## **Setup**
---

### **Data management setup**

#### Create Source data format

<br>Open System administration > Workspaces > Data management > Configure data source.

It is necessary to create a new Source data format. Setup depends on the type of import file. 

Example of XML file import setup:  

|**Source name**| **Operations** | 
|--|--|
|**Source name** |XML-Element  |
|**Description**  |XML Element  |
|**Type**  |File  |
|**Default dextension**  |XML  |
|**File format**  |XML |
|**XML style**  |Element  |
|**Root document**  |Document  |
|**Language locale**  |*pick local language that you want to use  |
|**Time zone preference**  | Company or Manual |


 
#### Import parameters

Open System administration > Workspaces > Data management > Import

Generate separate import group for Each bank format. 
1. **Create new import project** and name it the way that it will give enough information about the content  (e.g. BankStatementImport_SI) 



1. In the Selected entities Area **add new entity** (New File):

|Field| Value |
|--|--|
|**Entity name**  | Bank statements |
| **Source data format** |Choose one of data sources, generated in the previous step e.g. XML-Element |
|**Use sample file**  |Yes  |
|**Default refresh type**  | Any of two options |
|**Upload data file**  | upload SampleBankCompositeEntity sample file located in AOT resources |

file sample: [**SampleBankCompositeEntity.xml**](/.attachments/SampleBankCompositeEntity-33b781da-249e-4e72-8896-9fe62b83ea6d.xml)

![image.png](/.attachments/image-b253b583-0da5-4da6-a950-4522f5efad9f.png)

3. To **apply xslt transformations**, go to line that you created in previous step > View map > Choose correct entity > View map > Transformations Tab > New. XSLT files are specific for each bank/file format. Select an adequate XSLT file and confirm. In the case of more than one transformation file, the order of the transformations is very important. After upload, transformations should be applied by clicking on “Apply transforms”.


| **Format** | **Transformation** |
|--|--|
|**Halcom**  |Halcom_SI.xslt  | 
|**FINA**  | 1. FINA_TxtToXML_HR.xslt <br>2. FINA_XMLToRecon_HR.xslt | 
|**Asecco (Pexim)**  | Asseco_RS.xslt |
|**HalcomRS**  | 1. Halcom_TxtToXML_RS.xslt <br>2. Halcom_XMLToRecon_RS.xslt |




Transformations for the supported formats can be found on [this link](https://ad365o.visualstudio.com/AdSuite/_versionControl?path=%24%2FAdSuite%2FBankStatements%2FMain%2F10%2FMetadata%2FAdactaSuiteBankStatements%2FAdactaSuiteBankStatements%2FAxResource%2FResourceContent%2FData). 
 
 
### **Bank statement format**

Open Cash and bank management > Setup > Advanced bank reconciliation > Bank statement format.

Enter all bank statement formats that will be used in the bank statement processing. Formats added by this package are listed at the beginning of this chapter. 


|**Field**|**Value**  |
|--|--|
|**Statement format**  |Name of the statement format e.g. HalcomSI |
|**Name** |Description of the format  |
|**Processing group**  |Choose one of the processing groups generated  in previous steps. Each statement format has its own processing group e.g. BankStatementImport_SI |
|**XML file**  |  |
|**File type**  |  |
|**Generic electronic import format**  |  |
| **Import format configuration** |  |


  
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
 
