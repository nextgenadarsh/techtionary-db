# Elastic Container Service (ECS)

- [Elastic Container Service (ECS)](#elastic-container-service-ecs)
  - [Launching an ECS Cluster](#launching-an-ecs-cluster)
    - [Fargate Launch](#fargate-launch)
    - [EC2 Launch](#ec2-launch)

- Allows you to run Docker-enabled applications packaged as containers across a cluster of EC2 instances

## Launching an ECS Cluster

### Fargate Launch

- Requires you to specify the CPU and memory required, define networking and IAM policies, in addition to you having to package your application into containers

### EC2 Launch

- You are responsible for patching and scaling your instances and you can specify instances type and how many containers should be in a cluster.

