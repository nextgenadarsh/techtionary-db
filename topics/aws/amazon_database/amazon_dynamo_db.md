# Amazon DynamoDB

- [Amazon DynamoDB](#amazon-dynamodb)
  - [Advantages](#advantages)
  - [Disadvantage](#disadvantage)
  - [Amazon DynamoDB Accellerator (DAX)](#amazon-dynamodb-accellerator-dax)

- **NoSQL**
- Key-Value Store (A collection of items or records)
- Schemaless
- Supports secondary index

## Advantages

- Fully managed
- Schemaless
- Highly available
- Fast

## Disadvantage

- Eventual consistency
- Queries are less flexible than SQL
- Workflow limitation
  - Max record size: 400 KB
  - Max index per table: 20 global, 5 secondary
- Provisioned throughput

## Amazon DynamoDB Accellerator (DAX)

- **is an in-memory cache** delivering a significant performance enhancement up to 10 times as fast as the default DynamoDB settings, allowing response times to decrease from milliseconds to microseconds.