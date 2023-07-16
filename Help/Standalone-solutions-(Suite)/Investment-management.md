Investment management package provides a set of industry specific functionalities meant for companies where assets, their construction and maintenance, present the backbone of their business. These functionalities are implemented as part of three modules in D365FO:
- Project management and accounting 
- Inventory management
- Fixed assets

Investment management process within D365FO start with creating project including project hierarchy of type Investment. Once we have created projects, we can continue with adding work breakdown structures, forecasts or project budget and other data, if required. Investment management provides also possibility to define Sort fields in hierarchy, project purpose, financial types with amounts and relation to technical assets. When we have completed entering project information, we can set project stage to 'In process'.

Throughout lifecycle of a project we are spending hours, expenses, items and fees on project. These are posted as project transactions. If consumption is being tracked in external systems, Investment management integration layer is provided to receive these records also within D365FO. For handling of item returns or item consumption, Investment management provides automated process that is described in more details in following chapters.

When we have completed a project or a phase of a project (e.g. some fixed assets have been built), we can activate project to fixed assets. For this purpose, Investment management brings the Project activation proposal document with several advantages comparing to standard elimination functionality:
- 	More than one FA can be capitalized per project
- 	Project does not have to be fully completed in order to capitalize it partially
- 	Write-up adjustments are posted automatically
- 	Forecast model is not necessary to transfer project WIP (work in progress) costs to FA
- 	User does not have to create fixed assets before capitalizing project costs to FA.

After activation of fixed assets, we can finally set stage of projects to Finished. Following chapters provide detailed information about Investment management process within D365FO.
