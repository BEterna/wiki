# How To: Validate Registration and Tax exempt codes

In order to comply with locally used registration IDs (e.g. tax and identification numbers), additional registration categories are added with this localization feature and need to be set up for the adequate Registration IDs to allow other localized features to work correctly - e.g. REK reporting and eInvoices use Registration IDs with the localized registration categories for validation purposes. If inadequate registration categories are used for the set-up of registration IDs, validation when using other localized features may fail, while the required ID may also be missing from other documents, therefore localized registration categories should be used.

Standard D365 features allow for the validation of Tax exempt numbers formats. However, by standard, format validation is not available for Slovenian or Croatian Tax exempt numbers and is added with this localization feature.

This topic provides also country/region-specific information about the Croatian tax number (OIB) format and structure validation. OIB (Osebni identifikacijski broj) is used in Croatia as a tax identification number. Standard D365 feature does not allow for OIB format validation, therefore validation is added in the scope of this localized feature.


## Registration ID features (SI, HR, RS)

The standard functionality of Registration IDs is used for VAT ID, tax identification numbers, Company registration numbers and National identification numbers for Slovenia, Croatia, and Serbia. Users can set up the registration IDs with the localized registration categories for customers, vendors, workers, and legal entities. Localization features are additionally added registration categories, upon which also locally specific validation of format and structure is enabled.

### Registration types

1. Open Organization administration – Global address book – Registration types – Registration types.
2. Set up registration types for the different types of registration numbers that each party is subject to:
   - Name: The name of the registration type.
   - Description: The description of the registration type.
   - Country/region: The unique identifier of the country/region.
   - Tax authority: The tax authority that is associated with the registration type.
   - Restricted to: The kind of restriction that applies to the tax registration type: None, Person, Organization.
   - Format: The validation format for the registration type.
   - Can be updated: Defines if the registration number for the registration type can be updated after it is entered.
   - Unique: Defines if the registration number for the registration type is unique.
   - Primary for the country: If a party is associated with one or more addresses in a particular country and the registration ID is valid for all these addresses, you must designate one address as primary for the country. You can only register one ID as primary. Defines if the registration number can be entered only for primary for country address.

### Registration category

1. Open Organization administration – Global address book – Registration types – Registration category.
2. Registration category is country/region registration identifier approved for using in particular country/region for tax, customs, and other purposes. This category defines validation rules of particular registration ID (including check digits etc.) and inclusion registration ID in different reports: 
   - Registration type: The registration type for a particular country/region.
   - Restricted to: The kind of restriction applies to the tax registration type: None, Person, Organization.
   - Registration category: The unique registration identifier approved for use in the country. As part of localization following Registration categories were added:
     - Tax identification number (AD)  used for Davčna številka
     - Company registration number (AD)  used for Matična številka podjetja
     - National identification number (AD)  used for EMŠO
Standard Registration category VAT ID is used for ID za DDV.
The dropdown menu for Tax exempt number (with a filter on Party) will show all registration IDs with the VAT ID registration category (standard functionality).
 
### Use registration IDs

1. Click Registration IDs on forms related to the party, legal entity, vendor, customer, worker to open the Manage addresses page. 
2. On the Registration ID tab, click Add, and enter information about the registration ID. Validation upon format and structure for a registration number that is VAT ID registration category is part of localization functionality.
 
### Registration IDs 

Standard functionality Registration IDs are used for managing different kinds of identification numbers. Next bullets are included only for user setup help. 

#### VAT ID, Tax identification number (AD), Company registration number (AD) and National identification number (AD) for Slovenia

1. Setup in registration categories: 
   - VAT ID category as ID za DDV
   - Tax identification number (AD) as Davčna številka
   - Company registration number (AD) as Matična številka podjetja
   - National identification number (AD) as EMŠO 
2. On the Registration ID tab, enter information about the registration ID.
3. If tax identification numbers are imported, using LOC_ext functionality (for more, see Chapter Import of SI taxpayers*), they are shown in drop down in Registration number field. Drop down is available as part of LOC_core package. This is valid only for following Registration types:
   - VAT ID: Tax exempt numbers list is opened. Tax exempt number from the list is copied to Registration number field. Pay attention to the setup of the Registration type formatting. Correct formatting should be SI########. 
   - Tax identification number (AD): Slovenian taxable persons list is opened. Tax registration number from the list is copied to Registration number field.
   - Company registration number (AD): Slovenian taxable persons list is opened. ID number from the list is copied to Registration number field. 
In other cases registration number must be entered manually.

#### OIB number for Croatia

OIB number is entered as Registration type “Tax identification number (AD)”, using standard registration IDs functionality. For VAT purposes VAT ID Registration type is used. 
 
1. Set up registration categories.
2. In the case of Registration type with registration category Tax identification number (AD), a dropdown list with Croatian taxable persons opens. The dropdown is available as part of the LOC_core package. 
 
For the VAT ID registration category, manual entry is required. 

#### Registration IDs for Serbia

Registration ID can be used for an ID number, using standard registration IDs functionality.
 
1. Set up the Enterprise ID registration category for the ID number.
2. Click Registration IDs on forms related to the party, legal entity, vendor, customer, worker to open the Manage addresses page and enter registration number for selected registration type.

-----
## Tax exempt number validation (SI, HR)

Localization feature offers validation of Tax exempt number also for Slovenia and Croatia (8 digits for Slovenia and 11 for Croatia). Validation for each of these countries can be enabled or disabled by the authorized users. If validation is enabled, upon entering a tax exempt number with the inadequate format, a warning is displayed.

### Setup

Validation is performed if the Check tax exempt number is marked in Tax/Setup/Sales tax/Country/region parameters. 

### Validation

Validation for Slovenia and Croatia is added as part of localization. Validation for other supported countries is performed as part of the standard solution. Tax exempt number structure (8 digits for SI and 11 for CRO) is validated upon entry – there is a warning displayed in case of incorrect tax exempt number.   

-----
## OIB validation (HR)

The localization feature enables OIB number entry in Croatian taxable persons (localized) form and automatically validation in terms of the official OIB format and structure (11 digits). If the entered OIB number does not pass the validation, a warning is displayed.

### OIB validation (CRO)

1. New OIB number is entered in Croatian taxable persons (Tax – Declaration – Croatia – Croatian taxable persons). 2. Format and structure (11 digits) are validated upon entry – there is a warning in case of an incorrect OIB number.

### Tax exempt number validation (SI, CRO)

1. Validation is performed if the Check tax exempt number is marked in Tax/Setup/Sales tax/Country/region parameters.  
2. Validation for Slovenia and Croatia is added as part of localization. Validation for other supported countries is performed as part of the standard solution. Tax exempt number structure (8 digits for SI and 11 for CRO) is validated upon entry – there is a warning displayed in case of incorrect tax exempt number.   
