Azure Service Bus Quickstart
================

This project illustrates how you can interact with Azure Service Bus using (MicroProfile Reactive Messaging)[https://github.com/freedev/smallrye-reactive-messaging].

## Azure Service Bus

First you need a Azure Service Bus. You can follow the instructions from the [Azure Service Bus Documentation](https://docs.microsoft.com/en-us/azure/service-bus-messaging/service-bus-messaging-overview) .

## Configuration

From the Azure Portal:
- [create a Service Bus - Azure Documentation](https://docs.microsoft.com/en-us/azure/service-bus-messaging/service-bus-create-namespace-portal)
- [create a Service Bus Topic and Subscription - Azure Documentation](https://docs.microsoft.com/en-us/azure/service-bus-messaging/service-bus-quickstart-topics-subscriptions-portal)
- [create a Shared access policy and copy the connection string](https://docs.microsoft.com/en-us/azure/service-bus-messaging/service-bus-quickstart-topics-subscriptions-portal#get-the-connection-string)

Then configure properly the file `src/main/resources/application.properties` fixing the:
- `topic-name`
- `topic-name-subcription`
- and `connectionString` parameter

```
mp.messaging.incoming.source-in.endpoint-uri=azure-servicebus:topic-name?subscriptionName=topic-name-subscription&amqpTransportType=AmqpWebSockets&serviceBusType=topic&connectionString=Endpoint=sb://my-azuresb.servicebus.windows.net/;SharedAccessKeyName=camelTest;SharedAccessKey=XXXXXXXXXXXXXXXX=;EntityPath=topic-name
```

## Start the application

The application can be started using:

```bash
mvn package quarkus:dev
```  

Then, looking at the output you can see messages successfully read from a Azure Service Bus topic.

## Anatomy

The application is composed by 1 components:


* `MyReactiveMessagingApplication` - a bean receiving topic message.

The interaction with Azure Service Bus is managed by MicroProfile Reactive Messaging.

The configuration is located in the microprofile config properties the file `src/main/resources/application.properties`.
