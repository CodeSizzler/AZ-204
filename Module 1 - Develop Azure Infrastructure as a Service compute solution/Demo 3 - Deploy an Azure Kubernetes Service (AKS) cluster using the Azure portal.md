<h1>Deploy an Azure Kubernetes Service (AKS) cluster using the Azure portal</h1>

<h2>Introduction</h2>
<p>In this article you will understand how to create an Azure Kubernets Service (AKS) using the Azure Portal. Azure Kubernetes Service (AKS) is a managed Kubernetes service that lets you quickly deploy and manage clusters. In this you will deploy an AKS cluster using the Azure portal. A multi-container application that includes a web front end and a Redis instance is run in the cluster. You then see how to monitor the health of the cluster and pods that run your application.</p>

<h2>Prerequisites</h2>
<p>To perform this demo, you must need a valid Azure Subscription and some knowledge in Azure Kubernets Service and PowerShell.</p>

<h2>Steps:</h2>
<p>1. Log-in to Azure portal with your account using www.portal.azure.com. In the Azure portal click on Create a Resource and then select the Kubernets Service in the Containers category.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-004/1.png"/>
<p>2. When it prompts create a Kubernets Cluster with the following configurations as shown in the below picture and click on Review+Create.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-004/2.png"/>
<p>3. When your deployment is complete select the Go to Resource in the notification that will promote you the Kubernets Cluster page you have created and have a look at it.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-004/3.png"/>
<img src="https://codesizzlergit.blob.core.windows.net/az203-004/4.png"/>
<p>4. To connect the cluster you have to open the PowerShell by clicking this >_ icon on the top of the Azure Portal. Where you will use the kubectl a Kubernets command-line client which is pre-installed in the PowerShell.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-004/5.png"/>
<p>5. To configure kubectl which connects the Kubernets Cluster you will be using az aks get-credentials command. This command downloads credentials and configures the Kubernetes CLI to use them. Use the following command:</p>
<p>az aks get-credentials --resource-group codesizzler_rg --name DemoAKScluster</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-004/6.png"/>
<p>6. To verify the connection to your cluster, use the kubectl get command to return a list of the cluster nodes. Once you use the code you will receive an output showing the single node created in the previous step. Make sure that the status of the node is ready. Use the following command:</p>
<p>kubectl get nodes</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-004/7.png"/>
<p>7. Now you have run the cluster by kubernets manifest. A Kubernetes manifest file defines a desired state for the cluster, such as what container images to run. A manifest is used to create all objects needed to run the Azure Vote application. This manifest includes two Kubernetes deployments - one for the sample Azure Vote Python applications, and the other for a Redis instance. Two Kubernetes Services are also created - an internal service for the Redis instance, and an external service to access the Azure Vote application from the internet. Now in the PowerShell you have to create a file named azure-vote.yaml using nano or vi. And copy the following YAML definition:</p>
<p>Copy pate the script from here - http://bit.ly/AKSscript</p>
<p>The created file using nano will be shown like the following image. </p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-004/8.png"/>
<p>8. Once the file is created now you have to deploy the application using kubectl apply command and you have to specify the YAML manifest name like the following command:</p>
<p>kubectl apply -f azure-vote.yaml</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-004/9.png"/>
<p>9. Now you have to test the application by using kubectl get service command with the --watch argument. Once you deploy this command you will get an output with the External ip address. Sample command: kubectl get service azure-vote-front –watch</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-004/10.png"/>
<p>10. Use the External ip address to test the cluster by opening in the browser you will see the following page as a result:</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-004/11.png"/>
<p>11. You can also monitor the health and logs of the cluster. When you created the cluster, Azure monitors for containers was enabled. This monitoring features will provide health metric for both AKS cluster and pods running on the cluster. To see the usage go back to the Resource group select the DemoAKScluster and do the following steps:</p>
    <p>Select insights in the Monitoring section.</p>
    <p>Select the +Add filters icon</p>
    <p>Select the Namespace as properties and choose <All but kube-system></p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-004/12.png"/>
<p>Now select the Containers section to see the azure-vote-back and azure-vote-front containers are displayed.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-004/13.png"/>
<p>Now select the Logs in the Monitoring section to view the logs of azure-vote-front and this logs includes the stdout and stderr streams from the container.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-004/14.png"/>
<p>Once you are done with Kubernets service delete the Resource group in the Azure portal.</p>
