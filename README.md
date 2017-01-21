# Azure Application Insights
Azure Application Insights is a service that can help your team gain insights into the usage, reliability and performance of your live Node.js Express applications.

[Learn about Azure Application Insights](https://azure.microsoft.com/en-us/services/application-insights/ "Documentation")

The Application Insights extension for Visual Studio Code brings information from your production services right into your code editor to help you find and fix issues faster.

## Features
### Request data in CodeLens
Three request metrics are available in CodeLens in Visual Studio Code. Each shows data from the last 24 hours as measured by the Application Insights resource you set up with Visual Studio Code:
* **Total Requests** - Number of requests made to this route
* **Failed Request** - Number of failed requests to this route
* **Average Response Times** - Average response time for requests made to this route.

![Example of request CodeLens functionality](https://aidevtools.blob.core.windows.net/vscode-assets/codelens.gif)

### Easy Onboarding
Enable Application Insights telemetry collection in your Express app with a simple command in Visual Studio Code. 

![Example of onboarding](https://aidevtools.blob.core.windows.net/vscode-assets/onboarding.gif)

## Getting started with Express and Application Insights
### Create an Express app
Get started by installing the Express generator, creating a new app, and opening it in Visual Studio Code:
```
$ npm install express-generator -g
$ express mywebapp
$ cd mywebbapp && npm install
$ code .
```
[Learn about using the Express generator.](http://expressjs.com/en/starter/generator.html)

### Onboard with Application Insights
Run the 'Add to Project' command to register your app with Application Insights. 

`Ctrl/Command + Shift + P ->  "Application Insights: Add to Project"`

This command guides you through creating (or selecting) an Azure resource for your telemetry. It also adds the required packages/code to start collecting telemetry data and showing it in CodeLens. Run your app or deploy it to start seeing telemetry in Visual Studio Code and the Azure Portal.

Application Insights resources are free for the first gigabyte of data per month. See [Application Insights Pricing](https://go.microsoft.com/fwlink/?linkid=833169) for more details.

![Example of onboarding](https://aidevtools.blob.core.windows.net/vscode-assets/onboarding.gif)

### See CodeLens on request definitions
![Example of request CodeLens functionality](https://aidevtools.blob.core.windows.net/vscode-assets/codelens.gif)

Click on the CodeLens indicator to see more details.

## See CodeLens data from a different Application Insights Resource
If you want CodeLens to show data from a different resource than the one you onboarded from, then run the 'Choose CodeLens resource' command. This is a common scenario when you have different resources for your development and production environment.

`Ctrl/Command + Shift + P ->  "Application Insights: Choose CodeLens resource"`


![How to select a resource](https://aidevtools.blob.core.windows.net/vscode-assets/selectresource.gif)

## Release Notes
### Version 0.3.1
- Switched to using esprima-fb in order to support es7 syntax.
- Telemetry improvements.

### Version 0.3.0
- Added commnad to open azure portal.
- Informational prompt to add Application Insights to a new project.

### Version 0.2.0
- Application Insights onboarding for Node.js Express apps.
- Disable telemetry auto-collection.
- Update third party notices file.
- Add functionality to opt out of usage telemetry reporting.

### Version 0.1.1
- Bug fix to enable usage telemetry.

### Version 0.1.0
- Support CodeLens with request statistics for Node.js Express applications.

## Feedback
- In order to report bugs or provide general feedback please visit our repository's [Issues](https://github.com/Microsoft/applicationinsights-vscode/issues) page.

## Privacy Statement
The [Microsoft Online Services Privacy Statement](https://go.microsoft.com/fwlink/?LinkId=512156) describes the privacy statement of this software.

If you don’t wish to send usage data to Microsoft, add the environment variable AITOOLSVSCODE_DISABLETELEMETRY.

## License
The extension is made available under the [Microsoft Software License Terms](https://github.com/Microsoft/applicationinsights-vscode/blob/master/LICENSE). Please see the [third-party notices](https://github.com/Microsoft/applicationinsights-vscode/blob/master/ThirdPartyNotices.txt) file for additional copyright notices and license terms applicable to portions of the software.
