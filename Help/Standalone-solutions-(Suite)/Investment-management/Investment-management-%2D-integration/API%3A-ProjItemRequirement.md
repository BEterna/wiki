ProjItemRequirement API creates **new item requirements for a specific project** in the Project item requirements table in D365FO. It enables only inserts. After successful inserts of records in the Project item requirements table, an output is provided from D365FO to the 3rd party system. When inserts fail, the error message is provided to the 3rd party system.

All fields in the data entity are non-mandatory, but they are validated during the input process according to setup in D365FO (required inventory dimensions, project category). If an input parameter in the request is linked to a code list, the input value for such a parameter must already exist in D365FO code list. Nevertheless, some fields must be always provided in the input request, so that Item requirement line is created in the D365FO:
- Project ID
- Item number
- Site
