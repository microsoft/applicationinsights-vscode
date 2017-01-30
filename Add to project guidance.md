# Application Insights Add To Project Command Guidance

Azure Application Insights extension for Visual Studio Code provides effortless ways to onboard your Nodejs apps to Application Insights.

Gowing through the complete flow, you can easily create a new Application Insights resource, add telemetry initialization code to your project and gain insights about your app in production.

1. Invoke the Application Insights: Add To Project command from the command palette.
![Open Add To Project command](https://aidevtools.blob.core.windows.net/vscode-assets/AddToProjectCommand.PNG)

2. Select the Azure account you want to use.
![Select account](https://aidevtools.blob.core.windows.net/vscode-assets/SelectAccount.PNG)

3. Select your subscription.
![Select subscription](https://aidevtools.blob.core.windows.net/vscode-assets/SelectSub.PNG)

4. Select or create new Application Insights resource
![Select resoruce](https://aidevtools.blob.core.windows.net/vscode-assets/SelectResource.PNG)

Once you go through this flow we will install the npm install [appplicationinsights package](https://www.npmjs.com/package/applicationinsights) and inject the following code in your project's main file:

```
// Enable telemetry collection with Application Insights
var ai = require('applicationinsights');
ai.setup(process.env.APPLICATIONINSIGHTSKEY || 'XXXXXXXXXXXXXXXXXXXXXX').start();
```
where XXXXXXXXXXXXXXXXXXXXXX is the instrumentation key of the resource you selected (or created) in step 4.

NOTE: In order to inject code to your project's main file, we look at package.json's main argument. If it is not defined, we look for common main file names in the workspace's root directory. Finally, if we fail to find a main file, you would need to add the code shown above into your project. You can find the instrumentation key for your resource using [instructions described on this page](https://docs.microsoft.com/en-us/azure/application-insights/app-insights-create-new-resource).