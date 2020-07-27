# OOI/Azure Interoperability <!-- omit in toc -->

## Table of content<!-- omit in toc -->

- [Title proposals](#title-proposals)
- [Article structure](#article-structure)
- [Prototyping](#prototyping)
- [See also](#see-also)

## Title proposals

- Object-Oriented Internet - reactive visualization of asynchronous data using AZURE
- Object-Oriented Internet - Azure interoperability

## Article structure

- **Abstract**
- **Key words**
Azure, Cloud Computing, Object-Oriented Internet, OPC Unified Architecture, Machine to Machine Communication, Internet of Things,
- **Introduction**
  - **Subject**
A basic matter of thought, discussion, investigation, development, etc. Describe the problem and the motivation for undertaking the effort to solve the problem.
  - **Goal**
What we are going to achieve - the result or achievement toward which effort is directed.
  - **Scope**
What we must do to prove the goal have been achieved. Extent or range of development, view, outlook, application, operation, effectiveness, etc.
  - **Related work**
Any information about available reusable deliverables related to this work.
- **Azure Main Technology Fetuses**
  - **Selection of the service**
  - **Metadata**
    - **Device Template (DT)**
    - **Device Capability Model**
    - **Interface**
    - **Digital Twin Definition Language (DTDL)**
  - **Simple, complex and structural data processing**
  - **Connectivity**
  - **How to implement**
All about available libraries and tools
- **OOI Main Technology Fetuses**
  - Machinie To Machine communication based on the semantic data
  - OOI PubSub Implementation Architecture
  - Simple, complex and structural data processing
- **Azure to Sensors (M2S) connectivity deployment**
  - **Architecture**
Domain model presenting relationship between the: Azure, PubSub Gateway, Device, Design and development tools
  - **Connectivity**
Describe reactive nature of the Azure monitoring process data (telemetry) services.
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
- **Gateway implementation**
  - Architecture
  - Protocol selection and mapping
  - Configuration
  - Testing
- **Conclusion**
- **References**
List of available resources related to the topic in concern

## Prototyping

The prototyping is conducted in the repositories:

- [Object-Oriented Internet](https://github.com/mpostol/OPC-UA-OOI#object-oriented-internet) - Object-Oriented Internet - Machines to Machine Meaningful Interoperability
- [CrossHMI](https://github.com/Drutol/CrossHMI#crosshmi) - Thesis: Object-Oriented Internet - reactive visualization of asynchronous data using AZURE

## See also

- Postół M. (2020) Object-Oriented Internet Reactive Interoperability. In: Krzhizhanovskaya V. et al. (eds) Computational Science – ICCS 2020. ICCS 2020. Lecture Notes in Computer Science, vol 12141. Springer, Cham; [DOI: https://doi.org/10.1007/978-3-030-50426-7_31](https://doi.org/10.1007/978-3-030-50426-7_31)
  - Postół M. (2020) [Object-Oriented Internet Reactive Interoperability](https://www.researchgate.net/publication/341882427_Object-Oriented_Internet_Reactive_Interoperability), presentation, DOI: 10.13140/RG.2.2.33984.56323

- Mariusz Postol, [Machine to Machine Semantic-Data Based Communication: Comprehensive Survey](https://www.researchgate.net/publication/341165347_Machine_to_Machine_Semantic-Data_Based_Communication_Comprehensive_Survey) chapter in book [Computer Game Innovations 2018](https://www.researchgate.net/publication/335524620_Computer_Game_Innovations_2018), Publisher: Lodz University of Technology Press; ISBN: 978-83-7283-999-2

- Mariusz Postol, [Object Oriented Internet](https://ieeexplore.ieee.org/abstract/document/7321562), [3rd International Conference on Innovative Network Systems and Applications](https://fedcsis.org/2015/inetsapp), 2015, [IEEE Xplore Digital Library](https://ieeexplore.ieee.org/abstract/document/7321562) [![DOI](https://img.shields.io/badge/DOI-10.15439%2F2015F160-blue)](https://fedcsis.org/proceedings/2015/pliks/160.pdf)

<!--OOI on GitHub-->

- [Object Oriented Internet - C# deliverables supporting a new Machine To Machine (M2M) communication architecture; GitHub Open Source Software][OOI]
  - [GitHub UAOOI.Networking.UDPMessageHandler][OOI.Networking.UDPMessageHandler]
  - [GitHub UAOOI.Networking.ReferenceApplication][OOI.Networking.ReferenceApplication]
  - [GitHub UAOOI Releases Page][OOI.Releases]

[OOI]:https://github.com/mpostol/OPC-UA-OOI
[OOI.Networking.UDPMessageHandler]:https://github.com/mpostol/OPC-UA-OOI/tree/master/Networking/UDPMessageHandler
[OOI.Networking.ReferenceApplication]:https://github.com/mpostol/OPC-UA-OOI/tree/master/Networking/ReferenceApplication
[OOI.Releases]:https://github.com/mpostol/OPC-UA-OOI/releases

- [Object Oriented Internet - online ebook][OOIBook]

[OOIBook]:https://commsvr.gitbook.io/ooi/readme

- [OPC UA Address Space Model Designer (ASMD); GitHub Open Source Software][ASMD]

[ASMD]:https://github.com/mpostol/ASMD
