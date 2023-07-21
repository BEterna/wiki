


#**Number sequences**
Number sequences to be used within Loan and deposit management module are defined in the section: **_Loan and deposit management > Setup > Loan and deposit parameters > Number sequences_**.
Number sequences should be assigned to:
-	Treasury partner;
-	Loan – received or given loan;
-	Credit line flow voucher – flow posting voucher.


#**Loan groups**

The groups of loans should be formed according to the number of account combinations for posting of loan receivables, liabilities, revenue, and expenses.
Groups are defined in: **_Loan and deposit management > Setup > Loans > Loan groups_**. The following data is entered:

|      Field | Description|
|:----------------|:-------------|
|Loan group |group name. It is recommended to create self-explanatory codes, e.g. for received long-term loans in USD, we could name loan group: RL_LT_USD.
|Description  |more detailed description of the loan group.
|Credit line type |- Borrowing – used for received loans and deposits. <br>- Investment – used for given loans and deposits.|
| Default drawing category |Flow category (loan transaction type: Drawing) that will be set as flow category when Default drawing action is created (described in more details within section: Default drawing).

#**Flow categories**

With flow categories we set up posting rules for received and given loans (deposits). Flow categories are defined in: **_Loan and deposit management > Setup > Loans > Flow categories_**. Flow categories for accruals/defferals are specified at the end of this chapter. 

1. The **following data** is entered:

|      Field | Description|
|:----------------|:-------------| 
|Category |Category name (unique identifier). This code should also be self-explanatory, e.g. RL_DRAW for drawing of received loans.
|Loan transaction type |Loan transaction type for which posting rules are defined. <br>The following types are available:<br>- Drawing;<br>- Repayment; <br>- Interest; <br>- Fee – usually used for one-off fees, e.g. loan processing fees.
|Description | More detailed description of the flow category.

2. **General fast-tab**
General fast-tab contains following data:

|      Field |Description|
|:----------------|:-------------|
|Principal  |Determines whether the loan flow will affect loan principal amount. Principal amount (outstanding) is the base for later calculation of interest flows.
|Offset account type  |Determines offset account type for flow posting. <br>One of the following types should be selected: <br>- Customer – when flow should be posted as customer receivable (offset posting).  <br>- Vendor - when flow should be posted as vendor payable (offset posting). <br>- Ledger - usually used for migration purposes  <br>- Customer invoice, if we want to post flow via Free text invoice
|Customer posting profile |Posting profile which is used for posting when Customer offset account type is selected (setup for customer posting profile is in AR module). 
|Vendor posting profile |Posting profile which is used for posting when Vendor offset account type is selected (setup for vendor posting profile is in AP module). 
|Invoicing category |Invoicing category which is used to prepare invoices for interests when Customer invoice offset account type is selected 
|Item sales tax group | Defines one part needed for tax combination in order to calculate and post sales tax transaction.

3. **Posting setup fast-tab**

Within this fast-tab, GL accounts for posting are defined. This can be defined on Loan, Loan group or All loans level.

|      Field |Description|
|:----------------|:-------------|
|Valid for |Determines on what level, chosen account is to be used for posting. <br>Available values are: <br>- Table – chosen when we want to determine account for posting for specified loan. <br>- Group – to be used to determine account for posting for specified loan group (most common). <br>- All – selected account is to be used for all loans if no more strict rule is specified (Group or Table).
|Loan group | if rule is applicable on the Loan group level, in this field specific Loan group is selected. 
|Loan | if rule is applicable on Loan level, in this field specific Loan is selected.
|Main account |main account used for posting – principal liability/asset or interest/fee expense/revenue account. The offset account for posting of respected vendor payable / customer receivable is defined with Vendor/Customer posting profile (General fast-tab).
|Offset account |Offset main account if ledger was selected as Offset account type.

**Proposed flow categories setup for received loans (without accruals/deferrals):**

|             |Principal	|Offset account type    |Main account
|:------------|:----------------|:----------------------|:---------------|
|Drawing	|Yes	|Customer |Principal main account
|Repayment	|Yes	|Vendor	|Principal main account
|Interest	|No	|Vendor	|Related expense account
|Fee	|No	|Vendor	|Related expense account


