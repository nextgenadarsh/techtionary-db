# Elastic Beanstalk

- [Elastic Beanstalk](#elastic-beanstalk)
  - [Core Components](#core-components)
    - [Application Version](#application-version)
    - [Environment](#environment)
    - [Environment Configurations](#environment-configurations)
    - [Environment Tier](#environment-tier)
      - [Web server environment](#web-server-environment)
      - [Worker environment](#worker-environment)
    - [Configuration Template](#configuration-template)
    - [Platform](#platform)
    - [Applications](#applications)
  - [Workflow](#workflow)
  - [Deployment Options](#deployment-options)
    - [All at once (Default option)](#all-at-once-default-option)
    - [Rolling](#rolling)
    - [Rolling with additional batch](#rolling-with-additional-batch)
    - [Immutable](#immutable)

- AWS managed service that takes your uploaded code of your web application and automatically provisions and deploys the required resources within AWS to make the web application operational.
- Resources include EC2, Auto Scaling, application health-monitoring and Elastic Load Balancing, in addition to capacity provisioning.

## Core Components

### Application Version

- reference to a section of deployable code inside S3

### Environment

- refers to an application version that has been deployed on AWS resources

### Environment Configurations

- a collection of parameters and settings, that dictate how an environment will have its resources

### Environment Tier

- reflects on how Elastic beanstalk provisions resources based on the application. 

#### Web server environment

- Typically used for standard web applications that operate and serve requests over HTTP port 80
- Route 53
- Elastic Load Balancer
- Auto Scaling
- EC2 Instances
- Security Groups

#### Worker environment

- Typically used for applications that will have a back-end processing tasks, that will interact with AWS SQS.
- SQS Queue
- IAM Service Role
- Auto Scaling
- EC2 Instances

### Configuration Template

- is the template that provides the baseline for creating a new, unique, environment configuration

### Platform

- Culmination of components which you can build your application upon using Elastic Beanstalk

### Applications

- a collection of different elements, such as environments, environment configurations and application versions

## Workflow

- Create application > Upload version > Launch environment > Manage environment

## Deployment Options

### All at once (Default option)

- Roll the application out to your resources at the same time

### Rolling

- Minimise the amount of disruption that is caused
- Deploy your application in batches

### Rolling with additional batch

- Similar to Rolling
- Environment is updated in batches until all your resources have the new update

### Immutable

- Create an entirely new set of instances
- Served through a temporary autoscaling group behind your ELB
- The old environment would be removed and the autoscaling group updated

