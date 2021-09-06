# AzurePurview: Role Assignments for Purview Account's Root collection using PowerShell

This article helps to provide role assignment for Azure Purview account using PowerShell.

### Prerequisites

> * [Create an Azure Purview account in the Azure portal](https://docs.microsoft.com/en-us/azure/purview/create-catalog-portal).
> * You need Powershell v7.x.x to use this tool. Please [Download and upgrade your Powershell to v7](https://docs.microsoft.com/en-us/powershell/scripting/install/installing-powershell-core-on-windows?view=powershell-7.1).
> * Download and extract [Purview-API-Powershell.zip](https://github.com/Azure/Azure-Purview-API-PowerShell/blob/main/Purview-API-Powershell.zip) to a folder of your choice.

### Steps to launch Azure Purview API via PowerShell

1. Open PowerShell 7 and Run As Administrator
    ![image](https://user-images.githubusercontent.com/79183421/132214896-4cca3fcb-4da6-469a-b9e9-a2c94a3f231c.png)
2. Navigate to the folder where you have previously downloaded and extracted the Purview-API-PowerShell.
    ![image](https://user-images.githubusercontent.com/79183421/132217257-f6782816-62b5-49ee-9741-fa9f07db3638.png)
3. Run "Purview-API-PowerShell.exe" and enter the name of the Azure Purview account.
    ![image](https://user-images.githubusercontent.com/79183421/132217527-794dfab9-a656-469e-85f7-3192bb71383f.png)

### How to use Azure Purview API via PowerShell 

You can choose the below options to use the Azure Purview API.

 1. [G] GUI - Interactive Assistance On Help, Usage & Syntax of Purview APIs
    You can use this option to run the query with the helps of GUI. 
    ![image](https://user-images.githubusercontent.com/79183421/132218432-096fd131-3d41-4882-b4c3-bde907758d6c.png)
 2. [T] Text Mode - Enter API Command(s) Manually
    You can use this option to run the query manually by selecting the options available. 
    ![image](https://user-images.githubusercontent.com/79183421/132218944-7e2a50ba-f2e4-42a7-8942-961a9c142439.png)
 3. [Q] Quit
    ![image](https://user-images.githubusercontent.com/79183421/132219149-215ed738-5b25-40f1-b16d-9e702e27e4bc.png)

### How to provide the Role Assignments for Purview Account's Root collection using PowerShell

1. Get the details about the Service Principal/user which you want to add to the role assignment for Purview accounts root collections. 
> * For Users go to Azure Active Directory => users => search user => Click on profile => Copy the ObjectID
   ![image](https://user-images.githubusercontent.com/79183421/132221458-98ba082e-136c-481f-8644-384130fb31ee.png)
> * For Service Principal go to Azure Active Directory => Enterprise applications => Search application => Copy the ObjectID
   ![image](https://user-images.githubusercontent.com/79183421/132221769-78c5ed2a-527a-4962-866e-b41abe5da01c.png)
2. Get the details about the metadatapolicy by choosing the GET method => `readAllMetadataPolicies` command
    ![image](https://user-images.githubusercontent.com/79183421/132219657-05cd22d6-d23c-4433-a66f-d06dc07b7510.png)
3. Copy the enter API Response Recieved. 
    ![image](https://user-images.githubusercontent.com/79183421/132220256-9fe0f3ef-380f-4e64-a6d9-bc002c20e637.png)
4. Now paste enter API response in the file name "purview-api-body-payload.json" available in the extracted directory. 
> !Note:  The file "purview-api-body-payload.json" extracted in the same directory contains the API Body to be sent in case of PUT or POST APIs. Make sure to blank the file first, update your JSON into it and save the file before executing any "PUT" or "POST" APIs. If you need to back up your previous JSONs, you may do so in a different file name, since this file name "purview-api-body-payload.json" is reserved for the next upcoming API call.
5. Add the user/service principal objectID to the "purview-api-body-payload.json" and save.
    ![image](https://user-images.githubusercontent.com/79183421/132222221-9b5031e5-bc6d-4c0f-add2-893347b4ce87.png)
6. Go back to the PowerShell and select `G` and choose the PUT method => `putMetadataPolicy` command
    ![image](https://user-images.githubusercontent.com/79183421/132222703-0ed8526c-c274-4021-a529-1a00ff2d2eb2.png)
7. 



