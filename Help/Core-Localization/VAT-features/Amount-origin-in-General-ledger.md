When sales tax transactions need to be posted or corrected through the General journal using direct posting into the Sales tax main account and Sales tax codes. Also used in different integration scenarios where sales tax calculation from D365FO won't be applicable.

## Origin field
---

In the general journal lines.

1. Open **General ledger > General journals > Lines > General tab > Tax**. 
2. In the field **Origin** manually input the Amount origin of the sales tax transaction. 
3. Post general journal.  
4. View Posted sales tax transactions where the amount from the Origin field is transferred into the Amount origin column.

NOTE: When you post the amount of the sales tax on the Credit side of the General journal line and have a Sales tax payable direction on the Sales tax code, you must enter a negative value of the amount into the origin field. 