# Amazon Relational Database Service

- [Amazon Relational Database Service](#amazon-relational-database-service)
  - [RDS Backup Capabilities](#rds-backup-capabilities)
  - [Existing RDS Backup](#existing-rds-backup)
  - [Copy and Share RDS Snapshots](#copy-and-share-rds-snapshots)
  - [Database Engines](#database-engines)
    - [MySQL](#mysql)
    - [MariaDB (Fork of MySQL)](#mariadb-fork-of-mysql)
    - [PostgresSQL](#postgressql)
    - [Amazon Aurora (Fork of MySQL)](#amazon-aurora-fork-of-mysql)
    - [Oracle](#oracle)
    - [SQL Server](#sql-server)
  - [Amazon RDS Performance Insights](#amazon-rds-performance-insights)

## RDS Backup Capabilities

- When you delete your database instance, you will be given option to perform a final DB snapshot
- When you delete your db instance, your automatically backups will only last as long as retention period
- User initiated manual backups are known as Snapshots
- Manual snapshots do not offer the ability to perform point-in-time-recovery
- A full backup is taken and any subsequent backups that are taken are an increamental backup
- Manual DB Snapshots are not restricted by any retention periods

## Existing RDS Backup

- RDS backs up the transaction logs to Amazon S3 every 5 mins

## Copy and Share RDS Snapshots

- It is not possible to share an encrypted snapshot, if trying to share publicly
- You are unable to share a snapshot that has been encrypted with the default KMS key of source account
- You can't share snapshots that are encrypted with Transaction Data Encryption (TDE)
- If you have used a customer created CMK to encrypt your source db, then you must ensure that target account has permissions to use the CMK

## Database Engines

### MySQL

- Uses EBS

### MariaDB (Fork of MySQL)

- Uses EBS

### PostgresSQL

- Uses EBS

###  Amazon Aurora (Fork of MySQL)

- Shared Cluster Storage

### Oracle

- Uses EBS

###  SQL Server

- Uses EBS

## Amazon RDS Performance Insights

- It impacts the database performance limited to being no more than 1% of a cpu core
- Load is measured using Average Active Sessions (AAS). AAS is calculated by sampling memory to determine the state of each active database connection. The sampled data includes the SQL query, the state of the query, the host that originated the query and user running it.
- Active sessions are sampled once per second to present a seamless picture of a database's load
- Performance insight metric data is stored, processeded, and managed using AWS resources outside RDS instance. So analaysis has no impact on database performance.
- The dashboard has four categories that contribute to load, SQL, Hosts, Users, and Waits
- Access to performance insight can be granted or restricted using IAM policy.
- Free tier includes 7 days of performance data and 1 million API calls.
- Long term retention is supported upto 2 years.