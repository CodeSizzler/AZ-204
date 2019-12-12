<h1>Monitoring Application performance with Application Insights</h1>

<h2>Introduction</h2>
<p>Application Insights is an extensible Application Performance Management (APM) service for web developers on multiple platforms. You can use it to monitor your live web applications and other services.</p>

<h2>Prerequisites</h2>
<p>To perform this demo, you must have valid Azure subscription, Azure DevOps organization, SQL Web app, Visual Studio.</p>

<h2>Demo</h2>
<p>1. Log-in to Azure DevOps portal with your account here - https://www.azuredevopslabs.com/labs/azuredevops/prereq/. Once you log-in it will allows you to create your project and select the template.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-004/Screenshot (11).png"/>
<p>2. In the select template panel select the parts unlimited template and click on create the project. Once you click on the create project icon you can able to monitor the status of your project.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-004/Screenshot (16).png"/>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-004/Screenshot (17).png"/>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-004/Screenshot (18).png"/>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-004/Screenshot (19).png"/>
<p>3. After the project gets created navigate to the created project.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-004/Screenshot (20).png"/>
<p>4. In the Azure DevOps portal navigate to the Repos panel and click on Clone.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-004/Screenshot (21).png"/>
<p>5. When it prompts select Visual Studio and clone it.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-004/Screenshot (22).png"/>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-004/Screenshot (23).png"/>
<p>6. You need to login with your Azure account with Visual Studio.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-004/Screenshot (24).png"/>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-004/Screenshot (25).png"/>
<p>7. Now you can able to find your parts unlimited template.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-004/Screenshot (26).png"/>
<p>8. Navigate to Azure portal and log-in with your Azure account. In the market place search for Web + SQL and when it prompts cerate a SQL Web app.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-004/Screenshot (27).png"/>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-004/Screenshot (28).png"/>
<p>9. Configure the SQL Web app as shown in the below pictures.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-004/Screenshot (29).png"/>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-004/Screenshot (31).png"/>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-004/Screenshot (33).png"/>
<p>10. Don’t wait for the deployment to gets complete, navigate to Azure DevOps portal and click on release pipeline. In the release pipeline panel click on edit option to manage your release.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-004/Screenshot (35).png"/>
<p>11. When it prompts delete the stage Dev and QA.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-004/Screenshot (37).png"/>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-004/Screenshot (38).png"/>
<p>12. After deleting click on the production stage and authorize with your Azure account to access your subscription.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-004/Screenshot (39).png"/>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-004/Screenshot (40).png"/>
<p>13. After authorizing navigate back to pipeline panel and click on the Pre-deployment Condition. In the pre-deployment condition panel set the trigger to After Release.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-004/Screenshot (41).png"/>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-004/Screenshot (42).png"/>
<p>14. After setting the trigger navigate to variables blade and replace the default values with your values, then click on save.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-004/Screenshot (43).png"/>
<p>15. Navigate back to repos blade and in the search bar search for PartsUnlimited-aspnet45/src/PartsUnlimitedWebsite/Web.config file.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-004/Screenshot (44).png"/>
<p>16. Navigate back to Azure portal and open your Web App. From the overview panel navigate to configuration blade. In that copy the values of default connection string and Application Insight Instrumentation key, you need that for further steps.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-004/Screenshot (45).png"/>
<p>17. After taking note on the values, get back to Azure DevOps portal. Now the file which you have searched for will get opened. In that file replace the values which you have copied with the respective one. After replacing the values click on commit. It will start your release.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-004/Screenshot (46).png"/>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-004/Screenshot (49).png"/>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-004/Screenshot (50).png"/>
<p>18. Don’t wait for the release navigate back to Azure portal and click on the edit icon of your Application Insight Instrumentation key. Then add a new application settings and name it as Keys:ApplicationInsights:InstrumentationKey. For value paste the Instrumentation key.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-004/Screenshot (51).png"/>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-004/Screenshot (53).png"/>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-004/Screenshot (54).png"/>
<p>19. Then open the default connection string and rename it as DefaultConnectionString. After changing the values save the changes.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-004/Screenshot (55).png"/>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-004/Screenshot (56).png"/>
<p>20. Now get back to the Azure DevOps portal. Check that your release has completed successfully.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-004/Screenshot (57).png"/>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-004/Screenshot (58).png"/>
<p>20. Again, get back to Azure portal and open your Web App. You can find the URL of your Web App in the over view panel. Copy that and browse for it. Note that you can able to see the parts unlimited page.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-004/Screenshot (59).png"/>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-004/Screenshot (60).png"/>
<p>21. Make some traffic to the website and click on breaks. In the URL manually add 1 and search. You can see the server error.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-004/Screenshot (61).png"/>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-004/Screenshot (62).png"/>
<p>22. Now navigate back to Azure portal, in your App Service page click on Application Insight. When it prompts click View Application Insight data option. It allows you to monitor the performance.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-004/Screenshot (63).png"/>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-004/Screenshot (65).png"/>
<p>23. Then click on application map. It allows you to spot performance bottlenecks or failure hotspots across all components of your distributed application.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-004/Screenshot (66).png"/>
<p>24. Then click on smart detection. This automatically warns you of potential performance problems in your web application.</p>
<p>25. Then navigate to live metrices. This enables you to probe the beating heart of your live, in-production web application.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-004/Screenshot (67).png"/>
<p>26. Then navigate to availability panel. In that panel click on add test icon and add a test. Give a valid name to your test and for URL give your Web App URL. So that it can ping your website.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-004/Screenshot (77).png"/>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-004/Screenshot (78).png"/>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-004/Screenshot (79).png"/>
<p>27. The result will not be reflected immediately. Refresh the portal, so that you can able to see the test result.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-004/Screenshot (80).png"/>
<p>28. Then navigate to failure panel. Here you can able to see the failures happened in your website.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-004/Screenshot (81).png"/>
<p>29. Navigate to performance panel. Here you can able to see your website performance.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-004/Screenshot (82).png"/>
<p>30. Now navigate to the Alert panel. In the alert panel click on add alert.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-004/Screenshot (84).png"/>
<p>41. When it prompts click on add condition and search for Failed Requests, then select it. When it prompts change the threshold value to 1 and accept the other default values, then click on done.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-004/Screenshot (85).png"/>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-004/Screenshot (86).png"/>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-004/Screenshot (87).png"/>
<p>42. After adding the condition click on create action group and add a new action group.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-004/Screenshot (88).png"/>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-004/Screenshot (89).png"/>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-004/Screenshot (90).png"/>
<p>43. After adding the action group, click on select action group and select the one which you have created in the previous step.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-004/Screenshot (91).png"/>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-004/Screenshot (92).png"/>
<p>44. Finally give a valid name to your alert rule and note that now the create option is enabled. Click on create.</p>
<img src="https://codesizzlergit.blob.core.windows.net/az203-5-004/Screenshot (93).png"/>

<h2>Summary</h2>
<p>Once the rule has been created, return to the web site browser tab and invoke some errors using the method from earlier. Around five minutes later, you should receive an email indicating that your alert was triggered.</p>
