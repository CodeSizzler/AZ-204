<h1>Create a Virtual machine using Azure Portal </h1>

<h2>Use Case</h2>
<p>In this walkthrough task we will create a virtual machine in Azure via the Azure Portal, configure it as a web server and connect to the web server over the internet.</p>

<h2>Prerequisites</h2>
<p>You need an Azure subscription to perform these steps. If you don't have one you can create one by following the steps outlined on the Create your Azure free account today webpage.</p>

<h2>Steps:</h2>
<p>1. Sign in to the Azure portal at https://portal.azure.com. </p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-001/1.png"/>
<p>2. Choose Create a resource in the upper left-hand corner of the Azure portal. In the search box above the list of Azure Marketplace resources, search for and select Windows Server 2016 Datacenter, then choose Create. </p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-001/2.png"/>
<p>3. In the Basics tab, under Project details, make sure the correct subscription is selected and then choose to create new resource group. Type Codesizzler-01 for the name.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-001/3.png"/>
<p>4. Under Instance details, type CloudVM for the Virtual machine name and choose East US for your Location. Leave the other defaults.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-001/4.png"/>
<p>5. Under the Administrator account section, provide a username, such as demouser and a password. The password must be at least 12 characters long and meet the defined complexity requirements.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-001/5.png"/>
<p>6. Under Inbound port rules, choose Allow selected ports and then select RDP (3389) and HTTP (80) from the drop-down. These are to allow us to connect to the virtual machine using RDP over port 3389 and then to see a web page display over HTTP on port 80.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-001/6.png"/>
<p>7. Leave the remaining defaults and then select the Review + create button at the bottom of the page.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-001/7.png"/>
<p>8. Once Validation is passed click the Create button. It can take approx three to five minutes to deploy the virtual machine. </p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-001/8.png"/>
<p>9. Once the virtual machine is created, go to the resource group you placed the virtual machine in, and open up the virtual machine, then click the Connect button on the virtual machine properties page.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-001/9.png"/>
<p>10. In the Connect to virtual machine page, keep the default options to connect by DNS name over port 3389 and click Download RDP File. </p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-001/10.png"/>
<p>11. Open the downloaded RDP file and click Connect when prompted.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-001/11.png"/>
<p>12. In the Windows Security window, select more choices and then Use a different account. Type the username as localhost\username, (you could also type demouser enter password you created for the virtual machine, and then click OK.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-001/12.png"/>
<p>13. You may receive a certificate warning during the sign-in process. Click Yes or to create the connection and connect to your deployed VM. You should connect successfully.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-001/13.png"/>
 <p>Congratulations! You have deployed and connected to a Windows Server virtual machine in Azure.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-001/14.png"/>
<p>14. Open up a PowerShell command prompt on the virtual machine, by clicking the Start button, typing PowerShell right clicking Windows PowerShell in the menu and selecting Run as administrator.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-001/15.png"/>
<p>15. Install the Web-Server feature in the virtual machine by running the following command in the PowerShell command prompt: PowerShell.</p>
 <p>Install-WindowsFeature -name Web-Server -IncludeManagementTools</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-001/16.png"/>
<img src="https://codesizzlergit.blob.core.windows.net/az203-001/16.1.png"/>
<p>16. When completed you should see a prompt stating Success with a value True, among other items in the output. You do not need to restart the virtual machine to complete the installation.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-001/17.png"/>
<p>17. Back in the portal, select the VM and in the overview pane of the VM, use the Click to copy button to the right of the IP address to copy it and paste it into a browser tab.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-001/18.png"/>
<p>18. The default IIS Web Server welcome page will open, and is available to connect to the publicly via this IP address, or via the fully qualified domain name.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-001/19.png"/>
<p>Congratulations! You have created a web server that can be connected to publicly via this IP address, or via the fully qualified domain name. If you had a web page to host you could deploy those source files to the virtual machine and host them for public access on the deployed virtual machine.</p>













