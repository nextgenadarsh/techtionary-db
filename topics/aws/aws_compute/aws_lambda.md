# AWS Lambda

- [AWS Lambda](#aws-lambda)
  - [Working with AWS Lambda](#working-with-aws-lambda)
  - [Components](#components)
    - [Lambda function](#lambda-function)
    - [Event Source](#event-source)
    - [Trigger](#trigger)
    - [Downstream Resources](#downstream-resources)
    - [Log streams](#log-streams)
  - [Creating Lambda function](#creating-lambda-function)

- Azure Equivalent: Function App
- Serverless compute service that allows you to run your application code without having to manage EC2 instances.
- Allows you to focus on code and business logic instead of infrastrucuture

## Working with AWS Lambda

- You can either upload your code to Lambda, or write it within the code editors that Lambda provides.
- Supported Languages: Node.js, C#, Java, Python, Go, PowerShell and Ruby
- Configure your Lambda functions to execute upon specific triggers from supported event sources.
- Once specific trigger is initiated, Lambda will run your code using only required compute power as defined

## Components

### Lambda function

- is compiled of your own code that you want Lambda to invoke as per defined triggers

### Event Source

- are AWS services that can be used to trigger your Lambda functions

### Trigger

- is essentially an operation from an event sources that causes the function to invoke

### Downstream Resources

- are resources that are required during the execution of your Lambda function

### Log streams

- help to identify issues and troubleshoot issues with your Lambda function

## Creating Lambda function

- Selecting a Blueprint
  - Select a blueprint template provided by AWS Lambda
- Configure Triggers
- Configure Function