<h1>Create a Service Bus Namespace and Queue in Azure CLI</h1>

<h2>Introduction</h2>
<p>In this article you will learn how to send and receive messages with Service Bus by using the Azure CLI. Service Bus queues support a brokered messaging communication model. When using queues, components of a distributed application do not communicate directly with each other; instead they exchange messages via a queue, which acts as an intermediary (broker).</p>

<h2>Prerequisites</h2>
<p>To perform this demo, you must need a valid Azure Subscription and some knowledge on Azure CLI and Service Bus.</p>

<h2>Steps:</h2>
<p>1. Log-in to Azure portal with your account using www.portal.azure.com. Select the cloud shell button on the top right menu bar in the Azure portal.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-6-003/1.png"/>
<p>2. Once you open the Cloud Shell, now create the Resource Group using the following Bash command.</p>
 <p>resourceGroupName="codesizzler_rg"</p>
 <p>az group create --name $resourceGroupName --location CentralUS</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-6-003/2.png"/>
<p>3. Now create a service bus namespace with the unique name by using the following command.</p>
 <p>namespaceName=codesizzlerNameSpace$RANDOM</p>
 <p>az servicebus namespace create --resource-group $resourceGroupName --name $namespaceName --location CentralUS</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-6-003/3.png"/>
<p>4. Now create a service bus queue by using the following command.</p>
 <p>az servicebus queue create --resource-group $resourceGroupName --namespace-name $namespaceName --name BasicQueue</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-6-003/4.png"/>
<p>5. Once you create the service bus queue, now get the connection strings using the following command.</p>
 <p>connectionString=$(az servicebus namespace authorization-rule keys list --resource-group $resourceGroupName --namespace-name $namespaceName --name RootManageSharedAccessKey --query primaryConnectionString --output tsv)</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-6-003/5.png"/>
<p>6. Now use the following command to create a container in Azure. Select the YAML file you added earlyNow clone the Service Bus GitHub repository on your computer by issuing the following command.</p>
 <p>git clone https://github.com/Azure/azure-service-bus.git</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-6-003/6.png"/>
<p>7. Once the clone is done, now change your current directory to the sample folder, using forward slashes as path separators with the following command.</p>
 <p>cd azure-service-bus/samples/Java/azure-servicebus/QueuesGettingStarted</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-6-003/7.png"/>
<p>8. Now run the following command to build the application. It will take few minutes to build the application.</p>
 <p>mvn clean package -DskipTests</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-6-003/8.png"/>
<img src="https://codesizzlergit.blob.core.windows.net/az203-6-003/9.png"/>
<p>9. Now run the program, issue the following command after replacing the connection string with the value you copied earlier.</p>
 <p>mjava -jar ./target/queuesgettingstarted-1.0.0-jar-with-dependencies.jar -c "<Endpoint=sb://codesizzlernamespace14090.servicebus.windows.net/;SharedAccessKeyName=RootManageSharedAccessKey;SharedAccessKey=zfNwoRSo6HcBCHb0NZWDHYjPEHLcXK6PXz07AZRIEyI=>"</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-6-003/10.png"/>
<p>10. Once you run the application you will get the following result.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-6-003/11.png"/>

