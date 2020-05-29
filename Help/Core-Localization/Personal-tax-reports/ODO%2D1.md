ODO-1 report needs to be generated in case of payment to non-residents. 



## **Setup**
---

### General ledger parameters

1. Open **General ledger > Ledger setup > General ledger parameters > Adacta localization**.
2. Select **ODO1 report** configuration in ODO 1 electronic reporting format field. 
 
 
### Sales tax authorities

1. Open **Tax > Indirect taxes > Sales tax > Sales tax authorities**.
2. Create new **Tax authority** for personal tax reporting purposes.
3. In the **Vendor account** field select vendor FURS. Tax payments will be later posted to this account.
4. In the field **Report layout** select value **Default**.

### Sales tax settlement periods

1. Open **Tax > Indirect taxes > Sales tax > Sales tax settlement periods**.
2. Create new **Tax settlement period** for ODO-1 reporting. 
3. In the **Authority** field select authority that was created for personal tax reporting purposes. 
4. In the **Period interval unit** select interval that will be used for reporting.  

### Ledger posting groups

1. Open Tax – Setup – Sales tax – Ledger posting groups.
2. The new ledger posting group is opened for ledger posting (main account defined in field “Sales tax receivable”). According to our business practice, we open as many ledger posting groups as there are different ledger accounts we want to post liabilities to.
 
There is no need to set up a Settlement account since closing the period will post REK-2 entries to the vendor, defined as tax authority on sales tax settlement period for REK-2. 

### Sales tax codes

1. Open Tax – Indirect taxes – Sales tax – Sales tax codes.
2. REK income type is defined on sales tax code. For every income type there are individual sales tax codes for deductions and contributions:
   - Income tax
   - Each of the contributions to gross
   - Each of the deductions from gross 
3. Under General, settlement period and ledger posting group, created for REK-2 purposes, and currency are defined. 
4. Sales tax codes are created for deductions, calculated from gross amount, as well as for contributions to gross. For correct calculation of deductions from gross the functionality of negative tax is used on those sales tax codes that define deductions from gross. Enabling field “Allow negative sales tax percentage” allows the entry of negative sales tax code value. Bellow, there is an example for entering “PIZ iz bruta” setup of 15.5%. 
5. Sales tax code percentage is entered in form Value.

When entering the value for income tax it is important to enter also potential personal exemption, tax allowances, and contributions that reduce the basis for calculation.  There are additional fields in form Value (“Personal tax” part) that are considered for the calculation for income tax percentage.  
 
“Personal tax” part: field Value should be entered in negative amount for income tax; fields Personal exemption, Tax allowances (10%), and Contributions (PIZ (15,5%) + ZZ (6,36%) is 21,86%) are populated with adequate percentages. The percentage of sales tax code value is automatically updated after entering. 

Contributions to the gross increase in total employer cost. For each of the contributions to gross it is, therefore, necessary to create two sales tax codes – one with a positive value and 100% non-deductible (result is posting on cost account), the other with a negative value and 0% non-deductible (result is posting on liabilities account for withholding tax). 
 
### Income types and income tax income types

1. Open Tax – Setup – Adriatic – Personal tax – Income types.
2. It is necessary to set up REK income types for reporting purposes. Using the button “New” entry with income type and description is created.
3. Open Tax – Setup – Adriatic – Personal tax – Income tax income types.
4. Using the button “New” entry with income tax income type and description is created.
 
#### Setup for REK-2 reporting

There are fields in Adacta localization part on sales tax codes that need to be correctly populated in order for REK-2 reporting to work.
   - Personal tax reporting: REK-2
   - Income type: chosen from Tax – Setup – Adriatic – Personal tax – Income types
   - In case of sales tax code for income tax, fields Deduction type and Contribution type are populated with “None”, field Tax income type has to have a value from Tax – Setup – Adriatic – Personal tax – Income tax income types (same as in the picture above)
   - Deduction type: in case of entry paid by employee (deduction from gross), one of the following values has to be chosen: PIZ, ZZ, Parental care, Employment; field “Tax income type” has to be empty.
   - Contribution type: in case of entry paid by employer, it is necessary to choose one of the following options in this field: PIZ, ZZ, Parental care, Employment, Work injuries, Special tax, Contingent or temporary work levy. Same reporting setup needs to be done on both sales tax codes – positive and negative one.
   - Tax income type: in case of income tax entry, value is chosen from Tax – Setup – Adriatic – Personal tax – Income tax income types.
  
