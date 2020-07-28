# Azure Monitoring Options

## Azure Security Center

- Manages `security` of infrastructure from central location.
- On Premise + Cloud
- Applied by default for PaaS, but need to apply for IaaS

## Azure Application Insight

- Monitor and manage the `performance` of application
- Automatically gathers info related to performance, errors, exceptions
- Used to monitor the `release pipelines` for app.

## Azure Monitor

- Service for `collecting, combinding and analyzing` data from `different sources`.
- Collected data is `stored in workspace` that Azure Monitor can access.
- Other services like `Security Center` relies on Azure Monitor.
- Used for detailed view of app's and infrastructure's health.

## Azure Sentinel

- Used to collect data on devices, users, infrastructures, and apps across enterprise.
- Used to proactively hunt for threats and anomalies, and respond by using orchestration and automation.
- You can connect data sources like Office 365, Azure Advanced Threat Protection, AWS Cloudtrail, or on-premise sources.
- `Incidents` help you group and combine related alerts. It is used to reduce the alert noise because of scale of data.
- Use `Playbook` to automate your response to alerts in Sentinel. It can be configured using Azure Logic Apps.
- Use `Notebook` to automate investigations. Notebook is Playbook that can consist of investigation or hunting steps. 