# Scalability

- capability of a system to handle increasing workload

## Strategies/types of scalability

### Vertical scaling / scaling up

- Scales whole systems
- Requires downtime to scale
- It has the limit to the extent to which it can be beneficial
 
#### Approach I: 

- Find parts of the modules that cause the application to slow down, due to longer execution time
- Optimize code to be efficient so that it consumes less memory and processing power.

#### Approach II:

- Add more resources to IT infrastructure, such as upgrade RAM or add more disk drives.

### Horizontal scaling / Scaling out

- Find the modules which show higher impact on overall performance
- Implement load balancing to process greater amount of work
- Adding more servers does not require downtime
