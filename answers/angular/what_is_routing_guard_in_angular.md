Angular's route guards

- are `interfaces`
- can tell the router whether or not it should allow navigation to a requested route
- make this decision by `looking for a true or false return` value from a class which implements the given guard interface
- Guards:
  - [CanActivate](https://angular.io/api/router/CanActivate)
  - [CanActivateChild](https://angular.io/api/router/CanActivateChild)
  - [CanDeactivate](https://angular.io/api/router/CanDeactivate)
  - [CanLoad](https://angular.io/api/router/CanLoad)

