# ASP.Net MVC

## Model

- Define the domain model of application
- Don't contain any reference to our data sources and databases

## View 

- Respresents the data in form of HTML pages. In case of web services, views are not included as models are serialized as JSON, XML
- Should not contain business logic

## Controller

- Handles requests from users
- Take information from request, and update the model
