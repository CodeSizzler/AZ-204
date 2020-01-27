<h1>Run a batch job by using Azure CLI and Azure portal</h1>

<h2>Introduction</h2>
<p>Azure Batch Service is a cloud based job scheduling and compute management platform that enables running large-scale parallel and high performance computing applications efficiently in the cloud.</p>

<h2>Prerequisites</h2>
<p>To perform this demo, you must need a valid Azure Subscription and some knowledge on Azure CLI and Azure Batch.</p>

<h2>Steps:</h2>

<h2>Running Batch jobs with Azure CLI</h2>

<p>1. Open the Command prompt and run the <b>az login</b> command to login with your Azure account. It will open a browser which asks you to enter you Azure account credentials. This allows you to access your Azure account using Azure CLI.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-003/1.JPG"/>
<p>2. After loging in with your Azure account run the following command to create a new resource group.</p>
    <p><b> az group create --name myResourceGroup --location eastus2</b></p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-003/2.JPG"/>
<p>3. You can link an Azure Storage account with your Batch account. Although not required for this quickstart, the storage account is useful to deploy applications and store input and output data for most real-world workloads. Create a storage account in your resource group with the storage account create command.</p>
    <p><b> az storage account create --resource-group myResourceGroup --name mystorageaccount --location eastus2 --sku Standard_LRS</b></p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-003/3.JPG"/>
<p>4. Create a Batch account with the azure batch create command. You need an account to create compute resources (pools of compute nodes) and Batch jobs.</p>
    <p><b> az batch account create --name mybatchaccount --storage-account mystorageaccount --resource-group myResourceGroup --location eastus2</b></p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-003/4.JPG"/>
<p>5. To create and manage compute pools and jobs, you need to authenticate with Batch. Log in to the account with the batch account login command. After you log in, your batch commands use this account context.</p>
<p><b> az batch account login --name mybatchaccount --resource-group myResourceGroup --shared-key-auth </b>></p>

<h2>Create a pool of compute nodes</h2>
<p>1. Have a Batch account, create a sample pool of compute nodes using the batch pool create command. The following example creates a pool named mypool of 2 size Standard_A1_v2 nodes running Ubuntu 16.04 LTS. The suggested node size offers a good balance of performance versus cost for this example.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-003/5.JPG"/>
    <p><b> az batch pool create --id mypool --vm-size Standard_A1_v2 --target-dedicated-nodes 2 --image canonical:ubuntuserver:16.04-LTS --node-agent-sku-id "batch.node.ubuntu 16.04"</b></p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-003/6.JPG"/>
<img src="https://codesizzlergit.blob.core.windows.net/az203-003/7.JPG"/>
<p>2. Batch creates the pool immediately, but it takes a few minutes to allocate and start the compute nodes. During this time, the pool is in the resizing state. To see the status of the pool, run the batch pool show command. This command shows all the properties of the pool, and you can query for properties. The following command gets the location state of the pool.</p>
    <p><b> az batch pool show --pool-id mypool --query "allocationState"</b></p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-003/8.JPG"/>
