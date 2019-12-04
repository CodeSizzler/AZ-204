<h1>Create two Storage Account using Azure CLI</h1>

<h2>Introduction</h2>
<p>The Azure command-line interface (CLI) is Microsoft's cross-platform command-line experience for managing Azure resources. The Azure CLI is designed to be easy to learn and get started with, but powerful enough to be a great tool for building custom automation to use Azure resources. In this article you will learn how to use Azure CLI to create storage account.</p>

<h2>Prerequisites</h2>
<p>To perform this demo, you must need a valid Azure Subscription and some knowledge on Azure Storage Account, CLI and Command Prompt.</p>

<h2>Steps:</h2>
<p>1. Log-in to Azure portal with your account using www.portal.azure.com. In command Prompt login to your CLI using az login command. Once you login your Azure CLI in the command prompt you are ready to create a storage account.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-3-003/1.png"/>
<p>2. Now create a resource group and a storage account by using the following command</p>
<p>az group create -l CentralUS -n codesizzler_rg</p>
<p>az storage account create --location "CentralUS" --name "democodesizzlerstorage" --resource-group "codesizzler_rg" --sku "Standard_GRS"</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-3-003/2.png"/>
<p>3. Now create another storage account using the following command</p>
<p>az storage account create --location "CentralUS" --name "codesizzlerdemostorage" --resource-group "codesizzler_rg" --sku "Standard_GRS"</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-3-003/3.png"/>
<p>Once you create the two storage account in the CLI, now navigate to the portal to view the storage account that you created using Azure CLI.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-3-003/4.png"/>
