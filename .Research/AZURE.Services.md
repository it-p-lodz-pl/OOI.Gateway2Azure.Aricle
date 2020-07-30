# Research on AZURE Services <!-- omit in toc -->

## Table of content <!-- omit in toc -->

- [Functionality](#functionality)
  - [General Services](#general-services)
  - [Messaging Services](#messaging-services)
- [Architecture](#architecture)
- [Decision](#decision)

## Functionality

### General Services

1. [IoT Central](https://docs.microsoft.com/en-gb/azure/iot-central/core/)
   - allows to describe devices using metadata
   - provides process data visualization user interface
2. [IoT Hub](https://docs.microsoft.com/en-us/azure/iot-hub/)
   - part of IoT Central *(MP?? or IoT Central is dependent on)*
   - provides robust messaging solution, with responses/acknowledgements and commands
   - operates without types allowing any devices to exchange any kind of data
   - provides device identity
   - supports AMQP, MQTT, HTTPS
   - max message can be 256kb max
3. [Device Provisioning Service (DPS)](https://docs.microsoft.com/en-us/azure/iot-dps/)
   - The IoT Hub Device Provisioning Service (DPS) is a helper service for IoT Hub that enables zero-touch, just-in-time provisioning to the right IoT hub without requiring human intervention.
   - _MP??_ looks like component of the IoT Hub
4. [Industrial IoT Platform](https://github.com/Azure/Industrial-IoT#azure-industrial-iot-platform)
   - [Industrial IoT](https://github.com/Azure/Industrial-IoT)
   - complex solution targeting various IIoT protocols
   - runs based on [IoT Edge](https://azure.microsoft.com/en-in/services/iot-edge/)
   - appears to be focused on client-server aspect of OPCUA
   - MP??
     - IoT Central doesn't refers to this service
5. [IoT Edge](https://azure.microsoft.com/en-in/services/iot-edge/)
   - service that allows extracting initial data processing to local premises
   - helps saving the bandwidth thanks to sending the results of local processing
   - provides separate Virtual Machine images for Azure supported runtime
   - end users appear to be developing [modules](https://docs.microsoft.com/en-us/azure/iot-edge/module-development) which target aforementioned runtime to communicate with actual Azure and process the data
6. [Blob Storage](https://azure.microsoft.com/en-us/services/storage/blobs/) or <https://docs.microsoft.com/en-us/azure/storage/blobs/storage-blobs-overview>
   - like AWS S3
   - meant to store blobs of static data
   - various tiers of storage (Hot&Cold)
   - allows to define data lifetime
   - enables public access to the data
   - via SAS tokens it allows to delegate data upload directly by the client eliminating the need to forward it through some other infrastructure
   - required by IoT Hub if messages are to contain data over 256kb
   - MP??
     - Azure IoT Central refers to this service as the export destination only - **it is out of the scope**
     - IoT Hub refers to it as a messages routing destination: Message routing enables sending telemetry data from your IoT devices to built-in Event Hub-compatible endpoints or custom endpoints such as blob storage, Service Bus Queues, Service us Topics, and Event Hubs - it looks like out of scope.
7. [Digital Twins](https://azure.microsoft.com/en-us/services/digital-twins/) or <https://docs.microsoft.com/en-us/azure/storage/blobs/storage-blobs-overview.>
   - currently developed tech
   - aims at managing the graph of digital twins, which are to represent some real world process or entity
   - works based on DTDL v2
   - allows data ingress and egress 
   - graph traversing, management, versioning
   - can forward data to the messaging services described below

### Messaging Services

1. [Event Grid](https://docs.microsoft.com/en-us/azure/event-grid/)
   - notification events, but not bulk sensor data
   - promotes reactive programming
   - main purpose is to react to status changes
   - MP ??
     - Azure IoT Central don't have any reference to this service
     - Azure IoT Hub provides the capability to stream data from your connected devices and integrate that data into your business applications. IoT Hub offers two methods for integrating IoT events into other Azure services or business: IoT Hub message routing and IoT Hub integration with Event Grid.
1. [Event Hubs](https://docs.microsoft.com/en-us/azure/event-hubs/)
   - notification events, big data streams
   - focused on telemetry purposes
   - MP??
     - Azure IoT Central refers to this service as the export destination only - **it is out of the scope**
     - IoT Hub refers to it as a messages routing functionality: `Message routing enables sending telemetry data from your IoT devices to built-in Event Hub-compatible endpoints or custom endpoints such as blob storage, Service Bus Queues, Service Bus Topics, and Event Hubs.` - it looks like out of scope.
1. [Service Bus](https://docs.microsoft.com/en-us/azure/service-bus-messaging/)
   - robust messaging for enterprise applications
   - supports translations, ordering, duplicates removal, provides delivery guarantees
   - MP??
     - IoT Central refers to this service as the export destination only - **it is out of the scope**
     - IoT Hub refers to it as a messages routing destination (endpoint): `Message routing enables sending telemetry data from your IoT devices to built-in Event Hub-compatible endpoints or custom endpoints such as blob storage, Service Bus Queues, Service Bus Topics, and Event Hubs.` - it looks like out of scope.

> Notes:
>
>- Comparison can be found [here](https://docs.microsoft.com/en-us/azure/event-grid/compare-messaging-services)
>- event - fire and forget, sender does not particularly care about what will happen with this piece of data
>- message - contract exists between sender are recipient, sender expects recipient to process the message in certain way
>- MP?? In the documentation there is the following statement: `The publisher of the message has an expectation about how the consumer handles the message.`. Provided that the data must be reusable the data source must not decide about what the destination (may be many) will do - there must not be any expectation on the data source side. My point is that message must not be compared to event. Event is a kind of data, but message is just a stream of bits.

## Architecture

>TODO collect information about services relationship, namely: dependency, aggregation, collection, generalization, association, etc.

- Azure IoT Central uses Azure IoT Hub as a cloud gateway that enables device connectivity
- 

Compare the terms:

- messages routing
  - IoT Central refers to it as IoT Hub functionality
  - IoT Hub: message routing enables sending telemetry data from your IoT devices to built-in Event Hub-compatible endpoints or custom endpoints such as blob storage, Service Bus Queues, Service Bus Topics, and Event Hubs. To configure custom message routing, you create routing queries to customize the route that matches a certain condition.
  - MP?? it looks like embedded functionality of the IoT Hub
- messages services

## Decision

We have selected [IoT Central](https://docs.microsoft.com/en-gb/azure/iot-central/core/) because;

- provides process data visualization user interface
- allows to describe devices using metadata containing telemetry data types
