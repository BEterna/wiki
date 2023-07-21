
#Data entities - Open in excel functionality
--- 

There are few entities available for import data related to loans that can be used also via Open in excel functionality.

|Data             |Entity	|Target entity|
|------------|:-----------------|:---------------|
|Treasury partners|Treasury partners|AdTMPartnerEntity
|Loan (general setup)|Loans|AdTMCreditLineEntity
|Repayment setup|Loan repayment setup|AdTMCreditLineRepaymCalcSetupEntity
|Interests setup|Loan interest setup|AdTMCreditLineInterestCalcSetupEntity
|Actions|Loan actions	|AdTMCreditLineLineEntity

Kindly note:
- Treasury partners must be entered or imported prior to import of the Loan entity. 
- After the Loan is created, setup for Interest or Repayment can be entered or imported.
- Action (line) cannot be updated; the action line can be deleted and re-entered.
