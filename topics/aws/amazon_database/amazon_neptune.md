# Amazon Neptune

- [Amazon Neptune](#amazon-neptune)
  - [Components](#components)
    - [Query Languages](#query-languages)
      - [Apache Tinkerpop Gremlin](#apache-tinkerpop-gremlin)
      - [World Wide Web Consortium SparQL](#world-wide-web-consortium-sparql)
    - [Database Clusters, Instances, Storage](#database-clusters-instances-storage)
      - [Endpoints](#endpoints)


- A fast, reliable, secure and fully managed graph database service
- Use cases:
  - Social networking
  - Fraud detection
  - Recommendation engines

## Components

### Query Languages

#### Apache Tinkerpop Gremlin

#### World Wide Web Consortium SparQL

### Database Clusters, Instances, Storage

#### Endpoints

- Cluster endpoint
  - points directly to current primary DB instance of a cluster
  - used by applications which require both read and write operations to the database
- Reader endpoint
  - used to connect to read replicas
  - only one reader endpoint exist inspite of having multiple replica
- Instance endpoint
  - every instance within your cluster have a unique instance endpoint
  - allows to direct certain traffic to specific instance within cluster