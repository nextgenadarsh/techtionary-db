# Azure Workflow Technologies

- Logic Apps
- Microsoft Power Automate
- WebJobs and WebJobs SDK
- Azure Functions

## Similarities

- Input: Accepts piece of data or a file that is supplied to the workflow
- Actions: Simple operations that workflow executes and often modify data or cause another action to be performed
- Conditions
- Outputs

## Design First Technologies

- Workflows are created using UI

### Logic Apps

- Used to `automate, orchestrate, and integrate` disparate components of a distributed application
- Connector provides an interface to an external service. Over 200 connectors are included. Eg: `Twitter, Office 365 connectors`
- You can create your `own connectors` if your system exposes REST API.

### Microsoft Power Automate

- Used to `create workflows` even when you have `no dev or IT Pro` experience.
- You can create workflows `using website` or `Microsoft Power Automate mobile app`.
- Provides `easy to use design surface` that anyone can use to create flows of below types.
- Built on `Logic Apps` so supports same as connectors as Logic Apps.

#### Types of flow

- **Automated** - started by `trigger from some event`. Eg: new tweet or new file uploaded
- **Button** - Used to run `repetitive tasks` with single click from `mobile device`.
- **Scheduled**
- **Business process** - `models business process` such as stock ordering or complaints procedure.



### Comparisions

|                    | Microsoft Power | Azure Functions |
| --                 | -- | --  |
| **Design First**  | Y | Y |
| Intended Users     | Office workers and analysts    | Dev and IT Pro |
| Intended Scenarios | Self service | Advanced integration | 
| Design Tools | GUI Only. Browser and mobile app | Browser and VS Designer. Code editing is possible |
| App Lifecycle Mgmt | Includes testing and prod env | Source code can be included in Azure DevOps and SCCM |

## Code First Technologies

- When you need `more control` over performance of workflow or need to write `custom code`

### WebJobs

- `Azure App Service` is cloud-based hosting service for web app, mobile back-end and RESTful APIs.
- `WebJobs` are `part of Azure App Service` that can be used to run a program or script automatically
- WebJobs can be programmed using WebJobs SDK. SDK includes classes such as JobHostConfiguration and HostBuilder which reduces the code to interact with Azure App Service.
- SDK supports only C# and Nuget Package Manager

#### Types of WebJobs

- **Continous** - Runs in continous loop
- **Triggered** - Manually start or on a schedule

### Azure Functions

- Used to run small piece of code in cloud, without worrying about infrastructure to host code
- Supports range of templates like HTTPTrigger, TimeTrigger, BlobTrigger, CosmosTrigger etc
- 

### Comparisions
