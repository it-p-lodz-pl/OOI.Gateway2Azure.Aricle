# Research on AZURE Services <!-- omit in toc -->

## Table of content <!-- omit in toc -->

- [Definitions](#definitions)
- [Functionality](#functionality)
  - [General Services](#general-services)
  - [Messaging Services](#messaging-services)
- [Architecture](#architecture)
- [Field gateway](#field-gateway)
  - [Microsoft Azure IoT services Reference Architecture](#microsoft-azure-iot-services-reference-architecture)
  - [IoT Hub Documentation](#iot-hub-documentation)
    - [Field gateways](#field-gateways)
    - [Cloud gateway](#cloud-gateway)
  - [Microsoft Azure IoT Protocol Gateway Developer Guide](#microsoft-azure-iot-protocol-gateway-developer-guide)
  - [See also](#see-also)

## Definitions

- **Service**. In the context of this document a service is defined as any software component or module that is interfacing with devices through a _field gateway_ or _cloud gateway_ for data collection and analysis, as well as for command and control interactions. Services are mediators. They act under their own identity toward gateways and other subsystems, store and analyze data, autonomously issue commands to devices based on data insights or schedules, and expose information and control capabilities to authorized end users.
- **Solution**. A solution for a particular IoT scenario is a composition of system building blocks, including all user-contributed rules, extensions, and code. It includes all data storage and analysis capabilities specific to the known scope of the solution.
- **Device environment**. The device environment is the immediate physical space around the device where physical access and/or “local network” peer-to-peer, digital access to the device is feasible.
- **Local network**. A “local network” is assumed to be a network that is distinct and insulated from—but potentially bridged to—the public Internet, and includes any short-range wireless radio technology that permits peer-to-peer communication of devices. This notion of “local network” does not include network virtualization technology creating the illusion of such a local network and it does also not include public operator networks that require any two devices to communicate across public network space if they were to enter a peer-to-peer communication relationship.

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

>TODO collect information about services relationship, namely: dependency, aggregation, composition, generalization, association, etc.

- Azure IoT Central uses Azure IoT Hub as a cloud gateway that enables device connectivity
- 

Compare the terms:

- messages routing
  - IoT Central refers to it as IoT Hub functionality
  - IoT Hub: message routing enables sending telemetry data from your IoT devices to built-in Event Hub-compatible endpoints or custom endpoints such as blob storage, Service Bus Queues, Service Bus Topics, and Event Hubs. To configure custom message routing, you create routing queries to customize the route that matches a certain condition.
  - MP?? it looks like embedded functionality of the IoT Hub
- messages services

## Field gateway

### Microsoft Azure IoT services Reference Architecture

This reference model discusses preferred communication protocol choices, explains potential trade-offs with these choices, and also explicitly allows for custom protocol extensibility and adaptation at the field gateway or in a cloud-based protocol gateway.

Devices can be connected directly or indirectly via a field gateway. Both devices and field gateways may implement edge intelligence and analytics capabilities

Figure 3 outlines the conceptual representation of the different device connectivity options for IoT solutions. The numbers in the figure correspond to four key connectivity patterns, defined as follows:

1. **Direct** device connectivity to the cloud gateway: For IP capable devices that can establish secure connections via the Internet.
2. Connectivity via a **field gateway**: For devices using industry specific protocols (such as CoAP5, OPC), short-range communication technologies (such as Bluetooth, ZigBee), as well as for resource-constrained devices not capable of hosting a TLS/SSL stack, or devices not exposed to the Internet. This option is also useful when aggregation of streams and data is executed on a field gateway before transferring to the cloud.
3. Connectivity via a custom **cloud gateway**: For devices that require protocol translation or some form of custom processing before reaching the cloud gateway communication endpoint.
4. Connectivity via a **field gateway and a custom cloud gateway**: Similar to the previous pattern, field gateway scenarios might require some protocol adaption or customizations on the cloud side and therefore can choose to connect to a custom gateway running in the cloud. Some scenarios require integration of field and cloud gateways using isolated network tunnels, either using VPN technology or using an application-level relay service.

A **field gateway** is a specialized device-appliance or general-purpose software that acts as a communication enabler and, potentially, as a local device control system and device data processing hub. A **field gateway** can perform local processing and control functions toward the devices; on the other side it can filter or aggregate the device telemetry and thus reduce the amount of data being transferred to the cloud back end.

A **field gateway**’s scope includes the field gateway itself and all devices that are attached to it. As the name implies, field gateways act outside dedicated data processing facilities and are usually collocated with the devices.

A **field gateway** is different from a mere traffic router in that it has an active role in managing access and information flow. It is an application-addressed entity and network connection or session terminal. For example, gateways in this context may assist in device provisioning, data filtering, batching and aggregation, buffering of data, protocol translation, and event rules processing. NAT devices or firewalls, in contrast, do not qualify as field gateways since they are not explicit connection or session terminals, but rather route (or deny) connections or sessions made through them.

### IoT Hub Documentation

Use Azure IoT Edge to create a field gateway to perform protocol translation on the edge.

Azure IoT Hub natively supports communication over the MQTT, AMQP, and HTTPS protocols. In some cases, devices or field gateways might not be able to use one of these standard protocols and require protocol adaptation. In such cases, you can use a custom gateway. A custom gateway enables protocol adaptation for IoT Hub endpoints by bridging the traffic to and from IoT Hub. You can use the [Azure IoT protocol gateway](https://github.com/Azure/azure-iot-protocol-gateway/blob/master/README.md) as a custom gateway to enable protocol adaptation for IoT Hub.

Azure IoT protocol gateway enables protocol translation for Azure IoT Hub

#### Field gateways

In an IoT solution, a *field gateway* sits between your devices and your IoT Hub endpoints. It is typically located close to your devices. Your devices communicate directly with the field gateway by using a protocol supported by the devices. The field gateway connects to an IoT Hub endpoint using a protocol that is supported by IoT Hub. A field gateway might be a dedicated hardware device or a low-power computer running custom gateway software.

You can use [Azure IoT Edge](/azure/iot-edge/) to implement a field gateway. IoT Edge offers functionality such as multiplexing communications from multiple devices onto the same IoT Hub connection.

A field gateway enables connectivity for devices that cannot connect directly to [IoT Hub](#iot-hub) and is typically deployed locally with your devices.

- **Field gateways**. MQTT and HTTPS support only a single device identity (device ID plus credentials) per TLS connection. For this reason, these protocols are not supported for [field gateway scenarios](iot-hub-devguide-endpoints.md#field-gateways) that require multiplexing messages using multiple device identities across a single or a pool of upstream connections to IoT Hub. Such gateways can use a protocol that supports multiple device identities per connection, like AMQP, for their upstream traffic.

- [Reference - IoT Hub endpoints](iot-hub-devguide-endpoints.md) describes the various endpoints that each IoT hub exposes for runtime and management operations. The article also describes how you can create additional endpoints in your IoT hub, and how to use a field gateway to enable connectivity to your IoT Hub endpoints in non-standard scenarios.

#### Cloud gateway

A cloud gateway enables connectivity for devices that cannot connect directly to [IoT Hub](#iot-hub). A cloud gateway is hosted in the cloud in contrast to a [field gateway](#field-gateway) that runs local to your devices. A typical use case for a cloud gateway is to implement protocol translation for your devices.

### Microsoft Azure IoT Protocol Gateway Developer Guide

The terms ‘device’ or ‘devices’ are used in this guide as a generic way to indicate IoT devices or field gateways, but could also include other types of clients establishing communication with IoT Hub. ‘Protocol gateway’ or ‘gateway’ are used to refer to the Azure IoT protocol gateway.

### See also

- [Microsoft Azure IoT Protocol Gateway Developer Guide](https://github.com/Azure/azure-iot-protocol-gateway/blob/master/docs/DeveloperGuide.md)
