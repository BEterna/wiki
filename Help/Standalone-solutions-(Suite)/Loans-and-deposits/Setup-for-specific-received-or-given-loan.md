#General loan setup (received or given loan)

From the perspective of entering the loan there is no difference between received or given loan. First general loan parameters must be entered that consist of:

|      Field | Description|
|:----------------|:-------------|
|Loan |The loan code (usually determined by the number sequence).
|Loan status |Three different statuses are available: **Planned, Active** and **Completed**. When loan is first created it is in Planned status. When contract is valid, status of the loan must be changed to Active. Posting of loan transactions (actions or flows) is only possible when loan status is Active. Final status is Completed. This status for the loan should be set, when loan is no longer Active.  
|Description  |Short description of the loan, can be used for easy identification of the loan.
|Loan group  |Defines to which loan group loan belongs.
|Recalculation needed |Information to user whether recalculation of loan’s flows is suggested to be done. More details will be provided in the section: Recalculation needed.
|Treasury partner  |Treasury partner from which loan is obtained. Defines Customer and Vendor accounts for later postings.
|Customer account  |Defines the Customer account used for posting of loan’s receivables.
|Vendor account | Defines the Vendor account used for posting of loan’s payables.
|Contract number | Field where contract number could be entered for later easy referencing.
|Partners product | Defines default values for interest and repayment setup, so not all parameters have to be set for similar loans. Can be selected only during loan creation (cannot be changed after loan is created) while setup parameters set with template can be changed regularly as for any loan.
|Amount in transaction currency |Approved loan amount in loan currency. May be changed during loan life period.
|Currency |Loan currency.
|Drawing policy| There are two drawing policies available, **Revolving** and **Non-revolving**. This new possibilities extend Loan and Deposit functionality also for Revolving loans. This means, that if drawing policy is revolving, all repayments will be added back to principal amount and company can make new drawing up to available amount. 
|Start date (mandatory) | Loan start date. Represent the date from which cash inflows/outflows may be occurred (defined within contract). This date may be changed during loan life period.
|End date (mandatory) | Loan end date. Represents the date to which cash inflows/outflows may be occurred (defined within contract) and sometimes prolonged with annexes. This date may be changed during loan life period.
|Contact ID | Contact person from partner company.
|Worker | The main contact/responsible from our company. 
|Sales tax group |Should be entered only if interest transaction must be included in the VAT report. 

Beside above parameters, there is an additional setup for payment and financial dimensions related to the respective loan.



#Repayment setup
After the general loan data is entered, user can enter Repayment setup.

In the SETUP > Repayment form, we enter the repayment method, the repayment category that affects the posting and all other parameters relevant for repayment flows calculation and posting. 

Available fields are:

|      Field | Description|
|:----------------|:-------------|
|Effective |Date from which repayment setup is applicable.
|Expiration |Date to which repayment setup is applicable.
|Description |Short description of the repayment setup.
|Repayment method |Determines the method how principal repayment flows will be calculated. There are 3 available methods: <br>- Constant payment - equal annuities (principal + interest) are paid per period. It requires specific setup scenario together with interest setup. This feature works only in the basic configuration (interest change and one-off repayments are not available at the moment). <br>– Constant amortizing - equal amounts of principal are paid during the period. <br>– End of term - whole outstanding principal amount is paid on Loan end date.
|Amount of the instalment |can be used only if constant amortizing repayment method is chosen. 
|Date of the first payment  |The first date on which repayment will take place (flow date of the first repayment instalment). May be left blank if End of Term is set for Repayment method or Period for loan repayment.
|End of Month  |If the first date for repayment flow is, for example, April 30, 2019 and principal is always repaid on the last day of the month, we should select YES for this option.
|Period for loan repayment |Together with Length of the period determine what will be the frequency of repayment instalments. Available values are (more details on applied rules are provide in the table above): <br>–	Daily. <br>–	Monthly. <br>–	End of term.
|Length of the period |Length of the period (days or months) for repayment calculation.
|Payment terms for repayment |If principal repayment terms are different from the flow dates, in this field we can set payment terms (defined within standard D365FO modules) for calculated repayment flows.
|Repayment category | Flow category that will be used for later calculated repayment flows posting.
|Additional Fields that can be used| <br>- Working day adjustment. <br>- Adjust last day. <br>- Calendar. 

