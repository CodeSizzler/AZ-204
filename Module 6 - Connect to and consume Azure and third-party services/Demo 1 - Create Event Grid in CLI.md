<h1>Create Event Grid in CLI</h1>

<h2>Introduction</h2>
<p>In this article you will understand how to create an event grid using CLI. Event Grid is a fully managed event service that enables you to easily manage events across many different Azure services and applications. Made for performance and scale, it simplifies building event-driven applications and serverless architectures.</p>

<h2>Prerequisites</h2>
<p>To perform this demo, you must need a valid Azure Subscription and some knowledge on Azure Event Grid, CLI and Command Prompt.</p>

<h2>Steps:</h2>
<p>1. Log-in to Azure portal with your account using www.portal.azure.com. In command Prompt login to your CLI using az login. Now create a resource group in the command prompt using the following command.</p>
   <p>az group create --name "codesizzler_rg" --location "CentralUS"</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-6-001/1.png"/>
<p>2. Once you create the resource group you have to register the Microsoft Event Grid. Now register your Microsoft with the following command.</p>
   <p>az provider register --namespace "Microsoft.EventGrid"</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-6-001/2.png"/>
<p>3. Once the registration is completed you have to create the event grid in the command prompt using the following command.</p>
   <p>az eventgrid topic create --name codesizzlereventgrid -l CentralUS -g codesizzler_rg</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-6-001/3.png"/>
<p>4. Now create the eventhub namespace in the command prompt using the following command.</p>
   <p>az eventhubs namespace create --name codesizzlernamespace --resource-group codesizzler_rg</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-6-001/4.png"/>
<p>5. Once you created the eventhub namespace you have to create a hub in the command prompt using the following command.</p>
   <p>az eventhubs eventhub create --name codesizzlerhub --namespace-name codesizzlernamespace --resource-group codesizzler_rg</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-6-001/5.png"/>
<p>6. Once the namesapace hub is created, now use the following command to create the event subscription.</p>
   <p>az eventgrid event-subscription create --topic-name codesizzlereventgrid -g "codesizzler_rg" --name subtoeventhub --endpoint-type eventhub --endpoint "/subscriptions/b3abd624-6c8c-4830-bf7d-7fefae4c714c/resourceGroups/codesizzler_rg/providers/Microsoft.EventHub/namespaces/codesizzlernamespace/eventhubs/codesizzlerhub"</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-6-001/6.png"/>
<p>7. Now send an event to the custom topic using the following command.</p>
   <p>az eventgrid topic show --name codesizzlereventgrid -g codesizzler_rg --query "endpoint" --output tsv</p>
   <p>az eventgrid topic key list --name codesizzlereventgrid -g codesizzler_rg --query "key1" --output tsv</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-6-001/7.png"/>
<p>8. Now navigate to the Azure portal to view the EventGrid you have created.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-6-001/8.png"/>

