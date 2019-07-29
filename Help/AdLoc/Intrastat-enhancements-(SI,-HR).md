Intrastat is the system for collecting information and generating statistics about the trade of goods among countries/regions of the European Union (EU). Intrastat reporting is required whenever a product crosses the border of another EU country/region, whereas in several countries/regions, Intrastat reporting also applies to services. Mandatory and optional elements can be collected in Intrastat reporting. Most of the Intrastat functionality consists of standard D365 features. Some features, however are added in order to comply with the requirements of the Slovenian and Croatian local authorities. These localized enhancements are described in the following section.

-----

**EXCHANGE RATE**
 

In Croatia it is legally required to report foreign currency transactions converted into Croatian local currency (HRK), using the first valid exchange rate of Croatian national bank for the month in which Intrastat is required to be reported. This localization feature allows users to specify the adequate Exchange rate type in order to include the exchange rate calculation. When transferring transactions in foreign currency (other than HRK) to Intrastat journal, values are recalculated to accounting currency, using the specified Intrastat exchange rate.
ELECTRONIC REPORTING FORMATS Localization provides adequate Intrastat report file mappings (for Slovenia and Croatia), which enable users to generate Intrastat reports in accordance with the Slovenian and Croatian legislation, whereas the reporting format is standard.

-----
**INTRASTAT JOURNAL LINE STATUS**

Another localization feature is line status of transactions included to the Intrastat journal. With the localization added status allows lines in Intrastat journal to be available for editing until line status remains “Open”. Additionally, transactions can be filtered based on this status.

-----
**REPORTING HISTORY**

Feature enables reviewing historically created Intrastat declaration (and in these declarations included transactions). Additionally, it enables a generation of replacement declarations regarding past reporting periods, for which Intrastat declarations have already been submitted. Status of the reported transactions can be set back to “Open”, and then replacement declaration can be created for each of the reports from reporting history. This can be useful if changes have been made in connection with transactions, which have already been declared through Intrastat. In this case, replacement declarations can be created, with the updated transactions reporting period.

-----
**INTRASTAT ARCHIVE**

Enables users to review transactions, which have been compressed by parameters (compression is standard feature, while the review of compressed transactions is localized feature). Localization functionality also ads option to transfer the compressed transactions back to Intrastat journal in their original state (before compression) when applicable.

-----

[Detailed documentation](http://axweb/D365O%20Localization%20Documents/D365O%20LOC_Intrastat.docx?Web=1)