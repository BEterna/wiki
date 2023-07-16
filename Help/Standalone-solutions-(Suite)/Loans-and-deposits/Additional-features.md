#Multiple flows posting

User can post more calculated flows at once, using Multiple flows posting form. 

The form is accessed via menu item: **_Loan and deposit management > Periodic > Loans > Multiple flows posting_**. When form is opened, user should make selection of flows to be posted. 

The selection is made using fields:
- Flow date from, 
- Flow date to and 
- Loan group. 

After data is entered, user should click Update. User can shorten the shown list by selecting some flows and removing them (button Remove) or using filters within list’s columns. Before the process of posting is started, user should confirm list of flows to be posted by selection of flows in the shown list. When flows are selected, user should click button Post. In the pop-up window with information of number of flows to be posted, user should confirm the start of posting (button Yes).


#Invoicing of flows via Free text invoice

Some companies prefer to send invoices for interest for given loans. In order to use this functionality some additional setup is needed for invoicing categories. Setup is available via menu item **_Loan and deposit management > Setup > Invoicing > Invoicing categories_**

|      Field | Description|
|:----------------|:-------------|
|Invoicing category | Code for invoice category.
|Description  |Short description for the invoice category.
|Billing classification reference ID |If you setup Billing classification it will be used for invoicing. This is optional, however it should be setup if company sets billing classification as mandatory.
|Item sales tax group | Will determine what kind of tax should be calculated on invoice line.
|Invoice text |Text that will be set on invoice line.
 
Second part of setup is in menu item: **_Loan and deposit management > Setup > Loans > Flow categories_**, where for the Offset account type Customer invoice must be selected and Invoicing Category needed for billing.

After the flows are calculated, user can create interest invoices via menu item **_Loan and deposit management > Periodic > Loans > Create invoices - credit lines_**. This will create Free text invoices, which can be posted as any other FTI.

Note:
When preparing invoices kindly note that Accounts receivable default posting profile is used, setup in **_Accounts receivable > Setup > Accounts receivables parameters_** (Ledger and sales tax, Posting profile).