# Manuscript Sketch

## Abstract

## Introduction

- The role humans take while using these applications
- A typical human-centric and machine-centric examples - intro to M2M
- idea of a smart factory based on M2M - introduction to Industry 4.0, multi-vendor integration
- Internet - a demanding environment
- examples how to overcome: bank account remote control and voice over IP
- HMI, SCADA, DCS concepts
- Interactive communication (book shop example), client/server archetype
- dynamically attaching a new island of automation
- plug and produce scenario, network trac propagation asymmetric
- automation are mobile, Internet of Things domain
- reactive relationship, publisher, subscriber
- cloud computing concept
- abstraction and virtualization
- hybrid solution - implementation scenario's
- direct approach - is impractical or even impossible
- This article addresses further research on the integration
- The main goal of this article is to provide
- The remainder of this paper is structured as follows.

## Sensors to Cloud Field Level Connectivity

### Architecture

- The main challenge
- implementation scenarios ((tightly/loosely coupled)
- common data understanding, direct semantic-context, security-context
- common semantic-context based on standardization, common security-context - parties are using the same cyber-security measures
- direct integration features
- virtualization requirements
- real-time distributed control requirements
- edge device, field level gateway, embedded gateway
- Edge device description
- field level gateway
- The Embedded Gateway archetype relaxes most of the issues described above:
- To comply with the Industry 4.0 communication
- session-oriented: vs sessionless-oriented: - communication patterns
- session-oriented communication cannot be used to gather and process mobile data, pubsub IoT ready technology
- prototyping addresses Microsoft Azure
- Azure aids Internet protocols and open standards
- library requirements
- Library description, selections

### Azure Main Technology Features

- Azure introduction
- IoT Central
- gateway concept, a middleware must be considered as a coupler, IoT Hub
- solution, validation, security rules, IoT Hub Device Provisioning Service
- IoT Central can be also seamlessly integrated with other services as needed.
- Industrial IoT promotes OPC UA, IoT Edge servicesIoT Edge services, Digital Twins
- is that information is abstract
- workaround to address that impossibility - the information must be represented as a binary stream.
- regional newspapers in English, German, Polish
- role of the type definition
- CPS/cloud types compatibility
- types conversion is not considered for further discussion.
- CPS is represented as the device template, Device Template (DT), Device Capability Model (DCM).
- IoT Hub to handle network traffic
- HTTP, AMQP, and MQTT implementations, Microsoft.Azure packages, dependency injection

### OOI Main Technology Features

- UAOOI.Networking
- standardization and flexibility
- a polymorphic approach to implementation, separation of concerns
- DataManagementSetup and interfaces
- DataRepository represents data holding assets
- Consumer, Producer
- Consumer and Producer classes are derived from the DataRepository
- DataRepository may cover practically any concern
- separate development and late binding, configuration expandable
- semantic-context and security-context between them, starting point is the configuration
- Concluding, it supports any configuration management scenario,, configuration modification at any time

## Azure - OOI Implementation

- generic domain model presenting interconnection architecture
- the final deployment architecture
- IConfigurationFactory implementation
- PartBindingFactory implements the IBindingFactory
- IEncodingFactory and IMessageHandlerFactory interfaces, IServiceLocator3.
- CommunicationContext. role
- IDTOProvider role, PartBindingFactory maps selected object graph onto the JSON
- Azure and PubSub use different security mechanisms

## Conclusion

- further research on the integration
- dynamic nature of the CPS must be considered
- leveraging of the public communication infrastructure, cloud computing concept may be recognized as a reasonable answer.
- The main goal of this research is working out a new generic architecture
- network trac propagation asymmetry and mobility requires reactive relationship, real-time multi-
vendor environment => standardization
- the Embedded Gateway archetype best suits all requirements
- We proposed to use an open-source library named UAOOI.Networking
- the final model presented
- proposals are backed by proof of concept reference implementations
- The described results prove that the Embedded Gateway archetype
- cloud interoperability is obtained by implementing a dedicated part employing out-of-band communication, without dependency on the OPC UA functionality
- Concluding, the paper describes
