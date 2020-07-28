# Qpid

## Server Installation

- [Download Messaging Broker/Server](http://www.apache.org/dyn/closer.lua/qpid/broker-j/8.0.0/binaries/apache-qpid-broker-j-8.0.0-bin.tar.gz)
- Execute `qpidserver` under `qpid-broker/<version>/bin`
- [Qpid Mgmt Dashboard](http://localhost:8080)
- UserId: guest | Password: guest
- Connection `amqp://guest:guest@localhost:5672//`
- [Qpid Broker Docs](http://qpid.apache.org/releases/qpid-broker-j-8.0.0/book/)

## Client Installation

- [Download Qpid](https://qpid.apache.org/download.html)
- [Qpid JMS Client - Maven](https://qpid.apache.org/maven.html)
- [Qpid JMS Docs](https://qpid.apache.org/components/jms/index.html)

## Architecture

Producer    >   Broker  >   VirtualhostNodes >   Virtualhost >   Exchange    >   Queues  >   Consumer

## Concepts

#### Broker

- Backed by storage which record durable entities that exists beneath it.

#### Virtualhost
  - An independent container in which messaging is performed
  - A virtualhost node has exactly one virtualhost

#### Exchange

- Accepts messages from producer and routes to one or more Queues according to criteria called `bindings`

#### Queues

- Named entities that hold/buffer messages for later delivery to consumer apps.

#### Ports

- Accept connections for messaginga and management.
- Broker supports any number of ports.
- When connecting to messaging, user specifies virtual host name to indicate virtual host to be connected to

#### Authentication Proviers

- Assert the identity of user as it connects for messaging or management.
- Each port is associated with exactly one authentication provider.

#### Group Providers

- Provide mechanisms that provide grouping of users.
- Broker supports zero or more group providers.

#### Access Control Provider

- Allows the abilities of users to be restrained.
- Broker can have zero or more accell controll providers.

#### Keystores

- Provide a repositories of certificates and are used when broker accepts SSL connections.

#### Truststores

- Provide a repositories of trust and are used to validate a peer.

#### Loggers

- Responsible for production of log for the Broker.

#### 