# SOA  vs Microservice Architecture

|   | Service Oriented Architecture | Microservice Architecture |
|---|---|---|
| Dependency | Services are dependent on each other | Microservices are independent from each other
| Project Mgmt | Services can be managed and organized within multiple teams | Services can be developed, operated, and deployed independently
| Versioning | Diffuclt versioning | Easy versioning
| Communication | Uses Enterprise Service Bus (ESB) which can be reason for communication failure impacting entire application | If one service is down then only that microservice is affected. Other microservices will continue to handle requests.
| Data Storage | Common/sharable | Independent data storage
| Extensibility | Diffuclt to extend | Easily scalable, modular, adaptable
