<h1>Create a Blank API in Azure</h1>

<h2>Introduction</h2>
<p>API Management (APIM) is a way to create consistent and modern API gateways for existing back-end services. API Management helps organizations publish APIs to external, partner, and internal developers to unlock the potential of their data and services. In this article learn how to use the Azure portal to add an API manually to the API Management (APIM) Service. </p>

<h2>Prerequisites</h2>
<p>To perform this demo, you must need a valid Azure Subscription and some knowledge on Azure API Management Service. </p>

<h2>Steps:</h2>
<p>1. Log-in to Azure portal with your account using www.portal.azure.com. Select the left menu in the portal and then select All Service. Select API Management Service and click on Add icon to create an API management service with following configurations. </p>
  
  <p>Name: Give a valid name.</p> 
  <p>Subscription: Select a valid subscription.</p>
  <p>Resource Group: Select a valid Resource Group.</p> 
  <p>Location: Select a valid location.</p>
  <p>Organization Name: Give a valid name.</p>
  <p>Administration email id: Give a valid email id.</p>
  <p>Pricing tier: Select a valid pricing tier.</p>
  
<img src="https://codesizzlergit.blob.core.windows.net/az203-2-004/1.png"/>
<img src="https://codesizzlergit.blob.core.windows.net/az203-2-004/2.png"/>

<p>2. Once your deployment is complete select Go to resource, now select APIs in the API management section and then click on Blank API. </p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-2-004/3.png"/>
<p>3. Now create a blank api with the following configuration and then select Create.</p>
  Display Name: Blank API. 

  <p>Name: blank-api.<p/>
  <p>Web service URL: http://httpbin.org.<p/>
  <p>API URL suffix: hbin.<p/>
  
<img src="https://codesizzlergit.blob.core.windows.net/az203-2-004/4.png"/>
<p>4. Once you have created the blank API, now add a "/get" operation in order to map it to the back end "http://httpbin.org/get" operation. Add an operation with the following configurations and then select SAVE.</p>
  
  <p>Select the API you created in the previous step.<p/>
  <p>Click + Add Operation.<p/>
  <p>In the URL, select GET and enter "/get" in the resource.<p/>
  <p>Enter "FetchData" for Display name.<p/>

<img src="https://codesizzlergit.blob.core.windows.net/az203-2-004/5.png"/>
<img src="https://codesizzlergit.blob.core.windows.net/az203-2-004/6.png"/>

<p>5. Now test the operation in the Azure portal. Alternatively, you can test it in the Developer portal. Select the Test tab and then select FetchData, now Press Send to test the API. </p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-2-004/7.png"/>
<img src="https://codesizzlergit.blob.core.windows.net/az203-2-004/8.png"/>
<p>6. Once you click send the "http://httpbin.org/get" operation generates appears. Now add a parameterized operation in the API and test the API. Add the parameterized operation with the following configuration.<p/>

  <p>Select the API you created in the previous step.<p/>
  <p>Click + Add Operation.<p/>
  <p>In the URL, select GET and enter "/status/{code}" in the resource. Optionally, you can provide some information associated with this parameter. For example, enter "Number" for TYPE, "200" (default) for VALUES.<p/>
  <p>Enter "GetStatus" for Display name.<p/>

<img src="https://codesizzlergit.blob.core.windows.net/az203-2-004/9.png"/>
<img src="https://codesizzlergit.blob.core.windows.net/az203-2-004/10.png"/>

<p>7. Once you add the operation, now test the operation in the Azure portal. Alternatively, you can test it in the Developer portal. Select the Test tab and then select GetStatus. Press Send.<p/>
<img src="https://codesizzlergit.blob.core.windows.net/az203-2-004/11.png"/>
<img src="https://codesizzlergit.blob.core.windows.net/az203-2-004/12.png"/>
