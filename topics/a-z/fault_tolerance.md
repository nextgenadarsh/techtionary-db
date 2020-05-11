# Fault Tolerance in monolithic architecture

Monolithic applictions have high module dependency, as they are tightly coupled. Even a single module failure brings the system down, due to cascading effect.

There are different approaches to handle fault tolerance by decoupling modules:

## Web services

Web services failure can cause a cascading failure in the system that relies on them.

## ACID (Atomicity, Consistency, Isolation, Durability)

It takes care of failures at database level. 

