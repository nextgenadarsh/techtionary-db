# Anti-Corruption Layer Pattern

- Two different subsystems do not share the same semantics but they can talk to each other with the implementation of a layer (mostly with the help of Facade or Adapter patterns)
- Works as adapter between two subsystems

## Pros

- Helps to maintain both the legacy system and the new system
- Helps to make a proper translation between two different subsystems

## Cons

- It may add latency to inter-system calls
- It provides a function that needs to be managed and maintained
- Need to make sure that transactions are protected and that the data integrity can be checked