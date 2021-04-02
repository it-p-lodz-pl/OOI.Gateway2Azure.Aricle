# Object-Oriented Internet Cloud Interoperability <!-- omit in toc -->

## Table of content<!-- omit in toc -->

- [Executive sumary](#executive-sumary)
- [Article Abstract](#article-abstract)
  - [Keywords](#keywords)
- [Article Table  of Content](#article-table--of-content)
- [Prototyping](#prototyping)
- [See also](#see-also)

## Executive sumary

Our article titled `Object-Oriented Internet Cloud Interoperability` has been accepted and is to be published in the Lecture Notes in Computer Science series, on behalf of Springer. The public preview of the article is available for early review. To get the full story and get your copy check out the preprint from Research Gateway: [Object-Oriented Internet Cloud Interoperability](https://www.researchgate.net/publication/346563454_Object-Oriented_Internet_Cloud_Interoperability) or contact me.

The presented proposals are backed by proof of concept reference implementations. To start prototyping check out the open-source library: [Azure Gateway DataRepository Implementation](https://github.com/mpostol/OPC-UA-OOI/tree/master/Networking/DataRepository/AzureGateway#azure-gateway-datarepository-implementation).

It is conducted as part of the open-access [**Object-Oriented Internet** (OOI)](https://github.com/mpostol/OPC-UA-OOI#object-oriented-internet) project targets multi-vendor plug-and-produce machines interoperability scenarios targeting all aspects of the machine-centric global village concept aimed at providing reusable deliverables, training, best practice rules, prototyping, compliance testing and dissemination of valuable results.

The project collecting several repositories is maintained under the umbrella of the [Object-Oriented Internet (OOI) Partnership Program](https://github.com/sponsors/mpostol).

Any questions, comments, and proposals are welcome.

My blog on [About enablers of future solutions](mpostol.wordpress.com).

## Article Abstract

Optimization of industrial processes requires further research on the integration of machine-centric systems with human-centric cloud-based services in the context of new emerging disciplines, namely the fourth industrial revolution coined as Industry 4.0 and Industrial Internet of Things. The following research aims at working out a new generic architecture and deployment scenario applicable to that integration. A~reactive interoperability relationship of the communication parties is proposed to deal with the network traffic propagation asymmetry or assets’ mobility. Described solution based on the OPC Unified Architecture international standard relaxes issues related to the real-time multi-vendor environment. The discussion  concludes that the embedded gateway software component best suits all requirements and thus has been implemented as a composable part of the selected reactive OPC UA framework which promotes separation of concerns and reusability.

The proposals are backed by proof-of-concept reference implementations confirming the possibility of integrating selected cloud services with the OPC UA based cyber-physical system by applying the proposed architecture and deployment scenario. It is contrary to interconnecting cloud services with the selected OPC UA Server limiting the PubSub role to data export only.

### Keywords

`Industry 4.0`, `Internet of Things`, `Object-Oriented Internet` `Cloud Computing` `Industrial communication` `Reactive networking` `Machine to Machine Communication`, `OPC Unified Architecture`, `Azure`

## Article Table  of Content

1. Introduction
1. Sensors to Cloud Interconnection - Architecture
1. Cloud - OOI Interoperability Implementation
1. Conclusion

1. References

## Prototyping

The prototyping is conducted in the repositories:

- open-source library: [Azure Gateway DataRepository Implementation](https://github.com/mpostol/OPC-UA-OOI/tree/master/Networking/DataRepository/AzureGateway#azure-gateway-datarepository-implementation)
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
