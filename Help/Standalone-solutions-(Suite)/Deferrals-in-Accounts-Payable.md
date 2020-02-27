# How To: Post Defferals in Accounts Payable

Deferrals refer to expenses or revenues, which are not recognized immediately on the income statement. Instead, they need to be deferred to a balance sheet account and appear later on the income statement.

In contrast to standard D365O functionality, this feature enables deferrals to be created directly from Vendor invoices or Vendor invoice journals by applying the pre-set deferral scheme to each invoice line. It is possible to overview posted and non-posted deferrals (on different list pages) and post them manually (by marking selected deferral lines to be posted), manually collectively (by defining date frame for deferrals to be posted)) or automatically (via batch processing).

This custom feature is part of the AdactaSuiteDeferrals AdSuite D365O extension packet.

1	Setup
1.1	Deferral schemes
Accounts payable > Setup > Deferrals > Deferral schemes
Multiple deferral schemes with separate rules can be defined: 
Calendar type: Determines which calendar is used for deferrals. Fiscal, Calendar and Allocation key can be used in case of Fiscal and Calendar amounts are allocated evenly and in case of Allocation key amounts are allocated according to rules defined in Period allocation lines. This means that different portion of amount can be allocated to each period. 
Period frequency: Determines period as Monthly, Quarterly, Half-yearly or Yearly. In case of Monthly Deferrals are generated on monthly basis. 
Length: Number of periods, defined in Period frequency. If amount is supposed to be deferred in 6 months, Period frequency should be set to Monthly and Length to 6. 
Start deferrals on invoice date: If set to Yes, it determines that the first deferral will be posted on the date of the invoice. This can be used in cases when vendor invoice is issued in the middle of the year the cost refers to whole year. All amount that should be deferred into periods before invoice date will be summed on the invoice date. 
Period key: is enabled only if type Allocation key is defined in Calendar type. It defines allocation key for deferrals.
Posting frequency: Determines frequency of the deferral posting within the period. 
Value posting: Determines how the amount should be deferred. In case of Even amount will be divided into even parts and in case of Scale it will be weighed against the number of days in period. 
Posting date: Defines when in the period transaction should be posted – Beginning, End or middle. 
 
1.2	Number sequences
Organization administration > Number sequences > Number sequences
Two number sequences in Area Deferrals: 
•	Deferral voucher
•	Deferral ID
1.3	Allow deferrals with project
Accounts payable > Setup > Accounts payable parameters
Select to enable or disable deferrals on invoice lines linked to project. 
 
If “Allow deferrals with project” is enabled, it is possible to select deferral scheme on vendor invoice line with project ID. In this case, deferrals are not generated for project transactions.
When this setup is not enabled, it is not possible to select deferrals on vendor invoice line with project ID. 
1.4	Posting definitions
General ledger > Posting Setup > Posting definitions
Setup needs to be done in posting definitions (even if posting definitions are not enabled for other transactions). 
 
1.5	Budget control
Budgeting > Setup > Budget control > Budget control configuration
Deferrals can also be subject of budget control process. Budget control will be performed if Expense deferral option in Document and journals is marked. Option Check at line entry is disabled and cannot be enabled.
 
2	Generate deferrals
Accounts payable > Invoices > Pending Vendor Invoices
Line detail Deferral is added to Pending vendor invoice line. 
 
Every Vendor invoice line can be deferred separately, even using different Deferral scheme. Depending on chosen deferral scheme, Deferral lines are generated. Default Deferral date depends on the setup defined on Deferral scheme. Posting date of the first deferral line is the same as the Invoice posting date. All other deferral lines get posting date from Ledger posting setup on Deferral schemes. In this case Start date can be blank.
If deferrals refer to previous periods (e.g. Invoice received in March, but it refers to whole year), Start date needs to be entered somewhere in the past. In this case Deferrals will be generated for current and future periods, and all deferrals that should be posted in previous periods will be summed in current period. This amount will be posted to cost account all other deferral lines will be posted deferrals account. This is only valid for deferral schemes with Start deferral on invoice date set to Yes. 
 
When the invoice is posted, lines get posted to cost accounts and at the same time correction transaction is created to move the amounts from cost to deferral account. Posting definitions are used in this process. 
It is possible to subsequently generate deferrals for invoice lines that have already been posted. In Invoice journal select desired transaction, navigate to tab Lines, and select the line for deferrals.
 
If “Allow deferrals with project” is disabled in the parameters, it is not possible to select deferrals on vendor invoice line with project ID. 
 
It is also not possible to create deferrals in invoice journal on vendor invoice line with project ID. 
 
3	Deferrals posting
Accounts payable > Inquiries and reports > Deferrals > Deferrals
Accounts payable > Inquiries and reports > Deferrals > Unposted deferrals
Accounts payable > Inquiries and reports > Deferrals > Posted deferrals
Accounts payable > Inquiries and reports > Deferrals > Deferral lines
After posting Vendor invoice with deferral lines, voucher is generated (cost > deferral). It can be accessed using Voucher transactions option in Deferral tab. 
  
All invoice lines, posted to Deferrals, are listed in Deferrals list. Posted and unposted deferrals can be viewed in separate list pages (Posted/Unposted deferrals). In Posted deferrals list are listed only deferrals that are completely transferred from deferrals to costs. All the others are listed in Unposted deferrals list.
 
All the existing deferral lines are displayed. It is possible to filter between Posted/Not posted/All deferral lines.
 
Posting from deferrals to cost account can be performed manually or automatically. 
3.1	Manual posting
For manual posting go to deferrals list, open one deferral and then go to Lines. Mark the line and click Post. Deferral voucher will be generated. 
 
Functions as View distributions, Subledger journal, Voucher transactions, Budget checking are available for each deferral line. 
Deferrals can also be manually posted from Accounts payable > Inquiries and reports > Deferrals > Deferral lines form by choosing a specific deferral (line) and clicking “Post” button. From the same form it is also possible to: View distributions, Subledger journal, Voucher transactions and perform Budget checking for each deferral line.
3.2	Manual mass posting
Accounts payable > Periodic tasks > Deferrals > Post deferrals
Mass posting of deferrals can be performed. 
 

Date period needs to be defined. All deferrals that have posting date in defined interval, will be posted. 
3.3	Automatic posting
Accounts payable > Periodic tasks > Deferrals > Post deferrals
Deferrals can be posted automatically if batch processing is defined. 
 

3.4	Budget check 
Deferrals can be included in a budget check (if enabled in Buget check parameters). In this case budget is reserved at the moment of generating invoice (standard) and reversed at the moment of posting invoice. When posting deferrals (Deferrals > Expense account) budget in posted in the correct period. 

Scenario: 

•	Generate Purchase order with Kreiran nabavni> Budget reservation is created in Encumbrances section with the amount 1.750€
•	Generate Vendor invoice from Purchase order > Budget reservation from the Purchase order is released. Budget reservation in section Actual expenditures is generated with the amount 1.750€ 
•	Generate Deferrals for specific Vendor invoice line > Post Invoice > Budget in Actual expenditures is released (negative line with original amount is generated) 
•	Post Deferrals (deferrals > Expense) > Budget reservation is generated in Actual expenditures section in the correct period. 
