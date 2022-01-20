Azure Service Bus Quickstart
================

This project illustrates how you can interact with Azure Service Bus using (MicroProfile Reactive Messaging)[https://github.com/freedev/smallrye-reactive-messaging].

## Azure Service Bus

First you need a Azure Service Bus. You can follow the instructions from the [Azure Service Bus Documentation](https://docs.microsoft.com/en-us/azure/service-bus-messaging/service-bus-messaging-overview) .

## Configuration

From the Azure Portal:
- create a Service Bus
- create a Service Bus Topic
- create a Service Bus Subscription
- create a Shared access policy and copy the connection string

## Start the application

The application can be started using:

```bash
mvn package quarkus:dev
```  

Then, looking at the output you can see messages successfully send to and read from a Azure Service Bus topic.

[//]: # (## Anatomy)

[//]: # ()
[//]: # (In addition to the commandline output, the application is composed by 3 components:)

[//]: # ()
[//]: # (* `BeanUsingAnEmitter` - a bean sending a changing hello message to kafka topic every second.)

[//]: # (* `Sender` - a bean sending a fixed message to a kafka topic every 5 seconds.)

[//]: # (* `Receiver`  - on the consuming side, the `Receiver` retreives messages from a kafka topic and writes the message content to `stdout`.)

[//]: # ()
[//]: # (The interaction with Kafka is managed by MicroProfile Reactive Messaging.)

[//]: # (The configuration is located in the microprofile config properties.)
