# AWS Batch-CF

- [AWS Batch-CF](#aws-batch-cf)
  - [Components](#components)
    - [Jobs](#jobs)
    - [Job Definitions](#job-definitions)
    - [Job Queues](#job-queues)
    - [Job Scheduling](#job-scheduling)
    - [Compute Environments](#compute-environments)

- used to manage and run batch computing workloads within AWS

## Components

### Jobs

- is classed as the unit of work that is to be run by AWS batch

### Job Definitions

- define specific parameters for the Jobs themselves and dictate how the Job will run and with what configuration

### Job Queues

- Jobs that are scheduled are placed into a Job Queue until they run

### Job Scheduling

- Takes care of when a Job should be run and from which compute environment

### Compute Environments

- are the environments containing the compute resources to carry out the Job
  - Managed Environments
    - Service will handle provisioning, scaling and termination of compute instances
    - is created as an Amazon ECS Cluster
  - Unmanaged Environments
    - are provisioned, managed and maintained by you

