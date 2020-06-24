# Data Transfer Object (DTO)

## Types of model

### Domain model

- Describes entities and resources
- Often reflects `schema of our data source`, and very close to the lower level and business logic of application

### Request model

- Represents model of the request
- `Each action` in controller usually has its own `Request model`

### Response model

- View model, or presentation model of the web service
- Represents response of request 
- `Each action` in controller usually has its `own Response model`