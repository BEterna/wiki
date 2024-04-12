#Calculation engine
Calculation engine creates loan flows using the Loan setup for repayment and interests.
In order for the calculation to run, Action transaction for loan drawing must be entered - this is first transaction that will be posted for the respective loan.

Calculation engine will create expected flows, which represent repayments, interests and accruals/deferrals (if defined in interest setup). In case of the setup change in the loan life-time, user will be appointed to do the loan recalculation (indicator: recalculation needed).

If calculation of interests by the system is not correct (in some cases because of the rounding it can differ) it is possible to manually change the interest amount before posting. If there would be a difference in calculation of the repayment amount (repayment flow) this can be corrected only via additional action line.


## Actions
Loan drawing action can be entered manually (using New) or can be created as a Default drawing. **Action line** includes following data:

|      Field | Description|
|:----------------|:-------------|
|Flow date |Flow date is entered by user and it should represent transaction date (cash inflow/outflow date). If created as default drawing system will default this date from loan start date. 
|Posting date |Posting date is automatically copied from flow date and should not be set to date different than Flow date. 
|Due date |this is the date that will be set as the due date of Accounts payable/receivable when action is posted. This date is editable but only if action is not already posted or reversed. 
|Flow category |User selects flow category based on the Loan transaction type of the action and according to the posting user wants to perform. This flow category is transferred to list of flows with other action parameters. Flow category determines how the flow is posted later. It is suggested to use flow categories with different names than flow categories used for calculated flows (categories set within interest and repayment setups), so the user can easily distinguish action flows from calculated flows. If action line is created as default drawing system will default the value which is set on Loan group as default drawing for the group.
|Amount in pay. Currency | Amount in payment currency to be posted with action posting. Total amount of drawings cannot exceed approved loan amount if the loan drawing policy is Non-Revolving. The total amount of drawing cannot exceed approved loan amount together with repayments if the loan drawing policy is Revolving. 
|Payment currency | Currency of the action transaction. Set as loan currency by default and should not be changed to another currency. 
|Amount in pos. cur. | Amount in loan currency. Same as amount in payment currency. 
 
**Note: Usage of actions**

Beside for the creation of drawing, action line can be used for any kind of loan transactions (repayments, interests or fees) if the system was not able to calculate them as a flow (based on repayment or interest setup).
Action lines can only be posted from tab Actions.

**Note: Usage of actions and accruals together**

Kindly note, that if you manually enter non-scheduled Action for drawing or repayment and use also accruals/deferrals for interest that prior to posting of such action line you must do the recalculation of flows, so that interest accruals/deferrals are properly recalculated and divided within the period. 

**Reverse action**

When actions are posted and there was some error, user can use **"Reverse action"** button to correct the mistake. If the transaction with an error was not posted as last one,  reversal must be done first for the actions with newest date, back to the oldest date. When all transactions are reversed, user must **recalculate** the Loan. 

**Reversed actions**

When user clicks on **"Reversed flow"** button, additional columns are added to the Actions table. These columns include following data:

|      Field | Description|
|:----------------|:-------------|
|Reversal status| **None** - meaning that transaction was not reversed, **Reversed** - transaction was already reversed and is no longer valid. **Reversing** - this is the line that is reversing some other action line.
|Reversal voucher| With this voucher original transaction was reversed.
|Reversal posting date| This is the posting date of the reversal action.

##Flows
Calculation engine will create/update loan flows when user selects **“Calculate”** button. Flows that are created/updated represent interests and repayments (amortisation plan) based on parameters that were entered in the setup for repayment and interests.

If setup for repayment and interest is changed in loan life-time, with recalculation this will affect flows as of specific date if they are not yet posted.

When flows are created user can change posting date and in case of interests flows the amount. Under same conditions as the posting date (flow/action must not be posted or reversed) also due date can be changed. Everything else can not be changed.

**Flows table** consist of the following data:

|      Field | Description|
|:----------------|:-------------|
|Manual | Shows whether the amount in payment currency of the flow has been changed manually.
|Flow date | Flow date should represent transaction date (cash inflow/outflow date)
|Posting date | Posting date is automatically set as flow date and should not be set to date different than Flow date. 
|Due date | This is the date that will be set as the due date of Accounts payable/receivable when flow is posted. For calculated flows, this date is set in accordance with respective Interest/Repayment setup.
|Flow category | Flow category determines how the flow is posted later. Flow categories for calculated flows are set in accordance with respective setup.
|Payment currency | Currency of the flow transaction. Same as the loan currency.
|Amount in pay. Currency | Calculated amount in payment currency to be posted with flows posting. 
|Position currency | Loan currency.
|Amount in pos. cur. | Amount in loan currency. Same as amount in payment currency. 
|Nominal amt. in pos. cur. | Amount of the principal change (drawing or repayment action/flows affects principal).
|Fixed | This field is activated for flows from actions or for posted flows.
|Posted | Describes whether the flow is posted or not.
|Voucher | Voucher number of the posted flow.
|Balance | Remaining (not settled) amount of the account payable/receivable from the posted flow.

Using button **“Calculation details”** user can display more details about the calculated interest flows:

|      Field | Description|
|:----------------|:-------------|
|Period start | Starting date of the period for which interest amount is calculated.
|End | The ending date of the interest period.
|End inclusive | Shows whether the interest period is inclusive of the date from “End” field.
|Days | Number of days for which interest is calculated.
|Interest rate | Yearly interest rate used for interest calculation.
|Base amount | Base amount (principal) for stated period, for which interest will be calculated/charged.

Using button **“Accrual details”** user can display more details about the calculated accrual interest flows:


|      Field | Description|
|:----------------|:-------------|
|Accrual reversal date| Is the date, when calculated accruals in the line were reversed
|Accr. orig. period start| Is the start date of the original calculated accruals in the line
|Accr. orig. period end| Is the end date of the original calculated accruals in the line
|Accr. orig. end incl.| Tick that represents, that end date is included in the accrual calculation
|Accr. orig. days| Represents the number of days for which original accruals were calculated (number of days between Accr. orig. period start and Accr. orig. period end)
|Accr. orig. base amount| this 


**Reverse flow**

When flows are posted and there was some error, user can use **"Reverse flow"** button to correct the mistake. If the transaction with an error was not posted as last one, reversal must be done first for the flows with newest date, back to the oldest date. When all transactions are reversed, user must **recalculate** the Loan. 

**Reversed flows**

When user clicks on **"Reversed flow"** button, additional columns are added to the Flows table. These columns include following data:

|      Field | Description|
|:----------------|:-------------|
|Reversal status| **None** - meaning that transaction was not reversed, **Reversed** - transaction was already reversed and is no longer valid. **Reversing** - this is the line that is reversing some other action line.
|Reversal voucher| With this voucher original transaction was reversed.
|Reversal posting date| This is the posting date of the reversal transaction.
