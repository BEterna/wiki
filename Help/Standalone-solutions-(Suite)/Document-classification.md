# Purpose

---

Classification of documents functionality offers the ability to tag documents in **Procurement, Project, and Fixed assets modules** with user defined values for the purposes of reporting. Code list for tag types enables the user to define any number of tag types for which corresponding tag values should be specified. Tags, added to documents, serve as an additional classification in the business process, and transfer from some documents to others, following the processing logic. 

# Setup 

---
## Tag type and value

Create new records under _Organization administration > Setup > Classification of documents > Tag type and value._ Available fields to populate:

|**Field**  | **Description** |
|---------------|---------------|
| **Tag type** | tag type name |
| **Reporting value** | unique identifier for tag type; is displayed on documents, max 10 characters allowed |
|  **Order**| priority order in which the combination values are displayed on documents; each tag type should have different order priority|
|  **Tag value**| under each tag type create as many tag values as needed with unique reporting values and order priorities  |
| **Tag module**| tag type with specified code list of values is available for selection only within modules that are defined in the **Enable for** tab
Once a combination of tags is added to a document, a tag value combination is created in the background. Neither tag type nor tag value can be deleted from the code list if they have already been used on a document. 


## Transfer setup for procurement documents
Navigate to _Procurement and sourcing > Setup > Procurement and sourcing parameters_ > tab General > field **Tag transfer control** to define the options for tag transfers between purchase documents when multiple documents with different tags are merged to one document:
- If parameter is set to **Yes**: the union of tags is transferred to the new document, without the same values being repeated.
- If parameter is set to **No**: no union of tags; tags do not transfer where multiple values would be created for one tag type; the user selects the value(s) for that tag type manually. 


# Use of document tags

---
Tags can be added to documents using button **Manage tags** in the Action pane. New dialog window opens where Tag value can be selected for each added Tag type. Once saved, the tag values for each type are displayed in the **Tag combination value** field in the document detail header, using reporting values. Separator between tag types is pipe sign: **|**.

For usage of tags in respective modules, see the following pages:
- [Procurement module](https://dev.azure.com/DynamicsUIM/D365UIM/_wiki/wikis/D365UIM.wiki/50/Procurement-module?anchor=tags-on-procurement-documents)
- [Project module](https://dev.azure.com/DynamicsUIM/D365UIM/_wiki/wikis/D365UIM.wiki/52/Project-module?anchor=tags-on-project-documents)
- [Fixed assets module](https://dev.azure.com/DynamicsUIM/D365UIM/_wiki/wikis/D365UIM.wiki/54/Fixed-assets-module?anchor=tags-on-documents-in-fixed-assets-module)

# Availability of tags in workflow configurations

---
Tag combination value is available in the following workflow configurations:
- Purchase order 
- Purchase requisition  
- Purchase agreement

# Availability of tags in data entities 

---

Tag types and values are available through Open in Excel functionality in Tag type and value code list. There are two new data entities for importing and/or exporting code list Tag type and value:
- Purchase documents tag types
- Purchase documents tag value

The following data entities are extended with TAGVALUECOMBINATION DISPLAYVALUE field:
- Purchase
  - Purchase requisitions V2 (PurchaseRequisitionHeaderV2Entity.AdPE) 
  - Purchase agreements V2 (PurchaseAgreementHeaderV2Entity.AdPE) 
  - Purchase order headers V2 (PurchaseOrderHeaderV2Entity.AdPE) 
  - Case detail (CaseDetailBaseEntity.AdPE)
- Projects
  - Project groups (ProjectGroupEntity)
  - Projects (ProjectEntity)
  - Project category group (ProjCategoryGroupEntity)
  - Project category (ProjectCategoryEntity)
- Fixed asset
  - Fixed asset groups (AssetGroupEntity)
  - Fixed assets (AssetFixedAssetEntity)


Following data entities are enabled for **data export only**, while for the others also import is enabled:
- Projects
  - Project posted transactions (ProjPostTransViewEntity)
