# ASP.Net Core Controller

## Identifying Controller

- Class is suffixed with `Controller`, or inherits from class that has Controller suffix
- Class is decorated with `[Controller]` or `[ApiController]` attribute

## Extending Controller

- Extend `Controller` or `ControllerBase` class

### ControllerBase

- `ControllerBase` represents base class for MVC controller without view support.
- Provides some attributes like `HttpContext`, `Request`, `Response`
- ControllerBase provides `sufficient utilities for RESTful APIs` and services

### Controller

- Controller extends `ControllerBase` along with adding some properties and methods required to manage views such as `ViewData` attribute and `View()` and `PartialView()` methods

## Attributes

### [ApiController]

- Enables REST specific behaviors for controller
- Provides implicit model validation i.e. Model.IsValid
- Impmicitly defines model binding attributes so no need to specify `[FromBody]`, `[FromForm]`, `[FromHeader]`, `[FromQuery]`, or `[FromRoute]`