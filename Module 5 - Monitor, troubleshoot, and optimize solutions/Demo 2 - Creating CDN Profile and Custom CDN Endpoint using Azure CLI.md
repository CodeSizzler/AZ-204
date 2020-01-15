<h1>Creating CDN Profile and Custom CDN Endpoint using Azure CLI</h1>

<h2>Introduction</h2>
<p>In this article you will understand, how to create a CDN profile and a Custom CDN Endpoint using Azure CLI. Azure Content Delivery Network (CDN) is a global CDN solution for delivering high-bandwidth content. With Azure CDN, you can cache static objects loaded from Azure Blob storage, a web application, or any publicly accessible web server, by using the closest point of presence (POP) server.</p>

<h2>Prerequisites</h2>
<p>To perform this demo, you must need a valid Azure Subscription and some knowledge on Azure Content Delivery Network (CDN) and Azure CLI.</p>

<h2>Steps:</h2>
<p>1. Login to your Azure using the following command in the CLI.</p>
  <p>az login</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-002/1.png"/>
<p>2. Now create a resource group using the following command.</p>
  <p>az group create -l CentralUS -n Codesizzler-RG</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-002/2.png"/>
<p>3. Now create a CDN profile using the following command.</p>
  <p>az cdn profile create --location CentralUS --name cdprofile --resource-group Codesizzler-RG --sku Standard_Verizon</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-002/3.png"/>
<p>4. Once you created the CDN profile, now create a CDN endpoint in the existing CDN profile using the following command.</p>
  <p>az cdn endpoint create -g Codesizzler-RG -n cdendpoint --profile-name cdprofile --origin www.codesizzlerdemocdn.com 88 4444</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-002/4.png"/>
<p>5. Now navigate to the Resource Group created, as result you can see the CDN profile and the CDN endpoint.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-002/5.png"/>
<p>6. Now select the CDN profile to view the CDN endpoint you have created.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-002/7.png"/>
<p>7. Once you are done, clean up the resource group using the following command.</p>
<p>az group delete –n codesizzler-RG</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-002/8.png"/>

