This section, summarizes additional General Ledger features, which are part of the LOC_LEDGER extended localization package.

-----

#Journalize tax as parent line

This extended localization functionality enables posting tax to the same offset account as the line from which the tax is derived. Journalizing tax as parent line is available only if posting definitions are enabled. If “Journalize tax as parent line” option is enabled, tax is always posted with the same offset account as the original line from which the tax is derived.

[Detailed documentation](https://adacta.sharepoint.com/:w:/r/sites/ERP-Product-Development/Shared%20Documents/D365FO%20Localization%20documentation/D365O%20LOC_Additional%20GL%20setup.docx?d=w4bed79a4660e42aeb9f6ab0914109744&csf=1&e=6LGcEV)

-----
#Year-end procedure enhancements

Functionality enables balancing Main account balance with Ledger account balance in order to avoid opening transactions in cases where Ledger account balance equals zero and Main account balance does not. Feature is useful if at the end of the year a different balance on each main account - financial dimension combination s remains, while balance for the same main account (combining all the dimensions) is zero.

This extended localization feature enables a proposition for balancing General Ledger transactions from General journal. As result, journal lines with settlement proposals are generated. After journal is posted, balance on both, Ledger account and Main account, is zero.

[Detailed documentation](https://adacta.sharepoint.com/:w:/r/sites/ERP-Product-Development/Shared%20Documents/D365FO%20Localization%20documentation/D365%20ext%20LOC_Opening%20transactions.docx?d=we67640e06b9c4c3f8474e13701abddbe&csf=1&e=QrZuQ8)

-----