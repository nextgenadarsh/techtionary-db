Angular's route guards

- are interfaces
- can tell the router whether or not it should allow navigation to a requested route
- make this decision by looking for a true or false return value from a class which implements the given guard interface
- Guards:
  - CanActivate
  - CanActivateChild
  - CanDeactivate
  - CanLoad