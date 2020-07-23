Classification of purchase documents functionality offers the ability to tag procurement documents with user defined values for the purposes of reporting. Code list for tag types enables the user to define any number of tag types for which corresponding tag values should be specified. Tags, added to purchase documents, serve as an additional classification in the business process, and transfer from one document to another, following the processing logic. 

# **Setup**
---

### **Tag type and value**

1. Go to **Procurement and sourcing > Setup > Classification of purchase documents > Tag type and value**
2. In the Tag type field, **create tag types** by entering tag type name, unique reporting value and order. Under each tag type create as many tag values as needed with reporting value and order priority. 

|Field|Description  |
|--|--|
|**Reporting value**  |identifier of tag type or tag value that is displayed on documents; max 5 characters allowed.  |
|**Order**  |specify the priority order in which the combination values are displayed on documents. Each tag type should have different order priority, each tag value for tag type should have different order priority.   |

3. Once a combination of tags is added to a purchase document, a **tag value combination** is created in the background. Neither tag type nor tag value can be deleted from the code list if they have already been used on a purchase document. 


### **Transfer setup**

1. Go to **Procurement and sourcing >Setup > Procurement and sourcing parameters > tab General > field Tag transfer control** 
2. Define the **options for tag transfers** between purchase documents when multiple documents with different tags are merged to one document:
   - If **parameter is set to Yes**: the union of tags is transferred to the new document, without the same values being repeated.
   - If **parameter is set to No**: no union of tags; tags do not transfer where multiple values would be created for one tag type; the user selects the value(s) for that tag type manually. 


