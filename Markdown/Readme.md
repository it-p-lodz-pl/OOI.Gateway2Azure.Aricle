# Article content <!-- omit in toc -->

## Table of content <!-- omit in toc -->

- [Article preliminary structure](#article-preliminary-structure)
  - [Abstract](#abstract)
  - [Key words](#key-words)
  - [Introduction](#introduction)
  - [Azure Main Technology Features](#azure-main-technology-features)
  - [OOI Main Technology Features](#ooi-main-technology-features)
  - [Azure to Sensors (A2S) connectivity deployment (field level connectivity)](#azure-to-sensors-a2s-connectivity-deployment-field-level-connectivity)
  - [Gateway implementation](#gateway-implementation)
  - [Conclusion](#conclusion)
  - [References](#references)

## Article preliminary structure

### Abstract

### Key words

Azure, Cloud Computing, Object-Oriented Internet, OPC Unified Architecture, Machine to Machine Communication, Internet of Things,

### Introduction

- **Subject** - A basic matter of thought, discussion, investigation, development, etc. Describe the problem and the motivation for undertaking the effort to solve the problem.
- **Goal** What we are going to achieve - the result or achievement toward which effort is directed.
- **Scope** - What we must do to prove the goal have been achieved. Extent or range of development, view, outlook, application, operation, effectiveness, etc.
- **Related work** - Any information about available reusable deliverables related to this work.

### Azure Main Technology Features

- **Selection of the service**
- **Metadata** - must be discussed in context of the design/run time stages.
  - **Device Template (DT)**
  - **Device Capability Model**
  - **Interface**
  - **Digital Twin Definition Language (DTDL)**
- **Simple, complex and structural data processing**
- **Connectivity**
- **How to implement** All about available libraries and tools

### OOI Main Technology Features

- Machinie To Machine communication based on the semantic data
- OOI PubSub Implementation Architecture
- Simple, complex and structural data processing

### Azure to Sensors (A2S) connectivity deployment (field level connectivity)

> The title must be revised

- **Architecture** - Domain model presenting relationship between the: Azure, PubSub Gateway, Device, Design and development tools
- **Connectivity** - Describe reactive nature of the Azure monitoring process data (telemetry) services.
- **Deployment phases**
  - Design
  - Gateway and devices registration
  - Authentication
  - Device/Service association
  - Device/Application association
  - Establishing session
    - Device/Device Template (Device Capability Model) association - establishing a semantic-context
    - Security management - establishing security-context
  - Interconnection - exchange of data
  - Maintenance

We have selected [IoT Central](https://docs.microsoft.com/azure/iot-central/core/) because:

- provides process data visualization user interface
- allows to describe devices using metadata containing telemetry data types

### Gateway implementation

- Architecture
- Protocol selection and mapping
- Configuration
- Testing

### Conclusion

### References

List of available resources related to the topic in concern
