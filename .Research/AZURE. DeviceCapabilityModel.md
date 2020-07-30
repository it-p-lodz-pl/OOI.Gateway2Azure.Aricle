# AZURE Research on Device Capability Model

## Application templates

Application templates in Azure IoT Central are a tool to help solution builders kickstart their IoT solution development. You can use app templates for everything from getting a feel for what is possible, to fully customizing and your application for resale to your customers.

Application templates consist of:

- Sample operator dashboards
- Sample device templates
- Simulated devices producing real-time data
- Pre-configured rules and jobs
- Rich documentation including tutorials and how-tos

> Note MP: is a set of definitions that could be serialized as a JSON document?

## Device Template

A device template in Azure IoT Central is a blueprint that defines the characteristics and behaviors of a type of device that connects to your application. For example, the device template defines the telemetry that a device sends so that IoT Central can create visualizations that use the correct units and data types.

A device template includes the following sections

- Device Capability Model (DCM)
- Cloud properties
- Customizations
- Views

Metadata management: in an Azure IoT Central application, device templates define the behavior and capability of types of device. For example, a refrigerator device template specifies the telemetry a refrigerator sends to your application.

## Device Capability Models

A DCM defines how a device interacts with your IoT Central application.
A solution developer can import a JSON file that defines the DCM into a device template, or use the web UI in IoT Central to create or edit a DCM. 

The JSON file that defines the DCM uses the [Digital Twin Definition Language (DTDL) V1](https://github.com/Azure/opendigitaltwins-dtdl/tree/master/DTDL). IoT Central expects the
JSON file to contain the DCM with the interfaces defined inline, rather than in separate files.

> NOTE MP:
>
>- Interface is an Object according to the JSON syntax definition.
>- can we use DTDL to describe templates
>

## Interface

A typical IoT device is made up of:

- Custom parts, which are the things that make your device unique.
- Standard parts, which are things that are common to all devices.

These parts are called interfaces in a DCM. Interfaces define the details of each part your device implements. Interfaces are reusable across DCMs.

> NOTE MP:
>
>- Interface is an Object according to the JSON syntax definition.

## DTDL

> **TBD**

## JSON-LD

## Getting started

The easiest way to get dotNetRDF is via NuGet. We provide the following packages:

- dotNetRDF - contains the core libraries. This includes support for reading and writing RDF; and for managing and querying RDF data in-memory.
- dotNetRDF.Data.DataTables - a package which integrates RDF data with System.Data.DataTable
- dotNetRDF.Data.Virtuoso - provides support for using OpenLink Virtuoso as a backend store with dotNetRDF.
- dotNetRDF.Query.FullText - provides a full-text query plugin for dotNetRDF's Leviathan SPARQL query engine. The text indexing is provided by Lucene.
- dotNetRDF.Query.Spin - provides an implementation of SPIN using dotNetRDF's Leviathan SPARQL query engine.
- dotNetRDF.Web - provides a framework for hosting RDF data in an IIS web applicat

### See also

- [JSON-LD 1.1](https://www.w3.org/TR/json-ld11/) - A JSON-based Serialization for Linked Data.
- [dotnetrdf/dotnetrdf](https://github.com/dotnetrdf/dotnetrdf#welcome) - dotNetRDF is a powerful and flexible API for working with RDF and SPARQL in .Net environments