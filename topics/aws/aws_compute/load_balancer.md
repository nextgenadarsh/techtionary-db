# Load Balancer

- [Load Balancer](#load-balancer)
  - [Elastic Load Balancer (ELB)](#elastic-load-balancer-elb)
    - [Load Balancer Types](#load-balancer-types)
      - [Application Load Balancer](#application-load-balancer)
      - [Network Load Balancer](#network-load-balancer)
      - [Classic Load Balancer](#classic-load-balancer)
    - [Components of ELB](#components-of-elb)
      - [Listeners](#listeners)
      - [Target Groups](#target-groups)
      - [Rules](#rules)
      - [Health Checks](#health-checks)
      - [Internal ELB or Internet-Facing ELB](#internal-elb-or-internet-facing-elb)
      - [ELB Nodes](#elb-nodes)
    - [Cross-Zone Load Balancing](#cross-zone-load-balancing)

## Elastic Load Balancer (ELB)

### Load Balancer Types

#### Application Load Balancer

- Flexible feature set for your web applications running the HTTP or HTTPS protocol
- Operates at the request level
- Advanced routing, TLS termination and visibility features targeted at application architectures
- You can target the different target groups based on condition
- Operates at Application layer of OSI model analyzing the HTTP header
- Supports HTTP and HTTPS

#### Network Load Balancer

- Ultra-high performance while maintaining very low latencies
- Operates at the connection level, routing traffic to targets within your VPC
- Handles millions of requests per second
- Operates Transport layer of OSI model purely based on TCP protocol
- Supports TCP, TLS and UDP

#### Classic Load Balancer

- Used for applications that were built in the existing EC2 classic environment
- Operates at both the connection and request level
- Supports TCP, SSL/TLS, HTTP and HTTPS protocols
- Support for sticky session using application-generated cookies

### Components of ELB

#### Listeners

- One more more listeneres for ELB can be defined

#### Target Groups

- Group of resources that you want your ELB to route requests to

#### Rules

- are associated to each listener that you have configured within your ELB

#### Health Checks

#### Internal ELB or Internet-Facing ELB

#### ELB Nodes

- For each AZ selected an ELB node will be placed within that AZ

### Cross-Zone Load Balancing

