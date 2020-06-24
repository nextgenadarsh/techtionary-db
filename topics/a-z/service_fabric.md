# Service Fabric

- is a collection of services
- each collection in group into subsystems
- every subsystem has own specific responsibility
- allows us to write applications of different types like
  - Scalable applications
  - Manageable applications
  - Testable application
- offers multiple ways in which we can write and manage our services.
- Services can be any compiled executable program written in any language or code running in a container that is hosted on a Service Fabric cluster.

## Service Fabric Sub-systems

### Transport

- provides a communication channel for intra and inter cluster communication
- Channels are secured by X509 certificate or windows security
- Supports both one-way and request-response communicaton
- Internal to service fabric and can not be used by developers

### Fedaration

- responsible for logical grouping of virtual or physical machines to form service fabric cluster
- Key responsibilities include failure detection, leader election, and routing
- It forms a ring topology over nodes that have been allocated for cluster
- A token-leasing mechanism along with heartbeat check is implemented to detect failure, perform leader election, and to achieve consistent routing

### Reliability

- ensured by managing failover, replicating, and balancing resources across nodes in cluster
- Replicator logic is responsible for replicating state across multiple instance of service
- Main task of this subsyste is to maintain consistency between primary and secondary replicas in service deployment
- It interacts with failover unit and reconfiguration agent in order to understand what needs to be replicated
- Resource Manager:
  - deploys the application of the available nodes, while considering the placement constraints.
  - responsible for lifecycle of applications starting from provisiong to deprovisioning
  - integrates with health manager in mgmt subsystem to perform health checks during service upgrades

### Management

- Deals with application lifecycle management of workloads that have been deployed on service fabric cluster
- Developers can access mgmt subsystem functionalities through admin APIs or powershell cmdlets to provision, deploy, upgrade or deprovision applications without any downtime.
- Has three key components:
  - Cluster manager - interacts with failover manager 
  - Health manager - responsible for monitoring health of applications, services, nodes, partitions and replicas. Also responsible for aggregating health status and storing it in centralized health store
  - Image store
- 

### Hosting

- takes care of managing application deployments, within the scope of a node
- Cluster manager signals the Hosting subsystem, informing it about the application deployments to be managed on a particular node. 
- Manages the lifecycle of the application on that node.
- Interacts with the Reliability and Management subsystem to ensure health of each deployment

### Communication

- Provides features for service discovery 
- Provides instra-cluster messaging features that use a naming service
- `Naming service` is used to locate a service withing a cluster. It also lets users securely communicate with any node on a cluster, retrieve service meta data, and manage service properties. It also exposes APIs which allows user to resolve network locations for each service, despite being dynamically placed

### Testability

- Provides a list of tools for developers, deployment engineers, and testers so that they can introduce controlled faults and run test scenarios to validate state transitions and behaviors of services that have been deployed on service fabric
- Fault analysis service is automatically started when a cluster is provisioned or when a fault action or test scenario has initiated a command

## Service Farbric Cluster Resource Manager

- can be a central service that runs within our clusters
- manages the specified state of the services within the cluster; with relevant resource consumption and placement rules

## Service Fabric Programming Models

### Guest Executable

- existing executable that can be written in any language, and it can be run as a service in application.
- Service Fabric APIs have not been used by these guest executables

### Container

- is a part of the complete filesystem and contains tools, the runtime, and system libraries

### Reliable services

- is a lightweight framework for writing services that integrate with service fabric platform and use its features
- provide a minimal set of APIs that allow the service fabric runtime to manage the life cycle of services to enable interaction with runtime
- Application framework is minimal, so that you have full control over design and implementation choices. It can also be used to host any other app framework such as ASP.NET Core.

### ASP.NET Core

- is an open source and cross-platform framework that we can use to build web apps, IoT apps, and mobile backends
- Service fabric integrates with ASP.NET Core so that we can write both stateless and stateful apps that can take advantage of reliable collections and service fabric's advanced orchestration capabilities

### Reliable Actors

- build on top of reliable services, is an application framework that implements the Virtual Actor pattern, based on the actor design pattern
- framework uses independent units of compute and state with a single-threaded execution called actors. It provides built-in communication for actors and preset state persistence and scale-out configurations.