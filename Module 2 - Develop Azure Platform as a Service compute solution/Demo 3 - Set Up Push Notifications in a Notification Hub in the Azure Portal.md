<h1>Set Up Push Notifications in a Notification Hub in the Azure Portal</h1>
<h2>Introduction</h2>
<p>In this article you will understand how to set up a push notification in a notification hub in the Azure portal. You’ll use the platform notification system (PNS) settings in Notification Hubs.</p>

<h2>Prerequisites</h2>
<p>To perform this demo, you must need a valid Azure Subscription and some knowledge on Azure Notification Hub, Fire Base and Baidu cloud push project.</p>

<h2>Steps:</h2>
<p>1.Log-in to Azure portal with your account using www.portal.azure.com. Select the Notification Hub that you created early.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-2-003/1.png"/>
<p>2. Once you navigate to the notification hub you can see multiple platform in the settings section. You can select the platform which you need.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-2-003/2.png"/>
<h2>Google Firebase Cloud Messaging (FCM)</h2>
<p>1. Once you select the google platform it will ask for the API key. You can get the API key from the Fire Base. Create a Fire Base for your project.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-2-003/3.png"/>
<p>2. Select the project you created in the Fire Base and then select project settings in settings icon on the top.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-2-003/4.png"/>
<p>3. This will navigate you to the project settings page from that page you can get the API key in the general category.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-2-003/5.png"/>
<p>4. Once you get the API key use that key in the Google Platform to set up the push notification and then click Save. When you complete these steps, an alert indicates that the notification hub has been successfully updated. Note that the Save button is disabled.</p>
<h2>Apple Push Notification Service (APNS)</h2>
<p>Select the Apple platform to set up push notification in the Notification Hub and do the following steps</p>
<span>&#8226;</span>For Authentication Mode, select either Certificate or Token.
<img src="https://codesizzlergit.blob.core.windows.net/az203-2-003/7.PNG"/>
<h2>Windows Push Notification Service (WNS)</h2>
<span>&#8226;</span>Select the windows (WNS) platform in the settings.
<span>&#8226;</span>Enter values for the Package SID and Security Key.
<span>&#8226;</span>Finally select the Save icon.
<img src="https://codesizzlergit.blob.core.windows.net/az203-2-003/8.png"/>
<h2>Microsoft Push Notification Service for Windows Phone (MPNS)</h2>
<span>&#8226;</span>Select the windows phone (MPNS) platform from the settings.
<span>&#8226;</span>To enable unauthenticated push notifications, select Enable unauthenticated push and then click Save icon.
<span>&#8226;</span>To enable Authenticated push notifications select the Upload Certificate icon on the tool bar and then upload the certificate and click the save icon.
<img src="https://codesizzlergit.blob.core.windows.net/az203-2-003/9.png"/>
<h2>Amazon (ADM)</h2>
<span>&#8226;</span>Select the Amazon (ADM) platform to set up the push notification.
<span>&#8226;</span>Enter the Client ID and Client Secret.
<span>&#8226;</span>Click the Save icon.
<img src="https://codesizzlergit.blob.core.windows.net/az203-2-003/10.png"/>
<h2>Baidu (Android China)</h2>
<span>&#8226;</span>Select the Baidu (Android China) platform from the settings to set up the push notification.
<span>&#8226;</span>Enter the API Key and Secret Key that you obtained from the Baidu console in the Baidu cloud push project.
<span>&#8226;</span>Finally click the Save icon.
<img src="https://codesizzlergit.blob.core.windows.net/az203-2-003/11.png"/>
