<h1>Deploy multi-containers to Container Instances using a YAML file</h1>

<h2>Introduction</h2>
<p>In this article you will learn how to deploy a multi container instance using YAML file. Run a simple two-container sidecar configuration by deploying a YAML file using the Azure CLI. A container group is useful when building an application sidecar for logging, monitoring, or any other configuration where a service needs a second attached process.</p>

<h2>Prerequisites</h2>
<p>To perform this demo, you must need a valid Azure Subscription and some knowledge on Azure Container Instance, Azure CLI and YAML configuration.</p>

<h2>Steps:</h2>
<p>1. Log-in to Azure portal with your account using www.portal.azure.com. Select Powershell icon in the top of the portal.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-4-001/1.png"/>
<p>2. Use the following command to open the editor, there you can add your code in YAML file.</p>
<p>code deploy-aci.yaml</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-4-001/2.png"/>
<p>Now configure the YAML by copy pasting the script from http://bit.ly/YAMLScript</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-4-001/3.png"/>
<p>Once you add the above YAML file click save button.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-4-001/4.png"/>
<p>Now use the following command to create a resource group.</p>
<p>az group create --name Codesizzler_Rg --location CentralUS</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-4-001/5.png"/>
<p>Now use the following command to create a container in Azure. Select the YAML file you added early.</p>
<p>az container create --resource-group Codesizzler_Rg --file deploy-aci.yaml</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-4-001/6.png"/>
<p>Once you have created the container, use the following command to view the output table.</p>
<p>az container show --resource-group Codesizzler_Rg --name codesizzleryamlcontainer --output table</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-4-001/7.png"/>
<p>Now use the following command to view one of the container logs</p>
<p>az container logs --resource-group Codesizzler_Rg --name codesizzleryamlcontainer --container-name aci-tutorial-app</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-4-001/8.png"/>
