ProjActivationProposal API **creates or updates header of the Project activation proposal document** in the Project activation proposal (to fixed asset or to project) table. 

We differentiate two types of Project activation proposals based on the Activation type (which cannot be updated):
- **Project**: for transferring transactions from implementation projects (i.e. project subtype) to investment projects (i.e. project subtype) using project linking and project category mapping.
- **Fixed asset**: for capitalization/activation of WIP investment project transactions to fixed assets.

This API allows **inserting records when the Document ID does not yet exist** in D365FO, otherwise it updates existing Project activation proposal. After successful inserts or updates of records in the Project activation proposal table, an output is provided from D365FO to the 3rd party system. When inserts or updates fail, the error message is provided to the 3rd party system.

Additional validations during insert and update of records are:
- Update of Project activation proposal can be done only when the document is in the status **Draft**
 - When inserting new record, validation of Activation type is following:
   - Fixed asset – specified Project ID must have the **Investment** project subtype
   - Project – specified Project ID must have the **Implementation** project subtype
- **Update** is possible only for the following fields: 
  - Activation date
  - Note

