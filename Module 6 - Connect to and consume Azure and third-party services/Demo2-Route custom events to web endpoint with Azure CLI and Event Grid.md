<h1>Route custom events to web endpoint with Azure CLI and Event Grid</h1>

<h2>Introduction</h2>
<p>Azure Event Grid is an eventing service for the cloud. In this article, you will learn how to use the Azure CLI to create a custom topic, subscribe to the custom topic, and trigger the event to view the result. Typically, you send events to an endpoint that processes the event data and takes actions. However, to simplify you will send the events to a web app that collects and displays the messages.</p>

<h2>Prerequisites</h2>
<p>To perform this demo, you must need a valid Azure Subscription and some knowledge on Azure CLI and Event Grid.</p>

<h2>Steps:</h2>
<p>1. Open the command prompt and login with your Azure account by running the az login command.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-6-002/1.png"/>
<p>2. Once you login the Azure account, now create the resource group by using the following command.</p>
 <p>az group create --name Demo-Rg --location CentralUS</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-6-002/2.png"/>
<p>3. Now register the namespace using the following command.</p>
 <p>az provider register --namespace Microsoft.EventGrid</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-6-002/3.png"/>
<p>4. It will take some time register, to know the status of the registration use the following command.</p>
 <p>az provider show --namespace Microsoft.EventGrid --query "registrationState"</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-6-002/4.png"/>
<p>5. Once the registration is completed, now you will be creating Event Grid topic name by using the following command.</p>
 <p>az eventgrid topic create --name codesizzlerstopic -l CentralUS -g Demo-Rg</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-6-002/5.png"/>
<p>6. Now create a deployment in the Event Grid by using the following command.</p>
 <p>az group deployment create --resource-group Demo-Rg --template-uri "https://raw.githubusercontent.com/Azure-Samples/azure-event-grid-viewer/master/azuredeploy.json" --parameters siteName=codesizzlerssite hostingPlanName=viewerhost</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-6-002/6.png"/>
<p>7. Once you deployment is complete, now create a subscription in the Event Grid using the following command.</p>
 <p>az eventgrid event-subscription create --source-resource-id "/subscriptions/d04b00f4-8946-4d02-934c-c1d2a7c5e2d1/resourceGroups/Demo-Rg/providers/Microsoft.EventGrid/topics/codesizzlerstopic" --name demoViewerSub --endpoint https://codesizzlerssite.azurewebsites.net/api/updates</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-6-002/7.png"/>
<p>8. Once you create the subscription in the Event Grid, you can send an event to the topic by using the following command.</p>
 <p>endpoint=$(az eventgrid topic show --name $topicname -g gridResourceGroup --query "endpoint" --output tsv)</p>
 <p>key=$(az eventgrid topic key list --name $topicname -g gridResourceGroup --query "key1" --output tsv)</p>
<p>9. Once you are done clean up the resource by running the following command.</p>
<p> az group delete –-name Demo-Rg.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-6-002/8.png"/>

