#Tags on Project documents 
---

The following entities in Project module facilitate tags functionality:
- Project
- Project group 
- Project category
- Project category group

Tag combination value column, which is available for filtering, is **added to the list pages** of Projects and Posted project transactions. 

Tag combination value in the **Posted project transactions** list page in two separate columns: Project tag and Category tag. Project tag displays a tag combination value that is added on a project on which a transaction is posted. Category tag displays a tag combination value that is added on the project category used for posting a transaction.

# Tag transfer between documents 
--- 
Rules for transferring tags in the **Project management and accounting** module are following:
- **Project group > Project** – all tags from a project group are defaulted to a project upon the project creation and can be modified on Project. If subproject is being created, tags are always transferred from parent project.
- **Project category group > Project category** – all tags from a project category group are defaulted to a project category upon the project category creation and can be modified on Project category. 
- **Project > Project transaction** – all tags from a project are displayed on the Posted project transaction in the Project tag column.
- **Project category > Project transaction** – all tags from a project category are displayed on the Posted project transaction in the Category tag column.

Changing tags on project group does not reflect on already created projects. Changing tags on project category group does not reflect on already created project categories.

Project tags and Category tags on Posted project transactions are display values and cannot be edited. Project tags and Category tags on project transactions are showing the latest tag combination values from projects/project categories.
