# Registration ID features (SI, HR, RS)

-----
In order to comply with locally used registration IDs (e.g. tax and identification numbers), additional registration categories are added with this localization feature and need to be setup for the adequate Registration IDs to allow other localized features to work correctly - e.g. REK reporting and eInvoices use Registration IDs with the localized registration categories for validation purposes. If inadequate registration categories are used for the set-up of registration IDs, validation when using other localized features may fail, while the required ID may also be missing from other documents, therefore localized registration categories should be used.

Standard functionality of Registration IDs is used for VAT ID, tax identification numbers, Company registration numbers and National identification numbers for Slovenia, Croatia and Serbia. Users can set up the registration IDs with the localized registration categories for customers, vendors, workers, and legal entities. Localization features are the additionally added registration categories, upon which also locally specific validation of format and structure is enabled.

[Detailed documentation](http://axweb/D365O%20Localization%20Documents/D365O%20LOC_Tax%20identification%20number.docx?Web=1) (chapters 1.1 – 1.4.1)

-----
#Tax exempt number validation (SI, HR)

Standard D365 features allow for the validation of Tax exempt numbers formats. However, by standard, format validation is not available for Slovenian or Croatian Tax exempt numbers and is added with this localization feature.

Localization feature offers a validation of Tax exempt number also for Slovenia and Croatia (8 digits for Slovenia and 11 for Croatia). Validation for each of these countries can be enabled or disabled by the authorized users. If validation is enabled, upon entering a tax exempt number with inadequate format, a warning is displayed.

[Detailed documentation](http://axweb/D365O%20Localization%20Documents/D365O%20LOC_Tax%20identification%20number.docx?Web=1) (chapter: 1.5.2)

-----
#OIB validation (HR)

This topic provides country/region-specific information about the Croatian tax number (OIB) format and structure validation. OIB (Osebni identifikacijski broj) is used in Croatia as tax identification number. Standard D365 feature does not allow for OIB format validation, therefore validation is added in scope of this localized feature.

Localization feature enables OIB number entry in Croatian taxable persons (localized) form and automatically validation in terms of the official OIB format and structure (11 digits). If entered OIB number does not pass the validation, a warning is displayed.

[Detailed documentation](http://axweb/D365O%20Localization%20Documents/D365O%20LOC_Tax%20identification%20number.docx?Web=1) (chapter: 1.5.1)