**Proposed posting setup for received loans (without accruals/deferrals):**

||Account type Debit|Account (name) Debit|Account type Credit|Account (name) Credit|
|:------------|:---------------|:------------------|:-----------------|:--------------------|
|Drawing|GL account & Acc Receivables subledger	|Received loan pay-out	|GL account only (no subledgers)|	Loan liabilities
|Repayment|GL account only (no subledgers)|Loan liabilities|GL account & Acc payables subledger	|Received loan instalments - Due
|Interest|GL account only (no subledgers)|Loan interest expense	|GL account & Acc payables subledger|Received loan instalments - Due
|Fee	|GL account only (no subledgers)|Loan fees expense|GL account & Acc payables subledger|	Local/Foreign vendors


**Proposed flow categories setup for given loans (without accruals/deferrals):**

|             |Principal	|Offset account type    |Main account
|:------------|:----------------|:----------------------|:---------------|
|Drawing	|Yes	|Vendor	|Principal main account
|Repayment	|Yes	|Customer	|Principal main account
|Interest	|No	|Customer	|Related revenue account
|Fee	|No	|Customer	|Related revenue account

**Proposed posting setup for given loans (without accruals/deferrals):**

||Account type Debit|Account (name) Debit|Account type Credit|Account (name) Credit|
|:------------|:---------------|:------------------|:-----------------|:--------------------|
|Drawing|GL account only (no subledgers)|Loan receivables|GL account & Acc payables subledger|Given loan pay-out
|Repayment|GL account & Acc Receivables subledger|Given loan instalments - Due|GL account only (no subledgers)|	Loan receivables
|Interest|GL account & Acc Receivables subledger|Given loan instalments - Due|GL account only (no subledgers)|	Loan interest revenue
|Fee|GL account & Acc Receivables subledger|Local/Foreign customers|GL account only (no subledgers)|Loan fees revenue



4. **Financial dimensions fast-tab**

Financial dimensions to be used for posting of flows with flow category are selected in this fast-tab. 

5. **Accruals / deferrals**

When we are creating flow categories that will be used for posting of accruals/deferrals it is necessary that offset account type selected is Ledger.  
Posting setup should be:
- main account - GL account for interest posting
- Offset account - GL account for accruals / deferrals

As final posting (reversal of previously posted accruals) for accruals/deferrals is posted to opposite side, account for interest income or expense must have allowed posting to debit and credit. Because of this, some companies will create separate account for income or expense for accrued / deferred interests.


#**Partners’ product**
In the event that we have more loans with the same (similar) Interest and Repayment setups, we can create Partner’s product which can be used later as a template. We enter the Partner’s product in the **_Loan and deposit management > Setup > Loans > Setup of partner’s products – loans._** User can enter Interest setup and/or Repayment setup. 

#**Treasury partners**
We enter the lender or the borrower as a treasury partner in the _**Loan and deposit management > Common > Treasury partners.**_ We enter or select the following data from the drop-down list:
1. **General fast-tab**

|      Field |Description|
|:----------------|:-------------|
|Account | The partner code (usually determined automatically by the number sequence).
|Type |Account type: <br>- Organization. <br>- Person.
|Name / First name | Drop down list from which we select the relevant partner from Global address book.
|Other partner’s information data fields | Usually auto-filled with data from Global address book.
|Customer account |Customer account that will be used for later posting of loan’s account receivables. This account should belong to same Organization/Person as Treasury partner.
|Vendor account |Vendor account that will be used for later posting of loan’s account payables. This account should belong to same Organization/Person as Treasury partner.
|Sales tax group |Sales tax group for vendor or customer.

2. **Other fast-tabs**
User has the option to enter also partners data about:

|      Fast-tab |Description|
|:----------------|:-------------|
|Addresses |Addresses for the treasury partner.
|Contact information |Contact information for treasury partner (Phone, E-mail address...). 
|Payment |Payment details for vendor (Currency, Company bank account, Vendor bank account, vendor method of payment, Vendor payment specification).




