# Azure Messaging and Eventing Technologies

## Messaging

- Message contains raw data, produced by one component, that will be consumed by other component
- A message contains data itself, not the reference to data.
- Sender component expects the data to be processed in certain way by receiver component

### Azure Queue Storage

- Uses Azure storage to `store large number of messages` that can be securely accessed from anywhere `using REST` based interface.
- Provides `audit trail` for each message that pass through queue.

### Azure Service Bus Queues

- A `message broker` intended for `enterprise` apps.
- Often utilize `multiple communication protocols`, different data contracts, `higher security` etc
- It can include both cloud and on-premises services.
- Built on top of dedicate messaging infrastructure.

### Azure Service Bus Topics

- Topic is similar to Queue but can have `multiple subscribers`
- Topics `uses Queues` internally. When you post to a topic, message is copied to the queue for each subscription.

### Benefits of Queues

#### Increased reliability

- Queues are used as temporary storage for messages pending delivery to a destination component.

#### Message delivery guarantees

Queues guarantee delivery of each message to destination component. It has different approaches:

- **At-Least-Once Delivery**
- **At-Most-Once Delivery** - Uses `automatic duplicate detection` mechanism to ensure that each message is not guaranteed to be delivered.
- **First-In-First-Out (FIFO)**

#### Transactional support

- Allows to group multiple messages into a transaction

## Events

- Lighter weight than message, used for broadcast communication using Publisher/Subscriber pattern
- Might hold reference to data but not the data itself
- 0 or more subscribers/receivers

### Azure Event Grid

- Fully managed event routing service running on top of Azure Service Fabric.
- Distributes events from different sources to different handlers like Azure Function and Web Hooks.

#### Components of Azure Event Grid

- Events
- Event source
- Topics
- Event subscriptions
- Event handlers

#### Features / When to use

- Simplicity
- Advanced filtering
- Fan-out
- Reliability
- Pay-per-event

### Azure Event Hubs

- An `intermediary` between publisher and subscriber.
- Optimized for extremely hight throughput, large number of publishers, security and resiliency.
- Event Grid ++

#### Partitions (Buffers)

- Event hub divides the received communications into partitions.
- Subscriber can always use the buffer to catch up the old communications.
- Events exist for 24 hours before they get expired.
- Every event hub has at least two partitions and each has seprate subscribers.

#### Capture

- Event Hubs can send all communications immediately to Azure Data Lake or Blob Storage for inexpensive, permanent persistence.

#### Authentication

- All publishers are authenticated and issued a token.