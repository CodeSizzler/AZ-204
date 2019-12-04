<h1>Creating manually triggered web-job in Azure portal</h1>
<h2>Introduction</h2>
<p>In this article you will learn how to create Manually Triggered Webjob in the Azure portal. WebJobs is a feature of Azure App Service that enables you to run a program or script in the same context as a web app, API app, or mobile app. There is no additional cost to use WebJobs.</p>

<h2>Prerequisites</h2>
<p>To perform this demo, you must need a valid Azure Subscription and some knowledge on Azure App service, Web App and Webjobs.</p>

<h2>Steps:</h2>
<p>1. Log-in to Azure portal with your account using www.portal.azure.com. Select Create a Resource in the Azure portal.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-2-001/1.png"/>
<p>2. Now search Web App in the search bar and create the web App with the following configuration as shown in the below image and then select create.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-2-001/2.png"/>
<img src="https://codesizzlergit.blob.core.windows.net/az203-2-001/3.png"/>
<img src="https://codesizzlergit.blob.core.windows.net/az203-2-001/4.png"/>
<p>3. Once your deployment is complete click Go to Resource, now navigate to Webjobs in the Settings section.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-2-001/5.png"/>
<p>4. Now create a Webjob in the Web App by clicking +ADD icon and create with the following configuration as shown in the below image.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-2-001/6.png"/>
<img src="https://codesizzlergit.blob.core.windows.net/az203-2-001/7.png"/>
<p>5. Once your webjob is added successfully, select refresh to view the created webjob.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-2-001/8.png"/>
<p>6. Select the webjob and then select Run to start your deployment.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-2-001/9.png"/>
<img src="https://codesizzlergit.blob.core.windows.net/az203-2-001/10.png"/>
<img src="https://codesizzlergit.blob.core.windows.net/az203-2-001/11.png"/>
<p>7. Once you Run the webjob, the status of the webjob will be in ready condition.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-2-001/12.png"/>
<p>8. If you have uploaded a template or parameter file, once you run the webjob your deployment will be started.</p>