Option to set more than one repayment setup is available (setup periods cannot overlap). This option is useful when more than one repayment conditions are applicable over loan life period, e.g. repayment conditions are changed from fortnightly to monthly. 

#Interest setup


In the SETUP > Interest form, user enters the interest rate, the interest flow category (that affects the posting) and all other parameters relevant for interest calculation and posting. 

Available fields are:
|      Field | Description|
|:----------------|:-------------|
|Effective |Date from which interest will be calculated.
|Expiration |Date to which interest will be calculated.
|Description |Short description of the interest setup.
|Interest rate |Interest rate (percentage) on a yearly level.
|Interest category  |Flow category that will be used for later calculated interest flows posting.
|Day count convention |In this field, the method for day counting (calculation of number of days for which interest will be charged) is to be chosen. There are many available conventions, for End of term and Monthly instalments usually used conventions are: <br>- Act/365 Fixed, <br>- Act/365L, <br>- Act/360, <br>- Act/364, <br>-Act/Act ISDA, <br>-30US/360 and <br>-30E/360, <br><br>while for daily based instalments usually used conventions are: <br>- Act/365 Fixed, <br>- Act/365L, <br>- Act/360, <br>- Act/364,  <br>- Act/Act ISDA. <br><br>Flows are calculated according to setup based on good practice. Sometimes bank and other companies might have slightly different approach with loan contracts and one-off transactions. Due to this fact it is important that after flows are generated, they should be compared to amortization plan and checked for accuracy.
|First interest instalment date |The first date on which interest calculation will take place (flow date of the first interest instalment).
|Period inclusive of end date |If the entered date for the first interest instalment date should be included in period for which the interest is calculated, we should select YES for this option.
|End of Month |If the first day of interest is, for example, April 30, 2019 and flow date of interest instalment is always on the last day of the month, we should select YES for this option.
|Interest calculation period |Together with Length of the period determine what will be the frequency of interest calculation. Available values are: <br>–	Daily. <br>–	Monthly. <br>–	End of term (in this case, Interest setup expiration date is used as interest flow date).
|Length of the period |Length of the period (days or months) for interest calculation.
|Payment terms for interest |If interest payment terms are different from the flow dates, in this field user can set payment terms (defined within standard D365FO modules) for interest flows.
|Additional Fields that can be used | Working day adjustment; Adjust last day; Calendar; Full last period; Currency; 
|Accrue/defer interest| Set this parameter to Yes if accruals/deferrals should be calculated (e.g. if interest are paid quarterly, but we wish to have monthly interest posting).
| Flow category (accrual) | Select a flow category that will be used for accrued/deferred interests. It is advised not to use same category as for interests in order to separate the normal interest flow from accruals/deferrals interest flow.
|Method for accrual / deferral |There are two possibilities for its calculation: <br>- Linear - based on number of days in the month, <br>- Pro rata - each month same amount. <br> The selected method has effect only for calculations, where interest calculation Day count convention used is 30/360, while for other day count conventions it has no effect.


Option to set more than one interest setup is available (setup periods cannot overlap). This option is useful when more than one interest conditions are applicable over loan life period, e.g. interest rate is variable (depends on reference rate, such as EURIBOR).

**Note: Usage of actions and accruals**

Kindly note, that if you manually enter non-scheduled Action for drawing or repayment and use also accruals/deferrals for interest that prior to posting of such action line you must do the recalculation of flows, so that interest accruals/deferrals are properly recalculated and divided within the period. 

