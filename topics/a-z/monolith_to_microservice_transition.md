# Monolith to Microservices Transition

## Steps

### Module Interdependency

- Identify parts of the application that are `least dependent on by other` modules and have the `least dependency on them` as well
- These parts are `seams` which are most easily visible parts to change
- It allows us to isolate this part of the code from rest of the system

### Technology:  two-pronged approach

- Identify the features of application's base frameworks being utilized
- Identify pieces of code that use technology different from what is being used currently

### Team Structure

- Create the teams based on their technical skill set, geographical location, or security requirements.

### Database

- Identify the database structures that are being used to interact with database
- Check if you can isolate the database structures in code to be broken down and align this with newly defined vertical boundaries
- Identify what would it take to breakdown underlying database structure as well
- Break the foreign key relationship

### Master data

- Wrap up the master data in a separate service altogether

### Transactions

- Option I: try again and perform remaining part of transaction later
- Option II: cancel entire transaction spread across services
- Transactions need to be planned very well

### Compensating transactions

- allows us to roll back or undo all the tasks we have performed in a series of steps