#### Reliefs and certificates

If payment is done to contractors who exercise certain reliefs on income tax it is necessary to create additional sales tax codes with the appropriate settings. Recommended is to create new procurement categories for income types with relief and define new item sales tax groups (procurement category is then chosen on the purchase order/vendor invoice for the contractors that exercises a certain relief). It is also possible to create new sales tax groups and allocate them to respective vendors. 

Adacta localization tab on sales tax code allows “Benefit type” and “Required certificate” to be chosen in section Reporting. Choosing a certain relief does not automatically affect the calculation – it is necessary to manually enter the appropriate value (e.g. if relief for cultural workers is selected on sales tax code, it is necessary to enter the appropriate percentage of relief to Values; sole indication that it is a relief for cultural workers does not affect the amount).

For this purpose, new fields are added to sales tax codes, Adacta localization. It is possible to choose among the following relief options:
   - DTC reduced tax: enable if income tax is subjected to tax reduction under double taxation convention. 
      - Required certificate: choose certificate type, in case that is needed to exercise tax reduction (individual certificates are entered on vendor card – more in Chapter Vendor certifications) 
 
Certification types are entered in Procurement and sourcing – Setup – Vendors – Certification type.
 
The certificate number that is entered on vendor card, and the corresponding percentage of the personal income tax rate, which is entered in sales tax code value, are recorded in field D11 of the REK report.
   - Withholding rate deduction: enable if income tax is subjected to reduced deductions.
 
Fields 110 and 203 of the REK-2 report are populated with information about tax base amount and reduced deduction amount.
   - Additional tax reduction (cultural workers): checkmark to determine whether the income is subject to additional relief for the self-employed in culture (the gross amount is recorded in field 102 of REK-2 report)
 
#### Benefits

“Benefit type” field is added to the Sales tax code tab Adacta localization. Options to select are Personal vehicle, Accommodation, Insurance premium, and Other.
 
Test case presented in chapter Benefits.

#####	Payment setup

Payment section of the Adacta localization tab on sales tax codes enables entry of payment data, such as Vendor account (Slovenian tax authority FURS, in our case), Bank account to which the payment of personal tax will be executed, Payment ID, and Central bank purpose code. Entered data are transferred to the vendor journal payment line using the Payment proposal.
 
### Sales tax groups

1. Open Tax – Indirect taxes – Sales tax – Sales tax groups.
2. Add adequate sales tax codes to sales tax groups.
 
### Item sales tax groups

1. Open Tax – Indirect taxes – Sales tax – Item sales tax groups.
2. Create item sales tax group for each REK income type and add adequate sales tax codes. 
 
### Procurement categories

1. Open Procurement and sourcing – Procurement categories.
2. Create a procurement category for each income type and define the Item sales tax group. 
3. Procurement categories need an adequate ledger account for posting – this setup is done in Inventory management – Setup – Posting – Posting. 
 
If the cost of contract work is posted via the vendor invoice, the ledger account setup is done under “Purchase expenditure for expense” transaction type. In case product receipts are used, posting setup also needs to be done in the “Purchase expenditure, un-invoiced” section.

### Vendor certifications

1. Certificates regarding reliefs or international conventions are entered on vendor card -> button Certifications. 
2. Mandatory fields to enter are: 
   - Certification type and Certification number,
   - Certifying organizations (e.g. Slovenian tax authority or Ministry for culture),
   - Certification date. 
3. If Certification type is chosen on sales tax code and a certificate for the same certification type is entered on the vendor, then the certificate number is recorded in REK-2 field D11. 