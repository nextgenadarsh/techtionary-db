# Azure Relational Data

- [Azure Relational Data](#azure-relational-data)
  - [Azure SQL Database](#azure-sql-database)
    - [Performances](#performances)
    - [Terms Used](#terms-used)
      - [SQL ELastic Pools](#sql-elastic-pools)
      - [Collation](#collation)
  - [Azure PostgreSQL Database](#azure-postgresql-database)
    - [Secutiy options](#secutiy-options)

## Azure SQL Database

- Creating first Azure SQL Database creates an `Azure SQL Logical server`

### Performances

- Database Transaction Unit - (DTU)
  - Combined measure of compute, storage and IO resources
- vCores
  - Virtual cores allows to control compute, storage and IO resource independently


### Terms Used

#### SQL ELastic Pools

- Relates to eDTUs.
- Enables to busy set of compute and storage resources that are shared among all databases in pool
- Resource allocation service to manage and scale multiple Azure SQL databases that have varying requirements
- 

#### Collation

- Rules that sort and compare data

## Azure PostgreSQL Database

- Creating this resource allows you to configure your server instance
- If server instance is deleted, all your databases will be deleted
- All resources belonging to the parent are hosted in same region

### Secutiy options

- User accounts to restrict database access
- Virtual networks to restrict network access
- Firewall rules to restrict server access


##

ADMIN_LOGIN="ServerAdmin"
RESOURCE_GROUP=learn-67f6da00-a59e-4389-9c71-5245b4a82286
SERVERNAME=FitnessSQLServer-$RANDOM
LOCATION=westus2
PASSWORD=P@ssw0rd