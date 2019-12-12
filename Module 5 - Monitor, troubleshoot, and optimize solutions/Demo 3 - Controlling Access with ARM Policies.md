<h1> ControllingAccesswithARMPolicies </h1>

<h2> Lab Overview </h2>
<p> In this lab, you will deploy an Azure Resource Manager Policy that restricts access to a resource provider and apply it to a new custom resource group.</p>
<h2>Prerequisites</h2>
<p>You need an Azure subscription to perform these steps. If you don't have one you can create one by following the steps outlined on the Create your Azure free account today webpage.</p>

<h2>Demo</h2>
<p>1. Launch the PowerShell Integrated System Environment (ISE) by typing in PowerShell_ISE in the Windows run prompt.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-003/01.PNG"/>
<p>2. In the PowerShell ISE Console Pane run the Login-AzureRmAccount cmdlet by typing the cmdlet nameinandpressing Enter. This cmdletwill launch a dialog that will allow you to login with your Azure subscription credentials. The session is valid for 12 hours as long as you do not close and re-open the PowerShellISE. </p>
	<p>Login-AzureRmAccount</p>
<p>3. Enter the credentials for your Azure subscription when prompted.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-003/02.PNG"/>
<p>4. Inthe PowerShell ISEConsole Pane runthe following commandtolist the subscriptions that are attached to your account.</p>
	<p>Get-AzureRMSubscription</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-003/03.PNG"/>

<img src="https://codesizzlergit.blob.core.windows.net/az203-5-003/04.PNG"/>
<p>5. In the PowerShell ISE Console Pane run the following command to Select the subscription that will be used for the reminder of the course. Replace [subscription id] leaving the quotes.</p>
	<p>Select-AzureRmSubscription -SubscriptionId</p>
	<p>"[subscription id]"</p>
<p>6. OpenFileExplorerandnavigatetoC:\OpsgilityTraining.Right-clickthe ServiceCatalogPolicy.json file and select Open with and then choose Notepad.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-003/05.PNG"/>
<p>7. Create a new resource group by running the following command and pressing Enter. Replace the value of the Location parameter with the location nearest to you.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-003/06.PNG"/>
<p>8. Create a new policy definition using the ServiceCatalogPolicy.json file by executing the following PowerShell command.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-003/07.PNG"/>
<p>9. Create a $ResourceGroup variable and a $Policy variable by executing the following PowerShell commands.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-003/08.PNG"/>
<p>10. Now wewillassignthe newly createdpolicyto ourresource group by executing the following PowerShell command.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-003/09.PNG"/>
<p>11. In the Azure portal, click New, Databases, SQL Database.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-003/10.PNG"/>
<p>12. On the SQL Database blade, specify the settings below and click Server, to Create a new server. Click Select on the New server blade and Create on the SQL Database blade.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-003/11.PNG"/>
<p>13. In the Azure portal you will get anerroralert. Click on the alerttodrill into the details of the alert.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-003/12.PNG"/>
<p>14. On the Microsoft.SQL.NewDatabase blade you will see the status is Failed. Scroll to the Operation details at the bottom of the summary output. Notice that the status is Forbidden. Click on this entry to view the details of the operation.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-003/13.PNG"/>
<p>15. In the Operation details blade, review the Status Message. Note the underlying reason for the failure is RequestDisallowedByPolicy. The status message also has an explanation of the error and contains the policy identifier.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-003/14.PNG"/>
 
