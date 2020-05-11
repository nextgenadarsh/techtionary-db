# Monolithic Architecture

## What Monolithic is

- Self-contained
- Simple code change in one module may break major functionality in other module
- Modules/components are tightly coupled
- All components must be deployed consistently

## What Monolithic is not

## Challenges of monolithic architecture

- Security
  - No way to identify user via web service due to there being no clear consensus on a strong authentication scheme
- Response Time - time service takes to respond
  - Huge code and complex logic makes the response time of web service long
- Throughput - rate of processing requests
  - One common service call failure out of 10 calls would mean a 10% lower conversion rate
- Frequent downtime
  - Web services in monolith eco system are bound to be down during upgrade/deployment/failure
- Technology adoption
  - Requires whole application to be upgraded, tested, deployed
- Availability - percentage of time during which service is operating
  - Percentage of time during which a service is operating
- High-risk deployment
- Complex code deployment
- Longer testing time
- Unplanned downtime
- Production bugs
- Large code base
- Too many business modules
- Codebase complexity
- Single point of failure
  - One module failure may affect whole system
- Scalability for entire system
- Intermodule dependency
- Inability to easily adapt to new technology
- Organizational alignment
  - The same goal- timely and bug-free delivery at the end of each day
  - A different perspective- inter-dependency among different teams and components hampers overall delivery
- Big database
  - Single schema- creates confusion reagarding various tables that belong to different modules
  - Numerous stored procedures- prove to be a baffeling task to optimize them or breaking them down into smaller units
  - Any database change needs to be reviewed carefully before deployment
