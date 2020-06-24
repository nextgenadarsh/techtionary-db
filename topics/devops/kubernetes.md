- [Kubernetes (K8)](#kubernetes-k8)
  - [Kubernetes Environments](#kubernetes-environments)
    - [Learning](#learning)
      - [Minikube](#minikube)
        - [Features](#features)
        - [Quick Start](#quick-start)
        - [Managing Cluster](#managing-cluster)
          - [Configuring K8s](#configuring-k8s)
        - [Interacting with Cluster](#interacting-with-cluster)
          - [kubectl](#kubectl)
          - [Dashboard](#dashboard)
          - [Services](#services)
        - [Networking](#networking)
        - [Persistent Volumns](#persistent-volumns)
        - [Mounted Host Folders](#mounted-host-folders)
        - [Private Container Registries](#private-container-registries)
        - [Add-ons](#add-ons)
      - [Kind](#kind)
    - [Production](#production)
      - [Container runtimes](#container-runtimes)
      - [Installing k8s with deployment tools](#installing-k8s-with-deployment-tools)
      - [Turnkey cloud solutions](#turnkey-cloud-solutions)
      - [On-Premise VMs](#on-premise-vms)
      - [Windows in k8s](#windows-in-k8s)
  - [Concepts](#concepts)
    - [Overview](#overview)
      - [Kubenetes Features](#kubenetes-features)
        - [Service discovery and load balancing](#service-discovery-and-load-balancing)
        - [Storage orchestration](#storage-orchestration)
        - [Automated rollouts and rollbacks](#automated-rollouts-and-rollbacks)
        - [Automated bin packing](#automated-bin-packing)
        - [Self-healing](#self-healing)
        - [Secret and configuration management](#secret-and-configuration-management)
      - [K8s does **NOT**](#k8s-does-not)
      - [K8s Components](#k8s-components)
        - [Control Plane Components](#control-plane-components)
          - [kube-apiserver](#kube-apiserver)
          - [etcd](#etcd)
          - [kube-scheduler](#kube-scheduler)
          - [kube-controller-manager](#kube-controller-manager)
          - [cloud-controller-manager](#cloud-controller-manager)
        - [Node Components](#node-components)
          - [kubelet](#kubelet)
          - [kube-proxy](#kube-proxy)
          - [Container runtime](#container-runtime)
        - [Add-ons](#add-ons-1)
          - [DNS](#dns)
          - [Web UI (Dashboard)](#web-ui-dashboard)
          - [Container resource monitoring](#container-resource-monitoring)
          - [Cluster level logging](#cluster-level-logging)
      - [K8s API](#k8s-api)
      - [Working with K8 Objects](#working-with-k8-objects)
        - [K8s Objects](#k8s-objects)
          - [Object Spec and Status](#object-spec-and-status)
          - [Describing K8s Object](#describing-k8s-object)
          - [Requied Fields](#requied-fields)
        - [K8s Object Management](#k8s-object-management)
          - [Management Technique](#management-technique)
          - [Imperative Commands](#imperative-commands)
          - [Imperative object configuration](#imperative-object-configuration)
          - [Declarative Object Configuration](#declarative-object-configuration)
        - [Object Names and IDs](#object-names-and-ids)
          - [Names](#names)
          - [UIDs](#uids)
        - [Namespaces](#namespaces)
          - [Working with Namespace](#working-with-namespace)
          - [Namespace and DNS](#namespace-and-dns)
          - [Not All Objects are in Namespace](#not-all-objects-are-in-namespace)
        - [Annotations](#annotations)
          - [Example Annotation Information](#example-annotation-information)
          - [Application and Instances of Application](#application-and-instances-of-application)
    - [Cluster Architecture](#cluster-architecture)
      - [Nodes](#nodes)
        - [Management](#management)
      - [Control Plane-Node Communication](#control-plane-node-communication)
      - [Controllers](#controllers)
      - [Cloud Control Manager](#cloud-control-manager)
    - [Containers](#containers)
      - [Overview](#overview-1)
        - [Container Images](#container-images)
        - [Container runtimes](#container-runtimes-1)
      - [Images](#images)
        - [Image Names](#image-names)
        - [Updating Images / Pull Policies](#updating-images--pull-policies)
        - [Using Private Registry](#using-private-registry)
        - [Configuring Nodes to authenticate to a Private Registry](#configuring-nodes-to-authenticate-to-a-private-registry)
      - [Container Environment](#container-environment)
        - [Container Information](#container-information)
        - [Cluster Information](#cluster-information)
      - [Runtime Class](#runtime-class)
      - [Container Lifycycle Hooks](#container-lifycycle-hooks)
        - [Container Hooks](#container-hooks)
          - [PostStart](#poststart)
          - [PreStop](#prestop)
    - [Workloads](#workloads)
      - [Pods](#pods)
        - [Pod](#pod)
    - [Services, Load Balancing, and Networking](#services-load-balancing-and-networking)
      - [Service](#service)
        - [Service Resources](#service-resources)
          - [Cloud-native service Discovery](#cloud-native-service-discovery)
        - [Defining a service](#defining-a-service)
      - [Service Topology](#service-topology)
      - [EndpointSlices](#endpointslices)
      - [DNS for Services and Pods](#dns-for-services-and-pods)
      - [Connecting Application with Services](#connecting-application-with-services)
      - [Ingress](#ingress)
      - [Ingress Controllers](#ingress-controllers)
      - [Network Policies](#network-policies)
      - [Adding entries to Pod /etc/hosts with HostAliases](#adding-entries-to-pod-etchosts-with-hostaliases)
      - [IPv4/IPv6 dual-stack](#ipv4ipv6-dual-stack)
    - [Storage](#storage)
      - [Volumes](#volumes)
      - [Persistent Volumes](#persistent-volumes)
      - [Volume Snapshots](#volume-snapshots)
      - [CSI Volume Cloning](#csi-volume-cloning)
      - [Storage Classes](#storage-classes)
      - [Volume Snapshot Classes](#volume-snapshot-classes)
      - [Dynamic Volume Provisioning](#dynamic-volume-provisioning)
      - [Node-specific Volume Limits](#node-specific-volume-limits)
    - [Configuration](#configuration)
    - [Security](#security)
    - [Policies](#policies)
    - [Scheduling and Eviction](#scheduling-and-eviction)
    - [Cluster Administration](#cluster-administration)
    - [Extending Kubernetes](#extending-kubernetes)
  - [Tasks](#tasks)
    - [Install Tool](#install-tool)
    - [Administer a Cluster](#administer-a-cluster)
    - [Configure Pods and Containers](#configure-pods-and-containers)
    - [Manage K8s Objects](#manage-k8s-objects)
    - [Inject Data into Applications](#inject-data-into-applications)
    - [Run Applications](#run-applications)
    - [Run Jobs](#run-jobs)
    - [Access](#access)
  - [Tutorials](#tutorials)

# Kubernetes (K8)

- Opensource based on Google Kubernetes
- Managed container orchestration service
- Operates at container leve rather than hardware level

## Kubernetes Environments

### Learning

#### [Minikube](https://kubernetes.io/docs/setup/learning-environment/minikube/)

- Tool which makes it easy to `run K8s locally`
- Runs a `single node cluster` inside VM

##### Features

- DNS
- NodePorts
- ConfigMaps and Secrets
- Dashboards
- Container Runtime
- Enabling CNI (Container Network Interface)
- Ingress

##### Quick Start

- Create and configure a `VM` that runs a `single node K8s cluster`
  - `minikube start`
  - Configures `kubectl` installation to communicate with the cluster
  - Note: **Do not start minikube Virtual Machine from Hypervisor**
- Create deployment from existing image
  - `kubectl create deployment hello-minikube --image=k8s.gcr.io/echoserver:1.10`
- Expose deployment as NodePort service
  - `kubectl expose deployment hello-minikube --type=NodePort --port=8080`
- Check if Pod is up and running
  - `kubectl get pod --context=minikube`
- Get the exposed service Url
  - `minikube service hello-minikube --url`
- Delete the service
  - `minikube delete services hello-minikube`
- Delete deployment
  - `minikube delete deployment hello-minikube`
- Shut down minikube VM but preserve all cluster state and data. It gets restored when starting minikube cluster
  - `minikube stop`
- Shutdown and delete minikube VM. No data or state is preserved.
  - `minikube delete`
- Check minikube status
  - `minikube status`
- Upgrade minikube
  - `brew update`
  - `brew upgrade minikube`

##### Managing Cluster

- Login to minikube virtual machine
  - Default username: docker
  - Default password: tcuser

###### Configuring K8s

- Minikube allows to configure k8s components using --extra-config flag on `minikube start` command
- Eg: `minikube start --extra-config=kubelet.MaxPods=5 --extra-config=apiserver.authorization-mode=RBAC`

##### Interacting with Cluster

###### kubectl

- Set context for kubectl: `kubectl config use-context minikube`

###### Dashboard

- `minikube dashboard`

###### Services

- Access a service exposed via NodePort
  - `minikube service -n <namespace> --url <name>`

##### Networking

- minikube is exposed to the host via host-only IP address obtained with `minikube ip`
- Any service of type `NodePort` can be accessed over this IP address on the NodePort
- Determine NodePort of service:
  - `kubectl get service $SERVICE --output='jsonpath="{.spec.ports[0].nodePort}"'`

##### Persistent Volumns

- Persisted volumns are mapped to a directory inside the minikube VM
- Minikube is configured to persist files stored under host directories:
  - /data
  - /var/lib/minikube
  - /var/lib/docker

##### Mounted Host Folders

- `Some driver mount a host folder within VM` so that you can easily share files between host and VM

##### Private Container Registries

##### Add-ons

- Place the addons in ~/.minikube/addons directory

#### Kind

### Production

#### Container runtimes
#### Installing k8s with deployment tools
#### Turnkey cloud solutions
#### On-Premise VMs
#### Windows in k8s

## Concepts

### Overview

#### Kubenetes Features

##### Service discovery and load balancing

- K8s can expose container using DNS name or own IP address.

##### Storage orchestration

- Allows to automatically mount a storage system of choice such as local storage or cloud providers

##### Automated rollouts and rollbacks

- Desired state is described for deployed containers and K8s changes actual state to desired state

##### Automated bin packing

- K8s can fit containers onto nodes to make the best use of resources as per container config specified for CPU and RAM

##### Self-healing

##### Secret and configuration management

- K8s lets you store and manage sensitive information such as passwords, OAuth tokens and SSH keys.
- We can deploy and update secrets and app config without rebuilding container images and without exposing secrets in stack configuration.

#### K8s does **NOT**

- limit types of application supported. Applicaiton should be able to run in container.
- deploy source code and does not build application
- provide app level services such as middleware, data-processing frameworks, databases, caches, cluster storage systems as built-in services.
- dictate logging, monitoring, or alerting solutions
- provide or mandate a configuration language/system
- provide or adapt any comprehensive machine configuration, maintenance, mgmt, or self-healing

#### K8s Components

##### Control Plane Components

- Makes globa decision about the clusters
- Components can be run on many machines but runs normally on same machine for simplicity

###### kube-apiserver

- Frontend for the control plane which exposes K8s API
- Designed to scale horizontally

###### etcd

- Consistent and highly-available `key value store` used as `K8s backing store` for all cluster data
- Make sure to have backup plan for etcd data using Built-in Snapshot or Volume Snapshot

###### kube-scheduler

- Watches for newly created Pods with no assigned node, and select a node to run
- Scheduling decision factors:
  - Individual and collective resource requirements
  - Hardware/software/policy constraint
  - Affinity and Anti-Affinity specifications
  - Data locality
  - Inter-workload interferences
  - Deadlines

###### kube-controller-manager

- Runs controller processes
- Controller processes:
  - Node Controller
    - Responsible for noticing and responding when Node goes down
  - Replication Controller
    - Responsible for maintaining correct number of Pods for every replication controller object in the system
  - Endpoint Controller
    - Populates the Endpoint objects (join services and pods)
  - Service account and Token controllers
    - Create default accounts and API access tokens for new namespaces

###### cloud-controller-manager

- Lets you link cluster into cloud provider API
- Separates out the components that interact with cloud platform from cluster
- Only runs controllers that are specific to cloud provider
- Dependent controllers:
  - Node controller
  - Route controller
  - Service controller: creating, upating, deleting cloud provider load balancers

##### Node Components

- Runs on every node, maintaing running Pods and providing providing K8s runtime environment

###### kubelet

- An agent that runs on each node on the cluster
- Makes sure that containers are running in a Pod
- Takes a PodSpecs and ensures that containers described in those PodSpecs are `running and healthy`
- Does not manage container NOT created by K8s

###### kube-proxy

- A network proxy that runs on each Node implementing part of K8s service concept
- Maintains network rules on Nodes. Network rules allow communication to Pods from network session
- Uses OS packet filtering layer if it's available otherwise forwards traffic itself

###### Container runtime

- Sotware that is responsible for running containers
- Supported container runtimes: Docker, containered, CRI-O

##### Add-ons

- Use K8s resources (DaemonSet, Deployment etc) to implement `cluster level features`
- Namespaced resources for addons belong within the kube-system namespace

###### DNS

- All K8s cluster should have cluster DNS
- Cluster DNS: DNS server which serves DNS records for K8s services

###### Web UI (Dashboard)

- General purpose web based UI for K8s clusters
- Allows users to manage and troubleshoot apps running the cluster, as well as cluster itself

###### Container resource monitoring

- Records generic time-series metrics about containers in a central database, and provides a UI for browsing that data

###### Cluster level logging

- Responsible for saving container logs to a central log store with search/browsing interface

#### K8s API

- Lets you query and manipulate the state of objects in K8 API

#### Working with K8 Objects

##### K8s Objects

- Persisted entities in K8s system
- K8s uses these entities to represent the state of your cluster
- K8s objects describe:
  - What containerized applications are running and on which Nodes
  - Resources available to those resources
  - The policies around how those apps behave, such as restart policies, upgrades and fault-tolerance
- A K8s object is "record of intent", a desired state

###### Object Spec and Status

- Almost every K8s object includes two nested object fields that govern configuration: the object `spec` and the object `status`
- `spec` describes the desired state
- `status` describes the current state updated by K8s

###### Describing K8s Object

- When we create an object in K8s, we need to provide `spec` to K8s API or `kubectl`
- Mostly we provide .yaml file to `kubectl`, and it converts to JSON to pass to K8s API
- Apply .yaml configuration using kubectl
  - `kubectl apply -f https://k8s.io/examples/application/deployment.yaml --record`

###### Requied Fields

- **apiVersion**: K8s API version
- **kind**: Kind of object to be created, such as Deployment
- **metadata**: Helps uniquely identify the object, including name, UID, and namespace
- **spec**: Desired state of object

##### K8s Object Management

- `kubectl` supports ways to create and manage K8s objects

###### Management Technique

| Technique |  Operates on | Recommended environment | Supported writers | Learning curve
| --- | --- | -- | -- | -- |
|  Imperative command |  Live objects | Development projects | 1+ | Lowest
| Imperative object config | Individual files | Production Projects | 1 | Moderate
| Declarative object config | Directories of files | Production projects | 1+ | Highest

###### Imperative Commands

- User operates directly on live objects in a cluster
- Provides no history of previous configurations
- Examples:
  - `kubectl run nginx --image nginx` or
  - `kubectl create deployment nginx --image nginx`

###### Imperative object configuration

- Examples:
  - `kubectl create -f nginx.yaml`
  - `kubectl delete -f nginx.yaml -f redis.yaml`
  - `kubectl replace -f nginx.yaml`

###### Declarative Object Configuration

- Examples:
  - Check diff to be applied: `kubectl diff -f configs/`
  - Create or patch: `kubectl apply -f configs/`
  - Recursive: `kubectl diff -R -f configs/`
  - Recursive: `kubectl apply -R -f configs/`

##### Object Names and IDs

- Each object in cluster has a unique `Name` **for that object type** in cluster
- Each object in cluster has a unique `UID` across cluster

###### Names

- A client provided string refers to an object in resource url like `/api/v1/pods/pod-name`
-  Name constraints:
   -  DNS Subdomain Names - follow DNS subdomain naming standards
   -  DNS Label Names - follow DNS label standards
   -  Path Segment Names - names should be able to be safely encoded as a path segment

###### UIDs

- K8s `system generated` string to uniquely identify objects

##### Namespaces

- K8s supports multiple `virutal clusters`, called `Namespace`, backed by same physical cluster
- It provide a scope for names. Resource names need to be unique across Namespace, but not across Namespace**s**
- Namespaces can not be nested inside one another
- Use `labels` to distinuguish resources within same namespace

###### Working with Namespace

- Get namespaces: `kubectl get namepsace`
- Initial namespaces: 
  - default - for objects with no other namespace
  - kube-system - for objects created by K8s
  - kube-public - reserved for cluster usage and readable by all users
  - kube-node-lease - for lease objects associated with each Node
- Set namespace for request: Use `--namespace` flag
  - Eg: `kubelet run nginx --image=nginx --namespace=<namespace-name>`
  - Eg: `kubelet get pods --namespace=<namespace-name>`
- Set namespace **permanently**: 
  - `kubectl config set-context --current --namespace=<namespace-name>`
  - Validate: `kubectl config view --minify | grep namespace:`

###### Namespace and DNS

- When you create a service, it creates a corresponding DNS entry like `<service>.<namespace>.svc.cluster.local`

###### Not All Objects are in Namespace

- Namespace objects: Pods, Services, Replication Controllers etc
  - `kubectl api-resources --namespaced=true`
- Non-Namespace objects: Nodes, PersistentVolumes
  - `kubectl api-resources --namespaced=false`

##### Annotations

- Used to attach arbitrary non-identifying metadata to objects to be used by tools and libraries
- Attaching metadata
  ```
  "metadata": {
    "annotations": {
      "key1": "value1",
      "key2": "value2"
    }
  }
  ```

###### Example Annotation Information

- Fields managed by declarative configuration layer
- Build, release or image information like timestamps, releaseId, gitBranch, PR numbers, images hashes, registry address
- Pointers to logging, monitoring, analytics, or audit repositories
- Client library or tool information that can be used for debugging purpose like name, version and build information
- User or tool/system provenance information such as URLs of related objects from other ecosystem components
- Lightweight rollout tool metadata: for example, config or checkpoints
- Contact nuumber of person responsible or directory entries that specify where that info can be found
- Directives from end-user to the implementations to modify behavior or engage non-standard features
  ```
  metadata
    name: annotation-demo
    annotations:
      imageRegistry: "https://hub.docker.com"
    ```

##### Field Selectors

- Resource filters which let you select K8s resources based on the value of one or more resource fields
- Examples:
  - `metadata.name=my-service`
  - `status.phase!=Running`
  - `kubectl get pods --field-selector status.phase=Running`
- Supported fields
  - Vary by K8s resource type
  - All resource supports `metadata.name` and `meta.namespace`
  - Invalid field: `kubectl get ingress --field-separator foo.bar=baz`
- Supported Operators
  - `=` , `==`, `!=`
  - Eg: `kubectl get services --all-namespaces --field-selector metadata.namespace!=default`
- Chained Selectors use comma seprated list
  - `kubectl get pods --field-selector=status.phase!=Running,spec.restartPolicy=Always`
- Multiple Resource Types
  - `kubectl get statefulsets,services --all-namespaces --field-selector metadata.namespace!=default`

##### Recommended Labels

- Shared labels and annotations share a common prefix: `app.kubernetes.io`
- Labes without a prefix are `private` to users
- Shared prefix ensures that shared labels do not interfare with custom user labels
- Example:
  ```
  metadata:
    labels:
      app.kubernetes.io/name: mysql
      app.kubernetes.io/instance: wordpress-custom
      app.kubernetes.io/version: "5.7.21"
      app.kubernetes.io/component: database
      app.kubernetes.io/part-of: database
      app.kubernetes.io/managed-by: helm
    ```
###### Application and Instances of Application

- The name of application and instance name are recorded separately
- Every instance of an application must have a unique name 
- `Deployment` is used to oversee the pods running the appliation itself
- `Service` is used to expose the application

### Cluster Architecture

#### Nodes

- K8s runs your workload by placing `Containers` into `Pods` to run on `Nodes`
- A Node may be `physical or virtual machine` depending on cluster
- Each node contains services necessary to run Pods, managed by ControlPlane
- Node Components:
  - `kubelet`
  - a container runtime
  - `kube-proxy`

##### Management

- Two ways to add Nodes to the api server:
  - The `kubelet` on a node self-register to the clontrol plane
  - Manually add a node object
- Spec
  ```
  {
    "kind": "Node"
    "apiVersion" : "v1"
    "metaData": {
      "name": "10.240.79.157",
      "labels": {
        "name": "my-first-K8s-node"
      }
    }
  }
  ```
- Node Status:
  - `kubectl describe node <node-name>`
- Node Conditions:
  - Ready: healthy and realy to accept Pods
  - DiskPressure: disk capacity is low
  - MemoryPressure: node memory is low
  - PIDPressure: too many processed on the node
  - NetworkUnavailable: network of node is currently not configured
  - 

#### Control Plane-Node Communication

#### Controllers

#### Cloud Control Manager

### Containers

#### Overview

- Technology for packaging the compiled code for an application along with dependencies it needs at run time
- It decouples applications from underlying host infrastructure
- Container is immutable

##### Container Images

- Ready-to-run software package, containing everything needed to run an application

##### Container runtimes

- Software responsible for running containers
- K8s support several container runtimes: Docker, containered, CRI-O

#### Images

##### Image Names

- Eg: pause, example/myapp, kube-apiserver
- It can include registry hostname like `myregistry.example:10443/imagename`
- Default hostname is Docker public registry
- `Tags` let you identify different versions of the same series of images
- Tag name consists of alphanumeric, dash(-), underscore(_) and period(.) like `v1.34.2`

##### Updating Images / Pull Policies

- Default pull policy is `IfNotPresent` which skips downloading image if it already exists
- To force a image to be pulled everytime
  - set `imagePullPolicy` of container to `Always`
  - omit `imagePullPolicy` and use `:latest` as tag for image to use
  - omit `imagePullPolicy` and tag for the image to use
  - enable `AlwaysPullImages` admission controller

##### Using Private Registry

- Private registries may require keys to read images from them
- Credentials can be provided in many ways:
  - Configure Nodes to authenticate to a private registry
    - all pods can read any configured private registries
    - requires node configuration by cluster administrator
  - Pre-pulled images
    - all pods can use any images cached on a node
    - requires root access to all nodes to setup
  - Specify image pull secret on a Pod
    - only pods which provide own keys can access the private registry
  - Vendor specific or local extensions

##### Configuring Nodes to authenticate to a Private Registry

- You can configure Docker container runtime to authenticate to a private container registry
- Docker stores keys for private registries in `$HOME/.dockercfg` or `$HOME/docker/config.json`

#### Container Environment

- Provides several resources to containers
  - A filesystem, which is combination of an image and one or more volumes
  - Information about the container itself
  - Information about other objects in the cluster

##### Container Information

- The `hostname` of a container is the name of the Pod in which container is running. It is available through `hostname` command
- Pod name and namespace are available as environment variables throught the downward api
- Use defined environment variables are also available

##### Cluster Information

- A list of all services that were running when a container was created is available to that container as environment variables
- For a service named `foo` that maps to conainer `bar`, variables are:
  - `FOO_SERVICE_HOST=<the host the service is running on>`
  - `FOO_SERVICE_PORT=<the port the service is running on>`
- Services have dedicated IP addresses and are available to container via DNS, if DNS addon is enabled

#### Runtime Class

#### Container Lifycycle Hooks

- Hooks enable container to be aware of events in mgmt lifecycle and run code implemented in a handler when corresponding lifycycle hooks is executed

##### Container Hooks

- Two hooks are exposed to containers

###### PostStart

- Executes immediately after a container is created.
- No parameters are passed to the handler

###### PreStop

- Called immediately before a container is terminated due to an API request or mgmt event such as liveness probe failure, preemption, resource contention and others

### Workloads

#### Pods

##### Pod

- A unit of deployment: a single instanceof an application in K8s
- Encapsulates application's container, storage resources, IP address etc
- Pods in a cluster can be used two ways:
  - Pods running single container
  - Pods running multiple container
- You can scale horizontally by replicating instance of application using multiple Pods

### Services, Load Balancing, and Networking

#### Service

- An abstract way to expose an application running on a set of Pods as a network service
- K8s gives Pods their own IP addresses and a single DNS name for a set of Pods, and can load-balance across them

##### Service Resources

- A service is an abstraction which defines a logical set of Pods and a policy by which to access them (pattern called microservice)

###### Cloud-native service Discovery

- You can query the API server for endpoints

##### Defining a service

#### Service Topology

#### EndpointSlices

#### DNS for Services and Pods

#### Connecting Application with Services

#### Ingress

#### Ingress Controllers

#### Network Policies

#### Adding entries to Pod /etc/hosts with HostAliases

#### IPv4/IPv6 dual-stack

### Storage

#### Volumes

#### Persistent Volumes

#### Volume Snapshots

#### CSI Volume Cloning

#### Storage Classes

#### Volume Snapshot Classes

#### Dynamic Volume Provisioning

#### Node-specific Volume Limits

### Configuration

### Security

### Policies

### Scheduling and Eviction

### Cluster Administration

### Extending Kubernetes

## Tasks

### Install Tool

### Administer a Cluster

### Configure Pods and Containers

### Manage K8s Objects

### Inject Data into Applications

### Run Applications

### Run Jobs

### Access 

## Tutorials

