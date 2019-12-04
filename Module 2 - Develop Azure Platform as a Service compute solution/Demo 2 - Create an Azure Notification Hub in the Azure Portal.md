<h1>Create an Azure Notification Hub in the Azure Portal</h1>
<h2>Introduction</h2>
<p>In this article you will understand how to create an Azure Notification Hub in Azure Portal. Azure Notification Hubs provide an easy-to-use and scaled-out push engine that allows you to send notifications to any platform (iOS, Android, Windows, Kindle, Baidu, etc.) from any backend (cloud or on-premises).</p>

<h2>Prerequisites</h2>
<p>To perform this demo, you must need a valid Azure Subscription and some knowledge on Azure Notification Hub.</p>

<h2>Steps:</h2>
<p>1. Log-in to Azure portal with your account using www.portal.azure.com. In Azure portal click on All services on the left menu and then select Notification Hubs in the Mobile section.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-2-002/1.png"/>
<p>2. When it prompts create a Notification Hub with the following configurations as shown in the below image and click on create.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-2-002/2.png"/>
<p>3. Wait until the deployment gets succeed. After the deployment gets completed navigate to the created resource.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-2-002/3.png"/>
<p>4. From the Notification Hub page select Access Policies from the list. Note that the two connection strings are available to you. You'll need them later to handle push notifications.</p>
<p>Note - Do not use the DefaultFullSharedAccessSignature policy in your application. This is meant to be used in your back end only.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-2-002/4.png"/>
<p>5. Now you will be creating a Notification Hub in an existing Namespace. For that again navigate to All Service in the left menu and then select Notification Hub Namespace in Web section.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-2-002/5.png"/>
<p>6. Once the Notification Hub Namespace page opens select your existing Namespace.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-2-002/6.png"/>
<p>7. When it promotes to the namespace page now select the add hub icon to create a new notification hub in the existing namespace. </p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-2-002/7.png"/>
<p>8. Enter the Notification Hub Name and then select OK to create a new Notification Hub.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-2-002/8.png"/>
<p>9. Once you create the Notification Hub you can see your new Notification Hub in the existing Namespace.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-2-002/9.png"/>
