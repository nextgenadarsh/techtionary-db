# Sidecar Pattern

- helps perform peripheral tasks that `do not depend upon main` application, but assist in `monitoring, auditing, logging` the main application
- Main and sidcar can be written in different languages/runtime
- Resources are shared among main and sidecar
- Communication between main and sidecar has low latency
- Generally used with container and called sidecar container

## Best Practices

- Keep interprocess communication in mind when designing sidecar application/component
- Make sure that we have already decided that the functionality we need from sidecar would not be fulfilled by seprate independent service or a classic daemon

## When to use

- When the component or sidecar application and its logic or functionalities can be consumed by applications written in different languages using different frameworks
- When a component or feature must be colocated on the same host as the application

## When to avoid use

- When you want to optimize interprocess communication
- Deployment of multiple application would incur a cost; it budget is limited
- When main services are independent of main application and need optimization