This section summarizes VAT features, developed in scope of the LOC_BANK extended localization packet in connection with vendor payments.

-----

#Central bank purpose code on vendor payments

The four-digit code for the purpose of payment replaces the textual purpose of the payment purpose. Its use recommends payment service users to the SEPA scheme rule, along with a structured reference that allows automatic closing of claims. The use of codes is particularly important in the payment of salaries, pensions, holiday allowances, travel expenses, social transfers, etc., as these transfers to accounts of natural persons, if the execution of execution (asset diversion) takes place on the account is different, depending on the legislation.

This extended localization feature enables the transfer of Central bank purpose code from vendor to pending vendor invoice header and then to vendor transaction. If there is no Central bank purpose code on vendor when vendor invoice is created, the value is transferred from Accounts payable parameters. Value in field “Central bank purpose code” on vendor payment journal line can be edited before generating export file for bank. If purpose code is missing on vendor transaction upon transfer to payment journal, it is populated with Central bank purpose code value from Vendor, if it is defined there. If not, it is transferred from Accounts payable parameters.

[Detailed documentation](https://adacta.sharepoint.com/:w:/r/sites/ERP-Product-Development/Shared%20Documents/D365FO%20Localization%20documentation/D365%20ext%20LOC_Vendor%20Payments.docx?d=w3e80214c755e4910a3b5720334715941&csf=1&e=H7dfEj) (chapter 2.1)

-----

#Payment purpose description

This extended localization feature allows field “Payment purpose” on payment order to be populated with value from field “Note” on vendor payment journal line. This way, users do not need to populate the payment purpose field manually, when generating vendor payments.

[Detailed localization](https://adacta.sharepoint.com/:w:/r/sites/ERP-Product-Development/Shared%20Documents/D365FO%20Localization%20documentation/D365%20ext%20LOC_Vendor%20Payments.docx?d=w3e80214c755e4910a3b5720334715941&csf=1&e=H7dfEj) (chapter 2.2)

-----

#Export format configuration

This section includes information about the electronic vendor payments export formats, used as part of the Adriatic localization. Export formats, which are used by the majority of the local (Slovenian, Croatian, Serbian and North Macedonian) electronic banking system are included in scope of this extended localization feature.

This extended localization feature enables the setup (Methods of payments), adequate transformations and export of the locally used electronic vendor payment formats. Transformations for the following bank formats are part of this extended localization feature:
-	Slovenia – ISO 20022 (SEPA, VP70)
-	Croatia – FINA, ISO 20022
-	Serbia – Halcom, Halcom Foreign - GWS

[Detailed documentation](https://adacta.sharepoint.com/:w:/r/sites/ERP-Product-Development/Shared%20Documents/D365FO%20Localization%20documentation/D365%20ext%20LOC_Vendor%20Payments.docx?d=w3e80214c755e4910a3b5720334715941&csf=1&e=H7dfEj) (chapter 1)

-----

#Payment ID validation for vendor invoice and payment journal (SI, HR)

This topic provides country/region-specific information about the locally used Payment IDs, which are often mandatory information when making payments in Slovenia in Croatia. Payment IDs need to be generated according to local formats. In order to validate the payment ID form to comply with the local requirements, this extended localization feature enables the adequate validation.

This extended localization feature allows the validation of payment ID for vendor invoice and payment journal is executed upon saving. Control for Payment ID on vendor invoice is additionally triggered upon document saving when vendor bank account has country code for which validation is implemented (standard validation!). Payment ID is entered manually in purchase documents or on vendor payment journal line before posting. As part of extended localization controls are added for models SI00, SI01, SI02, SI03, SI04, SI05, SI06, SI07, SI08, SI09, SI10, SI11, SI12, SI18, SI19, SI28, SI38, SI40, SI41, SI48, SI49, SI51, SI55, SI58, and SI99. If the entered value is wrong, system will generate warning. For other (foreign) models standard validations are used. Validation can be enabled or disabled by the authorized users.

[Detailed documentation](https://adacta.sharepoint.com/:w:/r/sites/ERP-Product-Development/Shared%20Documents/D365FO%20Localization%20documentation/D365%20ext%20LOC_Vendor%20Payments.docx?d=w3e80214c755e4910a3b5720334715941&csf=1&e=H7dfEj) (chapter 2.4)


-----

#Payment reference generation

This topic provides country/region-specific information about the locally used Reference numbers, which are often mandatory information when making payments. Reference numbers need to be generated according to locally accepted formats. In order to simplify and automate Payment reference generation in an adequate form, this extended localization feature has been developed.

This extended localization feature enables the automatic generation of payment references for vendor payments through vendor payment journal. Payment reference number is generated upon XML creation and captured in “Payment reference” field of each of the payment journal lines. Payment reference form depends on the XML export format.

[Detailed localization](https://adacta.sharepoint.com/:w:/r/sites/ERP-Product-Development/Shared%20Documents/D365FO%20Localization%20documentation/D365%20ext%20LOC_Vendor%20Payments.docx?d=w3e80214c755e4910a3b5720334715941&csf=1&e=H7dfEj) (chapter 2.3)

