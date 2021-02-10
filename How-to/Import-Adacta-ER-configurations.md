There is a number of configurations that were developed as part of different Adacta solutions. Some of them are dependent on standard MS configurations. Therefore it is important to import configurations in **following order**:

Step 1: Generate new **Configuration provider Adacta** >  Go to Add and enter Name = Adacta; Internet address = http://www.adacta-group.com

Step 2: Add new Configuration repository.  
- To add new Microsoft repository go to **Workspaces > Electronic reporting > Configuration providers > Microsoft > Repositories > Add** and choose Operation resources repository.
- To add new Adacta repository go to **Workspaces > Electronic reporting > Configuration providers > Adacta > Repositories > Add** and choose one of Adacta repositories. Repeat for each repository.

Step 3: Import Microsoft configurations from **Operations resources repository**. Go to **Workspaces > Electronic reporting > Configuration providers > Microsoft > Repositories >  Operations resources**. Following MS configurations need to be imported first:


|**Configuration**| **Version** |
|--|--|
|EU Sales list model | 1 |
|Intrastat model |1  |
|ISO20022 Credit transfer |1.1  |
|Ledger accounting reports  | 1 |
|Payment model  | 1 |

Step 3: Import Adacta configurations from **Adacta repository**. There are separate repositories available for each package. Import  repositories for the packages you are using. 
1. Go to  **Workspaces > Electronic reporting > Configuration providers > Adacta > Repositories** > pick repository according to install packages. Available repositories: 

- Adacta localization
- Adacta localization (Bank)
- Adacta localization (Fiscalization)
- Adacta Suite (Dunning)

1. Cklick **Open**
1.Choose option **Import all** to import all configurations for selected repository or Select specific configuration and click **Impor**t under Versions option in cases when specific configuration needs to be refreshed.  



