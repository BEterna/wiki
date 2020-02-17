# How To: Prepare PDO report

PDO report is a report required by the Slovenian tax authority regarding the supply of goods and services for which the recipient (and not the provider of goods or services) is a VAT payer according to the 76.a Article of the Slovenian sales tax law (ZDDV-1), where specific services for which this is applicable is also defined – e.g. construction work related services. Slovenian taxable persons, which perform these activities, must notice the Slovenian tax authority about their activities within 30 days of their occurrence. PDO report needs to be submitted electronically until the last day of the following month after deliveries of such goods or services occurred. Reporting is done through eDavki portal of the Slovenian tax authority (FURS).

PDO reports sums transactions based on tax exempt numbers. Report consists of A (information about the deliveries for current period) and B part (information about the corrections for previous periods). PDO report can be previewed (html) and exported as XML file, using the adequate model for reporting to the Slovenian tax authority (FURS) portal eDavki.

PDO report 

Setup  

Export format configuration 

Workspaces – Electronic reporting à Reporting configurations 

Choose Exchange à Load XML file on any configuration. Based on file content it will automatically upload to correct configuration. 

Files for upload are attached below. Before upload, check the latest version of these files with developer.  

Click “Browse” and choose attached files (be sure to upload model first (PDO.xml file) because the format is dependent on it). After the file has loaded, click OK to upload it to configuration. 

Search for configuration “PDO” and expand it to find PDO format. Check for status “Completed” in tab Versions. 

General ledger parameters 

General ledger – Ledger setup – General ledger parameters 

To define export format navigate to Adacta localization and section Electronic reporting. Select “PDOXmlFormat” in field “PDO electronic reporting format". 

Sales tax code 

Tax – Indirect taxes – Sales tax – Sales tax codes 

Sales, liable under article 76a of ZDDV-1, need to be monthly reported in PD-O report. Define which sales are reported on sales tax code by enabling field “Include in PDO”.  

PDO report 

Tax – Declarations – Slovenia – VAT – PDO report 

Using button “New” new reporting period is created where it is necessary to choose reporting Month and define Year. 

Click the button “Prepare transactions for PD-O report” to transfer transactions to tab Current period transactions. Transactions are summed by Tax exempt number. 

Check tab Transactions for detailed information about summed transactions. Click on voucher number to open invoice journal. 




