<h1>Build an ASP.NET app in Azure with SQL Database</h1>

<h2>Introduction</h2>
<p>In this you will learn how to deploy a data-driven ASP.NET app in App Service and connect it to Azure SQL Database. Azure App Service provides a highly scalable, self-patching web hosting service. As a result you will have an ASP.NET app running in Azure and connected to SQL Database.</p>

<h2>Prerequisites</h2>
<p>To perform this demo, you must need a valid Azure Subscription and some knowledge in Azure SQL Database, Visual Studio and ASP.NET.</p>

<h2>Steps:</h2>
<p>1. Open the sample data in the visual studio, if you don’t have a sample data download it from the below link https://github.com/Azure-Samples/dotnet-sqldb-tutorial/archive/master.zip. Once you open the data, right click the DotNetappSqlDb in the Solution Explorer and then select Publish.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-3-004/1.png"/>
<p>2. Now create a new App service with the following configuration as shown in the below picture.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-3-004/2.png"/>
<img src="https://codesizzlergit.blob.core.windows.net/az203-3-004/3.png"/>
<p>3. Now create a SQL Database and SQL server with the following configuration as shown in the below picture.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-3-004/4.png"/>
<img src="https://codesizzlergit.blob.core.windows.net/az203-3-004/5.png"/>
<img src="https://codesizzlergit.blob.core.windows.net/az203-3-004/6.png"/>
<p>4. Once you created the SQL database and Hosting plan you will see the following image as a result. Now select create to complete the App Service.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-3-004/7.png"/>
<p>5. Once the app service is created, now copy the URL and open it in the browser, you will see the following image as a result.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-3-004/8.png"/>
<img src="https://codesizzlergit.blob.core.windows.net/az203-3-004/9.png"/>
<p>6. Now Access the SQL Database locally, From the View menu, select SQL Server Object Explorer. Select the SQL Database that you created earlier. The connection you created earlier is automatically filled at the bottom. Type the database administrator password you created earlier and click Connect.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-3-004/10.png"/>
<img src="https://codesizzlergit.blob.core.windows.net/az203-3-004/10.1.png"/>
<p>7. Expand your connection > Databases > <your database> > Tables. Right-click on the Todoes table and select View Data.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-3-004/11.png"/>
<img src="https://codesizzlergit.blob.core.windows.net/az203-3-004/12.png"/>
<p>8. Now you use Code First Migrations in Entity Framework to make a change to your database schema and publish it to Azure. Now open the Package Manager Console from NuGet Package Manager in the Tools Section.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-3-004/13.png"/>
<p>9. To enable code first migration run the following Razor code in the package manager console.</p>
    <p>Enable-Migrations</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-3-004/14.png"/>
<p>10. Once you enabled the migration, now add the migration using the following command.</p>
    <p>Add-Migration AddProperty</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-3-004/15.png"/>
<p>11. Now update the local database using the following command.</p>
    <p>Update-Database</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-3-004/16.png"/>
<p>12. Now make some changes in your code to use the Done property. In this demo you're only going to change the Index and Create views to see the property in action. Open Controllers\TodosController.cs.</p>
<p>13. Find the Create() method on line 52 and add Done to the list of properties in the Bind attribute. When you're done, your Create() method signature looks like the following code:</p>
    <p>public ActionResult Create([Bind(Include = "Description,CreatedDate,Done")] Todo todo)</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-3-004/17.png"/>
<p>14. Now open Views\Todos\Create.cshtml.In the Razor code, you should see a <div class="form-group"> element that uses model.Description, and then another <div class="form-group"> element that uses model.CreatedDate. Following these two elements, add another <div class="form-group"> element that uses model.Done using the following command.</p>
<p>    <div class="form-group"></div></p>
<p>    @Html.LabelFor(model => model.Done, htmlAttributes: new { @class = "control-label col-md-2" })</p>
<p>    <div class="col-md-10"></div></p>
<p>        <div class="checkbox"></div></p>
<p>            @Html.EditorFor(model => model.Done)</p>
<p>            @Html.ValidationMessageFor(model => model.Done, "", new { @class = "text-danger" })</p>
<p>        </div></p>
<p>    </div></p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-3-004/18.png"/>
<p>15. Open Views\Todos\Index.cshtml.Search for the empty <th></th> element. Just above this element, add the following Razor code.</p>
<p><th></p>
<p>    @Html.DisplayNameFor(model => model.Done)</p>
<p></th></p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-3-004/19.png"/>
<p>16. Find the <td> element that contains the Html.ActionLink() helper methods. Above this <td>, add another <td> element with the following Razor code.</p>
<p><td></p>
<p>    @Html.DisplayFor(modelItem => item.Done)</p>
<p></td></p>    
<img src="https://codesizzlergit.blob.core.windows.net/az203-3-004/20.png"/>
<p>17. Type Ctrl+F5 to run the app. You can now add a to-do item and check Done.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-3-004/21.png"/>
<p>18. Now you can stream tracing messages directly from your Azure app to Visual Studio. From the View menu, select Server Explorer. You can configure logging for your Azure app in Server Explorer. Expand the myResourceGroup resource group, you created when you first created the Azure app. Right-click your Azure app and select View Streaming Logs.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-3-004/22.png"/>
<img src="https://codesizzlergit.blob.core.windows.net/az203-3-004/22.1.png"/>
<p>19. The logs are now streamed into the Output window.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-3-004/23.png"/>
<p>20. However, you don't see any of the trace messages yet. That's because when you first select View Streaming Logs, your Azure app sets the trace level. To stop the log-streaming service, click the Stop monitoring button in the Output window.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-3-004/24.png"/>
<p>21. Now go to the Azure portal to manage the web app. Search for and select App Services. Select the name of your Azure app.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-3-004/25.png"/>
<img src="https://codesizzlergit.blob.core.windows.net/az203-3-004/25.1.png"/>
<img src="https://codesizzlergit.blob.core.windows.net/az203-3-004/25.2.png"/>
