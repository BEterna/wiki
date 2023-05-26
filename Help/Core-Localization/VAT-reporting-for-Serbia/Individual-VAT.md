This topic provides country/region-specific information about setting up, creating, and exporting data for Individual VAT reporting to comply with Serbian legislation. Individual VAT reporting data can be generated for the following document types:
- Vendor invoice (only for Individual VAT)

Supported providers:
- RS: Ministry of Finance eFaktura

#**Setup**
________________________________________
**Export format configuration**

Configuration for export of individual VAT is available. In the case of standard changes, the configuration needs to be adjusted.
1.	Open ****Workspaces** > Electronic reporting > Reporting configurations**.
2.	Choose Exchange > Load XML file on any configuration. Based on file content, it will automatically upload to the correct configuration.
3.	Search for the “Individual VAT” configuration and import the last configuration. Then import the remaining configuration:
- Individual VAT Format (JSON)

**General ledger parameters**
1.	Open General ledger > Ledger setup > General ledger parameters
2.	Under the Be-terna localization tab in the Electronic reporting/Individual VAT electronic reporting dropdown manu, choose the imported ER configuration.
3.	Under the Be-terna localization tab in the VAT payment (RS)/Individual VAT report API URL fill in the website to the eFakture portal API and under Individual VAT report API Key enter the API key for your company from the eFaktura portal.

**VAT category**
1.	Open **Tax > Indirect taxes > Sales tax > Sales tax codes**.
2.	Select Sales tax code and under tab Be-terna localization/INDIVIDUAL VAT REPORT/Individual VAT report column, choose the appropriate percentage (20% or 10%)

#**Individual VAT registry**
________________________________________
**Creation of the documents for the Individual VAT report**
1.	Open Tax > Declaration > Serbia > VAT > Process data for Individual VAT reporting
2.	In the filter, use the From date to reference the transaction transfer's beginning date. If you want to repeat the transfer of existing records, toggle “Overwrite existing records” to Yes.
NOTE: The process data in the batch is possible if there are many transactions by toggling “Batch processing” to Yes.
3.	Open Tax > Declaration > Serbia > VAT > Individual VAT Report to see all the transferred documents.
4.	New documents will have the status “New”. The transfer files should be created using the “Create messages” function from the main ribbon, and in the filter, use the From date to reference the transaction transfer's beginning date.
5.	Afterward, the document’s status will change to “Created”. In the “Details” tab, all relevant data and the JSON file can be checked.
6.	The final step for transferring the documents into the eFaktura portal is to select the “Transfer prepared messages” function from the main ribbon, and in the filter, use the From date to reference the transaction transfer's beginning date.
7.	If there is any error during the file transfer to the eFaktura portal, the column “Last error message” will be filled, and the status will be changed to “Error”.
The status should be changed manually using the “Reset status” function from the main ribbon to be able to re-create the file for transfer.
8.	If successfully sent to the eFaktura portal, documents will change status to “Transferred”.
9.	If there is a large number of transactions after years of using D365FO, it is possible to delete lines from the list using the “Cleanup old records” function from the main ribbon, and in the filter, use the From date to reference the transaction transfer's beginning date.
