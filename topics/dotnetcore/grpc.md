- [gRPC](#grpc)
  - [Concetps](#concetps)
    - [The Protocol](#the-protocol)
    - [RPC Types for client server communication](#rpc-types-for-client-server-communication)
      - [Unary](#unary)
      - [Streaming](#streaming)
    - [Protobuf](#protobuf)
      - [Protobuf file](#protobuf-file)
    - [Protobuf and gRPC](#protobuf-and-grpc)
    - [Stubbing and backward compatibility](#stubbing-and-backward-compatibility)
  - [Quick Start](#quick-start)
    - [Running gRPC application](#running-grpc-application)
    - [Updating a gRPC service](#updating-a-grpc-service)
    - [Generate gRPC code](#generate-grpc-code)
    - [Update and run the application](#update-and-run-the-application)

# gRPC

- A RPC platform developed by Google
- It has two parts: gRPC protocol + data serialization
- By default gRPC utilizes `Protobuf` for serialization, but is pluggable with any form of serialization you wish to use, with some caveats.

## Concetps

### The Protocol

- Based on `http2` and exploits many of its benefits.
- Supports http2 features like `compressing headers`, `persistent single TCP connections`, cancellation and timeout contracts between client and server.
- Load balancing is performed by client, which chooses the server for given request from list provided by Load Balancing server.

### RPC Types for client server communication

#### Unary

- Synchronous request made to the gRPC server with a single request that blocks until a response is received.

#### Streaming

- It can be accomplished in three different configurations:
  - Client pushing messages to a stream
  - Server pushing messages to a stream
  - Bidirectional - client and server pushing data in two streams in the same method.
- Client always initiates the RPC method.

### Protobuf

- Default serialization format for data sent between clients and servers.
- The encoding allows for small messages and quick decoding and encoding.
- Forgoes zero-copy of data like some other data interchange methods like `Cap'n Proto` and `Flatbuffers` instead opting for encoding and decoding bytes.

#### Protobuf file

```js
message Foo {
    string name = 1;
    int32 age = 2;
}
```

### Protobuf and gRPC

- They are completely independent of each other.
- All the automatic client server side code generation is performed by `protoc` the protobuf stub generation tool.

### Stubbing and backward compatibility

- Protobuf attempts to put safeguards into its encoding scheme.

## [Quick Start](https://grpc.io/docs/languages/csharp/quickstart/)

### Running gRPC application

### Updating a gRPC service

- Update a gRPC service by editing .proto file

### Generate gRPC code

### Update and run the application




> Reference
- [Introduction to gRPC](https://blog.container-solutions.com/introduction-to-grpc)
- [gRPC HelloWorld Examples](https://github.com/nextgenadarsh/grpc/tree/master/examples/csharp/Helloworld)
