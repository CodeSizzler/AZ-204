<h1>Create an Azure VM using Powershell</h1>

<h2>DIY:</h2>

<p>Azure PowerShell should be used to create and manage Azure resources from the PowerShell command line or in scripts. Try to use the Azure PowerShell module to deploy a VM in Azure that runs Windows Server 2016. To examine your VM in action, you then RDP to the VM and install the IIS web server. </p> 

<h2>Solution:</h2>

<p>Connect-AzureRmAccount</p>

<p>New-AzureRmResourceGroup -Name myResourceGroup -Location EastUS</p>

<p>New-AzureRmVm -ResourceGroupName "myResourceGroup" -Name "myVM" -Location "East US" -VirtualNetworkName "myVnet" -SubnetName "mySubnet" -SecurityGroupName "myNetworkSecurityGroup" -PublicIpAddressName "myPublicIpAddress" -OpenPorts 80,3389</p>
