# Research on AZURE Services <!-- omit in toc -->

## Table of content <!-- omit in toc -->

- [Functionality](#functionality)
- [Relationship](#relationship)
- [Decision](#decision)
- [Drutol comments](#drutol-comments)
- [Messaging services](#messaging-services)
  - [Event Grid](#event-grid)
  - [Event Hubs](#event-hubs)
  - [Service Bus](#service-bus)
- [MP comments](#mp-comments)

## Functionality

- [IoT Central](https://docs.microsoft.com/en-gb/azure/iot-central/core/)
- [Azure IoT Hub](https://docs.microsoft.com/en-us/azure/iot-hub/)
- [Azure Industrial IoT Platform](https://github.com/Azure/Industrial-IoT#azure-industrial-iot-platform)
- Azure Event Hubs
- Azure ServiceBus
- Azure Blob storage

## Relationship

## Decision

- What we have selected
- Why

## Drutol comments

    ## General services

    ### [Iot Central](https://azure.microsoft.com/en-us/services/iot-central/)

    - provides device types
    - provides visualization mechanisms

    ### [Azure IoT Hub](https://docs.microsoft.com/en-us/azure/iot-hub/)

    - part of IoT Central
    - provides robust messaging solution, with responses/acknowledgements and commands
    - operates without types allowing any devices to exchange any kind of data
    - provides device identity
    - supports AMQP, MQTT, HTTPS
    - max message can be 256kb max

    ### [Industrial IoT](https://github.com/Azure/Industrial-IoT)

    - complex solution targeting various IIoT protocols 
    - runs based on [Azure IoT Edge](https://azure.microsoft.com/en-in/services/iot-edge/)
    - appears to be focused on client-server aspect of OPCUA

    ### [Azure IoT Edge](https://azure.microsoft.com/en-in/services/iot-edge/)

    - service that allows extracting initial data processing to local premises
    - helps saving the bandwidth thanks to sending the results of local processing
    - provides separate Virtual Machine images for Azure supported runtime
    - end users appear to be developing [modules](https://docs.microsoft.com/en-us/azure/iot-edge/module-development) which target aforementioned runtime to communicate with actual Azure and process the data

    ### [Blob Storage](https://azure.microsoft.com/en-us/services/storage/blobs/)

    - like AWS S3
    - meant to store blobs of static data
    - various tiers of storage (Hot&Cold)
    - allows to define data lifetime
    - enables public access to the data
    - via SAS tokens it allows to delegate data upload directly by the client eliminating the need to forward it through some other infrastructure
    - required by IoT Hub if messages are to contain data over 256kb

    ### [Digital Twins](https://azure.microsoft.com/en-us/services/digital-twins/)

    - currently developed tech
    - aims to manage the graph of digital twins which is to represent some real world process or entity
    - works based on DTDL v2
    - allows data ingress and egress 
    - graph traversing, mangement, versioning
    - can forward data to the messaging services described below

## Messaging services

Comparison can be found [here](https://docs.microsoft.com/en-us/azure/event-grid/compare-messaging-services).

event - fire and forget, sender does not particularly care about what will happen with this piece of data
message - contract exists between sender are recipient, sender expects recipient to process the message in certain way

### [Event Grid](https://docs.microsoft.com/en-us/azure/event-grid/)

- notification events, but not bulk sensor data
- promotes reactive programming
- main purpose is to react to status changes

### [Event Hubs](https://docs.microsoft.com/en-us/azure/event-hubs/)

- notification events, big data streams
- focused on telemetry purposes

### [Service Bus](https://docs.microsoft.com/en-us/azure/service-bus-messaging/)

- robust messaging for enterprise applications
- supports translations, ordering, duplicates removal, provides delivery guarantees

## MP comments

- `Azure IoT Hub` - the wrong link - it opens general documentation,
- [What is Azure Blob storage?](https://docs.microsoft.com/en-us/azure/storage/blobs/storage-blobs-overview) - I propose this
- [Azure Digital Twins Preview Documentation](https://docs.microsoft.com/en-us/azure/storage/blobs/storage-blobs-overview) - consider this
