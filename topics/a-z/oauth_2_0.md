# OAuth 2.0

- Handles `authorization` on the web, in native mobile apps and in all headless server applications
- is a delegated authorization framework means that, to complete authorization flow, it relies on an authentication mechanism

## OAuth 2.0 parties

### Resource

- Entity gettings protected from unintended accessa and usage.
- Eg: Microservices / applications

### Resource owner

- Can be either a person or an entity who has ownership of the resource. Also called the end user

### Client

- Refers to any application that is trying to access protected resource

### Authorization server

- Authenticates the end user by issuing a valid token
- Authenticates the resource owner and issues the token to the client

## Authorization grants

### Authorization code

- Typical OAuth grant that is used by server-side web application, and it is the one you would use in your ASP.NET apps

### Implicit

- Very useful for single page applications because communication in single-page applications is mostly public, but it can be private
- Authentication is done by identifying the access token that has been returned from the server to the browser, and it can then be used to access resources

### Resource owner password credentails

- Requires the user to directly enter their username and password in the application
- Useful when you are developing a first-party application, to authenticate with your own servers

### Client credentials

- Required to access the resources that are protected
- Used when the client is acting on its own behalf (client is also the resource owner)
- Suitable for server-to-server communication