Technical assets can have a relation to **Project categories** in D365FO, which are used for posting Expense transactions to a project. TechAssetCategory API creates or updates this relation. It can insert records, when unique combinations do not exist yet or update existing records in D365FO. After successful inserts or updates of records in the Technical asset project category relation table, an output is provided from D365FO to the 3rd party system. When inserts or updates fail, the error message is provided to the 3rd party system.

Each technical asset can be related to several different project categories, if it meets the following requirements:
- the combination Technical asset – Unit of Measure is unique,
- the combination Technical asset – Project category – Unit of Measure is unique.

This means that technical asset can be related to only one project category with the same unit of measure. If unit of measure differs for the same technical asset, such record can be related also to different project category. Updates are possible only for the Category field if the combination Technical asset – Unit of Measure already exists within the system. 

For example (values of following combinations represent Technical asset – Category - Unit):
1.	we have existing record in the system with combination TA001 – Fuel – ltr
2.	we can insert new record with combination TA001 – Fuel – km (or e.g. TA001 – Car Rental – km)
3.	we can not insert another new record with combination TA001 – Car Rental – ltr as combination TA001 - - ltr already exists in the system, but such record can be updated.

The technical asset category relation form in D365FO IM package for specific project is located in **Project management and accounting > Projects > Setup > Technical assets > Technical assets project category relation**.

