<h1>Azure Cosmos DB: Develop with the Table API in .NET</h1>

<h2>Introduction</h2>
<p>Azure Cosmos DB is Microsoft’s proprietary globally-distributed, multi-model database service "for managing data at planet-scale". In this demo you are going to learn how to deploy a Cosmos DB and manage it using Visual Studio.</p>

<h2>Prerequisites</h2>
<p>To perform this demo, you must need a valid Azure Subscription and some knowledge on Azure Cosmos DB and Visual Studio.</p>

<h2>Steps:</h2>
<p>1. Login to your Microsoft Azure portal, click on Create new resource and select Azure CosmosDB from Databases category to create a CosmosDB Account and give the necessary details as follows.</p>

ID - a unique name
<p> API - Azure Table </p>
<p> Subscription - Select your subscription </p>
<p> Resource Group - Create a new resource group </p>
<p> Location - Any DC location of your choice </p>


<img src="https://codesizzlergit.blob.core.windows.net/az203-3-6/1.jpg"/>
<p>2. Once the deployment is succeeded, open the resource and click on Quick start/Connection String and note the Connection String key for a later purpose.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-3-6/2.jpg"/>
<img src="https://codesizzlergit.blob.core.windows.net/az203-3-6/3.jpg"/>
<p>3. Create a new C# Console Application within Visual Studio and name it as CosmosDBDemo.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-3-6/4.jpg"/>
<p>4. Once the project is created, install two NuGet Packages named WindowsAzure.Storage and WindowsAzure.ConfigurationManager to your solution. You can do this by selecting Tools > NuGet Package Manager > Manage NuGet Packages for Solution. In the Browse tab search for WindowsAzure.Storage and WindowsAzure.ConfigurationManager to get the packages complete the installation by reviewing the changes and accepting the license term for both.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-3-6/5.jpg"/>
<img src="https://codesizzlergit.blob.core.windows.net/az203-3-6/6.jpg"/>
<p>5. Now we have to add the Connection String to the storage account. For that open the App.config file and add following code snippet within the configuration. Replace the [Connection string] with the connection string value you copied in Step 2.</p>
    <p><appSettings></appSettings></p>
        <p><add  key="StorageConnection"  value="[Connection  String]"  /></p>
    <p></appSettings></p>
    
<img src="https://codesizzlergit.blob.core.windows.net/az203-3-6/7.jpg"/>
<p>6. Now go to the Program.cs Page and add the following code to the Main method. This code will create a connection with the storage account and create a table named customers in CosmosDB.(Copy the script from here - http://bit.ly/CosmosDB1)</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-3-6/8.jpg"/>
<p>7. Click on Start to run the program and you will see a console window waiting for an input as we given Console.Readkey() at the end of the code.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-3-6/9.jpg"/>
<p>8. Go back to your CosmosDB account and you can see our newly created table listed under tables section.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-3-6/10.jpg"/>
<img src="https://codesizzlergit.blob.core.windows.net/az203-3-6/11.jpg"/>
<p>9. Open your project in Visual Studio and create a new class named Customers inside a newly created folder called Entities.<p/>
    <p>Right-click your project in solution explorer  Add  New Folder</p>
    <p>Right Click on newly created folder  Add  New Item  Select class  Name the class as Customers.cs  Click on Add</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-3-6/12.jpg"/>
<p>10. In the newly created class Customers.cs replace the existing code with the following code.(Copy the script here - http://bit.ly/CosmosDB2) </p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-3-6/13.jpg"/>
<p>11. Back in the Program.cs, Add the following code to your Main method after the code for getting table reference.(Copy the script here - http://bit.ly/CosmosDB3)</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-3-6/14.jpg"/>
<p>12. Click on start to run the program and we can assume that the record inserted successfully as there was no error we got the message specified in the same block of code.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-3-6/15.jpg"/>
<img src="https://codesizzlergit.blob.core.windows.net/az203-3-6/16.jpg"/>
