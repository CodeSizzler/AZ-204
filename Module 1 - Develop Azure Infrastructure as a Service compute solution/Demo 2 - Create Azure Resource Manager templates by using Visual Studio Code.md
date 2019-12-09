<h1>Create Azure Resource Manager templates by using Visual Studio Code</h1>

<h2>Introduction</h2>
<p>In this article you will learn how to use Visual Studio code and the Azure Resource Manager Tools extension to create and edit Azure Resource Manager templates. In this demo you will deploy a storage account.</p>

<h2>Prerequisites</h2>
<p>To perform this demo, you must need a valid Azure Subscription and some knowledge in Visual Studio Code, Azure Resource Manager (ARM) and Templates.</p>

<h2>Steps:</h2>
<p>1. Open the visual studio code and the follow the steps to install the ARM tool.</p>
	 <p>�	Press CTRL+SHIFT+X to open the Extensions pane.</p>
     <p>�	Search for Azure Resource Manager Tools, and then select Install.</p>
     <p>�	Select Reload to finish the extension installation.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-002/1.png"/>
<p>2. Now open the template in the visual studio code, navigate to open files in the file tool bar. Navigate to the below link, download the template file save it to your local machine and then open the downloaded template in the Visual Studio Code</p>
 <p>https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/101-storage-account-create/azuredeploy.json</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-002/2.png"/>
<img src="https://codesizzlergit.blob.core.windows.net/az203-002/2.1.png"/>
<img src="https://codesizzlergit.blob.core.windows.net/az203-002/2.2.png"/>
<p>3. Once the file is opened save the file as azuredeploy.json to your local computer.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-002/3.png"/>
<p>4. Now navigate to the portal and then open powershell to run the template.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-002/4.png"/>
<p>5. Now upload the file to the powershell.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-002/5.png"/>
<p>6. Once you uploaded the file, now you can optionally use the ls command to verify the file is uploaded successfully.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-002/6.png"/>
<p>7. Now create a resource group in a valid location using the following command.</p>
  <p>$resourceGroupName = Read-Host -Prompt "Enter the Resource Group name"</p>
  <p>$location = Read-Host -Prompt "Enter the location (i.e. centralus)"</p>
  <p>New-AzResourceGroup -Name $resourceGroupName -Location "$location"</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-002/7.png"/>
<p>8. Once you created the resource group, now update the template file you have save early by using the following command.</p>
<p>New-AzResourceGroupDeployment -ResourceGroupName $resourceGroupName -TemplateFile "$Home/azuredeploy.json"</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-002/8.png"/>
<p>9.The storage account name and the storage URL in the outputs section are highlighted on the screenshot. You need the storage account name in the next step.</p>
<p>Now run the following command in the powershell to list the newly created storage account</p>
  <p>$resourceGroupName = Read-Host -Prompt "Enter the Resource Group name"</p>
  <p>$storageAccountName = Read-Host -Prompt "Enter the Storage Account name"</p>
  <p>Get-AzStorageAccount -ResourceGroupName $resourceGroupName -Name $storageAccountName</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-002/9.png"/>
<p>10. Once you are done clean up the resource group.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-002/10.png"/>

