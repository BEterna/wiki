This section summarizes VAT features, developed in scope of the LOC_BANK extended localization packet in connection with vendor payments.

-----

#Central bank purpose code on vendor payments

The four-digit code for the purpose of payment replaces the textual purpose of the payment purpose. Its use recommends payment service users to the SEPA scheme rule, along with a structured reference that allows automatic closing of claims. The use of codes is particularly important in the payment of salaries, pensions, holiday allowances, travel expenses, social transfers, etc., as these transfers to accounts of natural persons, if the execution of execution (asset diversion) takes place on the account is different, depending on the legislation.

This extended localization feature enables the transfer of Central bank purpose code from vendor to pending vendor invoice header and then to vendor transaction. If there is no Central bank purpose code on vendor when vendor invoice is created, the value is transferred from Accounts payable parameters. Value in field “Central bank purpose code” on vendor payment journal line can be edited before generating export file for bank. If purpose code is missing on vendor transaction upon transfer to payment journal, it is populated with Central bank purpose code value from Vendor, if it is defined there. If not, it is transferred from Accounts payable parameters.

[Detailed documentation](http://axweb/D365O%20Localization%20Documents/D365%20ext%20LOC_Vendor%20Payments.docx?Web=1)