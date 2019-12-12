<h1>Using Key Vault to Encrypt data with SQL Database</h1>

<h2>Use Case: </h2>
<p>In this article you will learn about encrypting data using Azure Key Vault in Azure SQL Database.</p>

<h2>Prerequisites</h2>
<p>To perform this demo you must have valid Azure subscription and some basic knowledge on Azure Key Vault and SQL Database.</p>

<h2>Steps:</h2>
<p>1. Open the command prompt and run the az login command to login with your Azure account. When you run the command a pop-up window will get opened and it will ask you to provide your Azure account credentials. After logging in run the following command to create a resource group.</p>
    <p>az group create --name "Codesizzler-Rg" --location CentralUS</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-4-003/1.png"/>
<img src="https://codesizzlergit.blob.core.windows.net/az203-4-003/2.png"/>
<p>2. After creating the resiurce group run the following command to create a Key Vault.</p>
    <p> az keyvault create --name "codesizzlerkeyvault" --resource-group "Codesizzler-Rg" --location CentralUS</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-4-003/3.png"/>
<p>3. Run the following command to store a secret value in the Key Vault.</p>
    <p>az keyvault secret set --vault-name "codesizzlerkeyvault" --name "WhatWeAre" --value "Cloud Consultant"</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-4-003/4.png"/>
<p>4. Run the following command to show the secret value.</p>
    <p> az keyvault secret show --name "WhatWeAre" --vault-name "codesizzlerkeyvault"</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-4-003/5.png"/>
<p>5. After creating the Key Vault navigate to Azure portal and create a blank SQL Database. Click on create a new resource and under the data category select the SQL Database.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-4-003/6.png"/>
<img src="https://codesizzlergit.blob.core.windows.net/az203-4-003/7.png"/>
<p>6. When it prompts configure the required settings as shown the below image. For the server create a new one and click on Review + Create.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-4-003/8.png"/>
<img src="https://codesizzlergit.blob.core.windows.net/az203-4-003/9.png"/>
<p>7. Then click on create.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-4-003/10.png"/>
<p>8. Once the deployment competes navigate to the created resource.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-4-003/11.png"/>
<p>9. You will need the connection string later in the tutorial, so after you create the database, database and copy the connection string. You can get the connection string at any time, but it's easy to copy it in the Azure portal. Go to SQL databases > Keyvaultdatabase > Show database connection strings. Go to SQL databases > Keyvaultdatabase > Show database connection strings.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-4-003/12.png"/>
<p>10. Open SSMS. (Go to Connect > Database Engine to open the Connect to Server window if it isn't open.)</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-4-003/13.png"/>
<p>11. Enter your server name and credentials. The server name can be found on the SQL database. For user name and password provide the one which have given while deploying the SQL Server.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-4-003/14.png"/>
<p>12. Expand Databases Right click keyvalutdatabase and click a New Query button.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-4-003/15.png"/>
<p>13. Expand Databases>Keyvalutdatabas Right-click the Patients table and select Encrypt Columns to open the Always Encrypted wizard.</p>
 <p>Copy past the script form here - http://bit.ly/SQLKeyVault and click on execute.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-4-003/16.png"/>
<p>14. When it prompts click on next.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-4-003/17.png"/>
<p>15. Encrypt SSN and BirthDate information for each patient. The SSN column will use deterministic encryption support operations and Set the Encryption Type for the SSN column to Deterministic and the BirthDate column to Randomized Click Next.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-4-003/18.png"/>
<img src="https://codesizzlergit.blob.core.windows.net/az203-4-003/19.png"/>
<p>16. When you click on next it will ask for your Azure account creadentials.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-4-003/20.png"/>
<p>17. After that select Azure Key Vault. Select the desired key vault from the drop-down list.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-4-003/21.png"/>
<p>18. Run setting blade choose on Proceed to finish now and click on next button.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-4-003/22.png"/>
<p>19. Verify that the settings are all correct and click Finish to complete the setup.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-4-003/23.png"/>
<img src="https://codesizzlergit.blob.core.windows.net/az203-001/24.png"/>
