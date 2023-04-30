The purpose of this functionality is to provide a document as an alternative to fixed asset journal, that:
-	has all the benefits as journals (document numbering, workflow, etc.),
-	cannot be deleted with a cleaning job after it is posted,
-	can be reversed,
-	is limited only to disposals of fixed assets.

Companies that deal with assets of higher value (e.g. infrastructure) often need to keep records of documents that relate to asset acquisition and disposal. These documents need to be available for the entire asset service life, which can last several years or even decades. The disposal document is therefore a document through which users can perform fixed asset disposal (sale, scrap or partial disposal) and register the document itself as a business document in D365FO.
This functionality also enables disposing multiple fixed assets throughout a single document. Disposal document offers three transaction types – Disposal – sale, Disposal – scrap and Partial disposal – scrap. Transaction types are added to disposal groups, which are selected on the Disposal document header. 

# **Setup**
---

### **Fixed asset parameters**
1. Go to **Fixed assets > Setup > Fixed assets parameters** 
2. Select **Number sequence** tab: number sequence code must be selected for Disposal document
3. Select **Disposal documents** tab:
   - Name of Journal: select name of journal to be used for asset disposal (this name is used for creating a temporary fixed assets journal which is used to post asset disposal document).
   - Create disposal document for Write off – Disposal documents: refers to [Fixed asset counting](/Help/Standalone-solutions-\(Suite\)/Fixed-assets-management/Fixed-Assets-counting). When set to **Yes** a disposal documents is generated for all write-offs from the counting process, otherwise a fixed asset journal is generated.

### **Asset disposal groups**
With Asset disposal groups setup, users can define their own ways of grouping disposal documents and define which disposal transaction are allowed for a selected group.
1. Go to **Fixed assets > Setup > Assets disposal groups > New** 
2. Enter the following values:
   - Disposal group: name of the disposal group
   - Description: description of the disposal group
   - Reason code: reason code that will be defaulted for a selected disposal group on the disposal document
   - Reason comment: reason comment that will be defaulted for a selected disposal group on the disposal document
   - Transaction types: select transaction types that will be available within the disposal group 


# **Create Disposal document**
---
Disposal documents are created in **Fixed assets > Disposal documents > Asset disposal documents > New**. Following the above-described procedure, a new form opens, where users can enter the following information:
1. Disposal header:
   - Description: disposal document description
   - Date: posting date
   - Disposal group
   - Disposal document: populated automatically based on the number sequence setup
   - Status: populated automatically based on the workflow status
   - Approved: populated automatically based on the workflow status
   - Reason code and Reason comment are populated automatically based on the Disposal group setup, but can be changed by the user
2. Disposal lines (each line needs to represent one fixed asset that will be disposed with the disposal document): 
   - For disposal type Disposal:
      - Description (optional)
      - Currency
      - Amount in transaction currency
      - Offset account type (most often Customer)
      - Offset account: account based on the Offset account type selection (e.g. if Offset account type is “Customer”, select Customer ID in Offset account field)
   - For disposal type Disposal:
      - Description (optional)
      - Offset account type is “Ledger”
   - For disposal type Partial disposal:
      - Description (optional)
      - Disposal percent
      - Offset account type is “Ledger”

**Note**: Fixed assets can be added one by one (button New) or massively with the function Propose lines. 

**Note**: More details about each line can be found under **Line details** tab where an overview per line and possibility to change Financial dimensions of the fixed asset are available.
 
# **Disposal document results**
---
Disposal document is posted by clicking the button **Post**. Fixed asset transactions are generated. Posted transactions can be checked on each fixed asset. Each transaction type is posted in the same way as throughout fixed asset journal.

# **Disposal document workflow**
---
A new workflow for Disposal document is available under **Fixed assets > Setup > Fixed assets workflows**. Configuration of the workflow for Disposal document is based on the standard workflow configuration with some adjustments.

**Actions** provided within the **Review task**:
- Accept: this is the action that appears when review task comes to more users. User who clicks accept, takes the review task to himself.
- Complete: this action finishes review task, workflow stays in status In review and goes to the next step.
- Request chang: Status of the document: Change requested. Document can be edited. Workflow submitter has following options: Resubmit, Recall, View history.
- Return: the identical action as Request change
- Delegate: delegate the document to somebody else. 

**Actions** provided within the **Approval task**:
- Approve:  approve the document
- Delegate: delegate the document to somebody else
- Request change: Status of the document: Change requested. Document can be edited. Workflow submitter has following options: Resubmit, Recall, View history.
- Deny: Status of the document: Draft. After this action, workflow is returned to the Draft status and workflow is completed. When the workflow is completed, workflow originator cannot check the workflow history in Common > Inquiries > Workflow > Workflow history. Workflow originator can start workflow again from the beginning by clicking the option Submit. Once the new workflow is started, all workflows connected to the specific document can be checked by clicking the button View History.

**Action Recall** is the option available to the workflow originator to stop the workflow at any time. Document goes back to status Draft and the document can be changed.

# **Disposal document data entities**
---
Disposal document has two different data entities: 
- **Asset disposal documents**: provides the list of all Disposal documents.
- **Asset disposal document lines per header**: enables importing and editing Disposal document lines per header and prevents publishing invalid data (e.g. Customer account cannot be published for Disposal – scrap transaction).
