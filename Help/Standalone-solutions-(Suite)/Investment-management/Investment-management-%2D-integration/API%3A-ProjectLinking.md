Project linking is used to link different projects which are not in the same project hierarchy (e.g. mapping implementation to investment projects). ProjectLinking API creates records in **Projects linking** table. It inserts records, when the combination of Implementation project – Investment project does not exist yet in D365FO. **Updates are not available**, but it is possible to delete existing record. 

After successful inserts of records in the Projects linking table, an output is provided from D365FO to the 3rd party system. When inserts fail, the error message is provided to the 3rd party system.

The project linking form in D365FO IM package is located in **Project management and accounting > setup > Projects > Projects linking**.