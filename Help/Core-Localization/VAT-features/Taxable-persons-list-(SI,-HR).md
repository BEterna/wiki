# How to: Add additional information on Taxable person list
 
A taxable person list is added in the scope of Slovenian and Croatian localization. Slovenian list stores information, such as tax registration number, company registration number, taxable person type, name, address, and special handling (e.g. 76.a ZDDV-1) checkmark, while Croatian list stores the following information: OIB, identification number, type, and name. This list can later be used when adding VAT ID to Vendor or Customer. 

_*List of Taxable persons can also be imported. Import is enabled as part of a separate Tax package._

<!-- 
[Detailed documentation](https://adacta.sharepoint.com/:w:/r/sites/ERP-Product-Development/Shared%20Documents/D365FO%20Localization%20documentation/D365O%20LOC_Tax%20identification%20number.docx?d=wa2bf0a8b9616456eade04fa02e33d080&csf=1&e=o2QDt3)
 -->

## Setup

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

Registration category is country/region registration identifier approved for using in particular country/region for tax, customs, and other purposes. This category defines validation rules of particular registration ID (including check digits etc.) and inclusion of registration ID in different reports

1. Open Organization administration – Global address book – Registration types – Registration category.
2. Set fields:
   - Registration type: The registration type for a particular country/region. 
   - Restricted to: The kind of restriction applies to the tax registration type: None, Person, Organization. 
   - Registration category: The unique registration identifier approved for use in the country. As part of localization following Registration categories were added: 
      - Tax identification number (AD): in Slovenia used for Davčna številka. 
      - Company registration number (AD): in Slovenia used for Matična številka podjetja. 
      - National identification number (AD): in Slovenia used for EMŠO.

Standard Registration category VAT ID is used in Slovenia for ID št. za DDV. 

Dropdown menu for Tax exempt number (with the filter on Party) will show all registration IDs with the VAT ID registration category (standard functionality). 

## Use registration IDs 

1. Click Registration IDs on forms related to the party, legal entity, vendor, customer, worker to open the Manage addresses page.  
2. On the Registration ID tab, click Add, and enter information about the registration ID. Validation upon format and structure for a registration number that is VAT ID registration category is part of localization functionality. 

## Registration IDs  

Standard functionality Registration IDs are used for managing different kinds of identification numbers. Next bullets are included only for user setup help.  

### 1. VAT ID, Tax identification number (AD), Company registration number (AD) and National identification number (AD) for Slovenia 

Setup in registration categories:  
   - VAT ID category as ID za DDV 
   - Tax identification number (AD) as Davčna številka 
   - Company registration number (AD) as Matična številka podjetja 
   - National identification number (AD) as EMŠO  

On the Registration ID tab, enter information about the registration ID. 

If tax identification numbers are imported, using LOC_ext functionality (for more, see Chapter Import of SI taxpayers*), they are shown in a dropdown in the Registration number field. A dropdown is available as part of the LOC_core package. This is valid only for following Registration types: 
   - VAT ID: Tax exempt numbers list is opened. Tax exempt number from the list is copied to the Registration number field. Pay attention to the setup of the Registration type formatting. Correct formatting should be SI########.  
   - Tax identification number (AD): Slovenian taxable person list is opened. The tax registration number from the list is copied to the Registration number field. 
   - Company registration number (AD): Slovenian taxable person list is opened. ID number from the list is copied to the Registration number field.  

In other cases, registration numbers must be entered manually. 

### 2. OIB number for Croatia 

OIB number is entered as Registration type “Tax identification number (AD)”, using standard registration IDs functionality. For VAT purposes VAT ID Registration type is used.  

Set up registration categories. 

In the case of Registration type with registration category Tax identification number (AD), a dropdown list with Croatian taxable persons opens. A dropdown is available as part of the LOC_core package.  

For the VAT ID registration category, manual entry is required.  

### 3. Registration IDs for Serbia 

Registration ID can be used for an ID number, using standard registration IDs functionality. 

Set up the Enterprise ID registration category for the ID number. 

Click Registration IDs on forms related to the party, legal entity, vendor, customer, worker to open the Manage addresses page and enter registration number for selected registration type. 

## Registration ID validation 

### OIB validation (CRO) 

New OIB number is entered in Croatian taxable persons (Tax – Declaration – Croatia – Croatian taxable persons). Format and structure (11 digits) are validated upon entry – there is a warning in case of an incorrect OIB number. 

### Tax exempt number validation (SI, CRO) 

Validation is performed if the Check tax exempt number is marked in Tax/Setup/Sales tax/Country/region parameters.  

Validation for Slovenia and Croatia is added as part of localization. Validation for other supported countries is performed as part of standard solution. Tax exempt number structure (8 digits for SI and 11 for CRO) is validated upon entry – there is a warning displayed in case of incorrect tax exempt number.    

## Taxable persons list 

### Taxable persons list for Slovenia 

*Tax – Declarations – Slovenia – Slovenian taxable persons* 

Slovenian taxable persons list is added as part of localization. Information like tax registration number, ID number (i.e. company registration number), taxable person type, name, and address of the taxpayer, and the information whether the partner is liable for Slovenian VAT or whether it has special handling based on 76.a article of ZDDV-1 can be recorded in the list. 

### Taxable persons list for Croatia 

*Tax – Declarations – Croatia – Croatian taxable person*

Croatian taxable persons list is added as part of localization. The following information can be recorded: OIB, Identification number, type, and name. 



 

 

 

