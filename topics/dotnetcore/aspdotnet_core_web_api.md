# ASP.Net Core Web APIs

- It follows new, lightweight, cross-platform and opensource way to apps
- Designed to be cloud ready i.e. framework is no longer part of server
- .Net core maintains high level of modularity which allows you to use only what is needed in tailored apps
- .Net core introduces new hosting solutions for web apps
  - Kestrel: 
    - Default HTTP server for .Net core
    - Supports HTTPS and web socket and it is crossplatform
    - Kerstrel is normally combined with a `reverse-proxy` such as NGINX, IIS or Apache
  - HTTP.sys:
    - Window only HTTP server which can be used an alternative to Kestral on windows