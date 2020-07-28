# Life Cycle Madness

We should avoid following cases to avoid performance issues:

## Consuming Scoped dependencies in a Singleton consumer

- Runtime will throw exception
- Runtime can not create a scoped service for each request when it is referred to by a Singleton instance.

## Consuming Transient dependencies in a Singleton consumer

- Runtime will NOT throw exception
- Runtime will not create a new instance of trasient service each time.
- Transient service will be initialized only once because it is declared in a Singleton.