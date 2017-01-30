# Application Insights Add SDK Only Guidance

If you choose the Add SDK only flow in the Add To Project command you have the option of linking your app's telemetry data to Application Insights resource later.

![Add SDK Only](https://aidevtools.blob.core.windows.net/vscode-assets/AddSDKOnly.PNG)

Once you go through this flow we will install the npm install [appplicationinsights package](https://www.npmjs.com/package/applicationinsights) and inject the following code in your project's main file:

```
// Add your instrumentation key or use the APPLICATIONINSIGHTSKEY environment variable on your production machine to start collecting data.
var ai = require('applicationinsights');
ai.setup(process.env.APPLICATIONINSIGHTSKEY || 'your_instrumentation_key').start();
```

You can then [create an Application Insights resource](https://docs.microsoft.com/en-us/azure/application-insights/app-insights-create-new-resource) and add the instrumentation key here.

You can also simply set APPLICATIONINSIGHTSKEY environment variable to your Application Insights reource's instrumentation key and all data will be auto collected to that resource.

NOTE: In order to inject code to your project's main file, we look at package.json's main argument. If it is not defined, we look for common main file names in the workspace's root directory. Finally, if we fail to find a main file, you would need to add the code shown above into your project.