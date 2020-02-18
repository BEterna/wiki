# How To: Create eSettlement

In Slovenia, it is legally required (IV. Chapter of the ZPreZP-1) from debtors to report their overdue liabilities to vendors, with a goal to settle multilateral sett-offs. Reporting of the liabilities is done electronically via ePobot application of AJPES (Agency of the Republic of Slovenia for Public Legal Records and Related Services). Slovenian eSettlement offers a fast, safe, efficient and affordable way of settling the mutual liabilities between the legal entities, business entities registered in the Business Register of Slovenia (PRS). This system allows for monthly multilateral set-offs of reported mutual liabilities between legal entities, which can then be settled in the process.

This localisation feature (SI) allows users to set up, process and export the generated eSettlement (ePobot) files. Transactions to be included in eSettlement are prepared through vendor payment journal from where they can be exported in an adequate XML file, supported by the ePobot application. When results of the e-settlement are known the non-compensated transactions from vendor payment journal should be deleted, while customer entries with which vendors’’ transactions have been settled with should be entered before posting the journal.


This topic provides country/region-specific information about how to set up, create and process multilateral set-offs in scope of the Slovenian localisation.

1	Setup
1.1	Export format configuration
Workspaces – Electronic reporting  Reporting configurations
 
Choose Exchange  Load XML file on any configuration. Based on file content it will automatically upload to correct configuration.
 
Click “Browse” and choose ePobot (S).xml file attached below (before upload, check the latest version of this file with developer).
 
After the file has loaded, click OK to upload it to configuration.
 
Search for configuration “Payment model” and expand it to find ePobot (SI). Check for status “Completed” in tab Versions.
 
1.2	Method of payment
Create new payment method with Period “Invoice” and Payment type “Electronic payment”. Navigate to tab File formats and enable “Generic electronic reporting”. In field Export format configuration choose “ePobot (SI)”.
 
Navigate to Payment specification and create entries for mandatory and voluntary set-off. Export format is defined by payment specification parameters for each settlement type as shown below:
-	1 – mandatory set-off
-	2 – voluntary set-off of outstanding liabilities
-	3 – voluntary set-off of due liabilities
 
1.3	Mandatory set-off periods
Accounts payable – Payment setup – Mandatory set-off periods
Insert periods from Ajpes schedule in the form. 
 
1.4	Fictive back account
Cash and bank management – Bank accounts – Bank accounts
For the purposes of exporting entries for e-settlement create a fictive bank account “AJPES”. 
 
2	eSettlement
Accounts payable – Payments – Payment journal  Payment proposal  Create payment proposal for mandatory set-off
 
Automatic proposal of liabilities that have fallen due but have not been paid is enabled in Vendor payment journal. It is necessary to define mandatory set-off period in proposal. “From date” and “To date” fields are automatically transferred upon choosing period. Note: dates populated are shifted one day back (if period is defined 1.1.-31.1., dates populated are 31.12.-30.1.). “Total payment date” is also automatically transferred from mandatory set-off period (defined as Settlement date). 
 
Define smallest amount payable (250€). Additional filters can be entered in tab Records to include, if needed. In case of enabling “Change method of payment” choose Method of payment created for eSettlement and Payment specification that defines settlement round (1-mandatory, 2-voluntary of outstanding liabilities, 3-voluntary of due liabilities). Upon creating proposal, these data will accordingly change on transactions, included in proposal. 
 
Method of payment and Payment specification can also be subsequently changed using “Multiple change” functionality in proposal.
 
Before transferring payments to payment journal make sure to check if all transactions have Method of payment for e-settlement and adequate Payment specification (important for export format).
 
After confirming, transactions are transferred to payment journal lines.
 
ESettlement proposal is exported to file using standard functionality “Generate payments. Define payment method for e-settlement, file name, and bank account, created for settlement purposes.
 
After confirming parameters for payment generation, it is necessary to choose Mandatory set-off period. 
 
System displays Infolog about the file – define location to save the XML to. 
 
When the results of e-settlement are known, delete the transactions that have not been compensated from vendor payment journal. Enter customers’ entries which vendors’ transactions were settled with and post journal. 
3	Test case
 
