# Azure Storage Account

- An Azure resource which appears under Azure resource groups
- A container that groups a set of Azure storage services together
- Azure (Blobs + Files + Queues + Tables)
- Storage accont settings are applied to everything in the account
- Deleting storage accounts deletes all the data stored in it
  
## Storage account settings

### Subscription

- Azure subscription to be billed for services in the storage account

### Location

- Datacenter that will store the services in the account

### Performance

- Data services and hardware disks used for account
  - **Standard**: any data service and uses magnetic disk drives
  - **Premium**: additional data service and uses solid-state drives (SSD) for storage

### Replication

- 