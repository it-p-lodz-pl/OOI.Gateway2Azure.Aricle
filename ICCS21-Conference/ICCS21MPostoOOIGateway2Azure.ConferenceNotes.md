# Conference notes

## Executive summary

The document contains notes to prepare a conference presentation.

## Presentation

### Slide 1

#### Title

- Object-Oriented Internet Cloud Interoperability
- Mariusz Postół (mailto:mariusz.postol@p.lodz.pl)
- Piotr Szymczak
- Institute of Information Technology, Lodz University of Technology, Łódź, Poland

#### Notes 1

My name is Mariusz Postół and I am representing the Institute of Information Technology Lodz University of Technology. It is my pleasure to present my and Piotr Szymczak research work related to Object-Oriented Internet and Cloud services integration focusing on the generic architecture that is proposed to implement and deploy this interoperability scenario.

### Agenda

#### Slide 2

- Topic 1
- Topic 2

#### Notes 2

To keep your attention let me present the agenda for my presentation. At the very beginning, let's describe the scope of my research. I am going to talk about highly distributed industrial processes. It is very broad application domain that includes but it is not limited to Industrial Internet of Things and smart factory concepts. There is no doubts that nowadays systems like that must be designed and deployed considering multivanom environment. It makes standardization especially important.

____
 smart factory Talking about M2M communication I will try to point out the most important in my opinion features of this application domain.

Because the Industry 4.0, IoT, and in general cyber-physical developed based on the M2M may bother with the problems related to:

- traffic asymmetry
- data holder mobility
- Multi-vendor environment

I will investigate the possibility to engage the Reactive Communication instead of Interactive communication.

To make my proposals adaptable by end-users I will propose details making the presented abstract model a foundation for further development in this respect.
____

### Industrial highly distributed applications - human role

#### Slide 20

- Human-centric - information origin or ultimate information destination is an operator
  - GUI Based Human Interface
  - Robustness (errors tolerance) depends on human interaction
  - Cloud-base IoT front-end
- Machine-centric
  - Machine to Machine Communication (M2M) - information creation, consumption, networking, and processing are achieved entirely without human interaction
  - No human interaction possible to improve solution robustness
  - Cyber-physical systems base on Machine to Machine communication
  - OPC Unified Architecture to promote multi-vendor environment

#### Notes 20

Based on the role humans take while deploying smart factory concept the computer applications may be grouped as Human-centric and Machine-centric.

A typical human-centric approach is a web-service supporting a web user interface (UI) to monitor conditions and manage millions of devices and their data in a typical cloud-based internet of Things approach. In this case, it is characteristic that any uncertainty and necessity to make a decision can be relaxed by human interaction.

An example of the machine-centric scenario is the coordination of robot behavior in a work-cell. In this case, any human interaction must be recognized as impractical or even impossible. This interconnection scenario requires the machine to machine communication (M2M) demanding multi-vendor devices integration. In this case, the solution must be robust by design because no human interaction is applicable at run-time.

To promote composition using multi-vendor parts the standardization is especially important. Industry 4.0 is an initiative that addresses this application domain addressing  the Smart factory concept design and deployment. Thai concept is recognized as forth industrial revolution. Additionally, to adders interconnection and interoperability of the multi-vendor component parts the OPC Unified Architecture is considered to normalize reactive M2M communication.

The main goal of this article is to prove that the Object Oriented Internet cyber physical network can be interconnected with the Internet of Things cloud services:

- based on the OPC UA standard implemented as a powerful standalone library without dependency on the Client/Server session-oriented archetype,
- cloud interoperability can be implemented as an independent part employing out-of-band communication without dependency on the OPC UA implementation,
- the proposed generic architecture allows that the gateway functionality is implemented as a composable part at run-time - no programming required.

### Cyber-physical Systems Telemetry

#### Slide 25

- Integrated machines interconnected over the Internet
- Internet of Things (IoT)
- Data holder mobility:
  - Mobile Device - Network attachment point
  - Mobile Application - Serverless data access – reactive communication
  - Mobile Data - Random location of data publication
- Real-time processing
- semantic and security contexts

#### Notes 25

Going beyond the smart factory realm, a similar concept may be used to make any general-purpose entities interoperable. Finally, we get cyber-physical systems where a variety of entities may be aggregated into distributed information processing solutions. In this case, we are opening the public connectivity domain, which requires a globally scoped infrastructure, i.e. the Internet.

For any generic solution addressing the design of the cyber-physical system, the data holder mobility must be considered as well. Mobile data means that it may come from mobile devices or be generated in unpredictable attachment points. If the data places exposition is arbitrary it means that the data appearance must be recognized and processed as an event. A good example of this scenario is a product - for example drugs - global tracking system - an application domain where the IoT term has been coined. One of the arguments for the IoT is allowing distributed yet interlinked devices, machines, and objects (data holders) to interact with each other without relying on human interaction to set-up and commission the embedded intelligence.

In this kind of applications time must be considered as important contributor to the implemented algorithm.

In case any kind of mobility has to be considered, the next engineering challenge is dynamic discoverability on the network and the possibility of establishing the semantic and security contexts of the parts composing the IoT application.

### Direct Interconnection Interoperability Scenario

#### Slide 30

![Direct Interconnection](../.Media/DirectInterconnetion.png)

#### Notes 30

To promote reusability the research must be conducted atop of a formal description. The proposed solution and all intermediate steps illustrating how to derive the final solution from the selected domain features are described by means of the UML that is a well known and widely used language for this purpose. Finally the workout is abstract enough to be reused in any development environment. As a proof of concept we published two implementations as the open source.

Before meting any further research decision the first important question is relationship between the cloud-based frond-end and cyber physical network, and first natural option is direct interconnection. By design, the direct interconnection approach requires that the cloud has to be compliant with the interoperability standard the cyber-physical system is based atop of.

This approach is not practical, became by design, the cloud-based services require that for interconnection preparation and data interchange a session over the Internet has to be established by the data holding assets. Contrary to this, Machine to machine communication is usually constrained by real-time requirements to use protocols applicable only to local computer networks (e.g. multicast IP, Ethernet, TSN 1, etc.).

Concluding, it si obvious that because the cloud services support only communication over the Internet the direct interconnection cannot be applied in a general case.

### Edge Interconnection Interoperability Scenario

#### Slide 40

![Edge interconnection](../.Media/EdgeInterconnection.png)

#### Notes 40

An edge entity is a remote cloud agent acting as an intermediary for nodes of the cyber-physical system. It is a consistent part of cloud-based frond-end services. Main disadvantage of this solution is possibility to support interconnection with only one cloud.

### Field Level Gateway Interoperability Scenario

#### Slide 50

![Field level gateway](../.Media/FieldLevelGateway.png)

#### Notes 50

Field level gateway is a dedicated custom agent acting as an intermediary for nodes connected to the cyber-physical system. This solution is not constrained by the vendor communication context and as the result may be used to handle communication with a variety of clouds. Still this solution is contained only to fulfil the gateway functionality.

### Embedded Gateway Interoperability Scenario

#### Slide 60

![Embedded Gateway](../.Media/StrategyDomainModel.png)

#### Notes 60

We propose a new architecture derived from the field-level approach but not constrained to gateway functionality only. The embedded-gateway is only a composed part of the Networking services of a cyber-physical node. In this approach it may be assumed that the gateway functionality is only an add-iin to expand typical functionality of the node including but not limited to establishing semantic and security context with the other nodes connected to the cyber-physical network. The responsibility of the Embedded Gateway is to establish communication context with the cloud-based frond-end and conduct the selected data transfer in compliance with this context.

Because - according to this proposal - the Embedded-Gateway is composable to any Cyber-physical node it could be deployed far after designing and deploring of the hosting cyber-physical node. The only requirement that constrains this approach is a common abstract contract usually expressed an an interface that the embedded-gateway must be compliant with to be aggregated to the whole. In other words in our solution the gateway is losely copled with the node contray to the Edge and Field-level approach where the gateway functionality is an ebeded part of the host. It improves flexibility, reusability, and in general maintenance cost.

The proposals are backed by proof-of-concept reference implementations confirming the possibility of integrating selected cloud services with the OPC UA based cyber-physical system by applying the proposed architecture and deployment scenario. It is contrary to interconnecting cloud services with the selected OPC UA Server limiting the PubSub role to data export only.

### Sessionless (Reactive communication) vs Session Oriented (Interactive communication)

#### Slide 70

![Cyber-physical network architecture](../.Media/ProcessingUAData.png)

Reactive interoperability relaxes the interconnection problems

- network traffic asymmetry - limits of the network traffic propagation for the security reasons, for example, enforced by a firewall
- data holder mobility – due to data origin mobility the network node may need to move from one attachment point to another losing its previous endpoint address

#### Notes 70

This discussion presented in pervious research was concluded that only reactive interoperability can be used to overcome network traffic asymmetry and data holder mobility. Therefore the further work is concentrated on this communication scenario. Still, reusability of the existing concepts and solutions must be concerned.

- A reactive interoperability relationship of the communication parties is proposed to deal with the network traffic propagation asymmetry or assets’ mobility.
- Described solution based on the OPC Unified Architecture international standard relaxes issues related to the real-time multivendor environment.
- After dynamically attaching a new island of automation the control application (responsible for the data pulling) must be reconfigured for this interoperability scenario. In other words the interactive communication relationship cannot be directly applied because the control application must be informed on how to pull data from a new source.

### Reactive interoperability implementation

### Slide 80

![Reactive interoperability implementation](../.Media/UADataApplicationArchitecture.png)

### Notes 80

- encoding
- machine to machine communication
- configuration
- DataRepository (process data binding)
  - Consumer
  - Producer
  
### Implementation Domain Model

#### Slide 90

![Implementation Architecture](../.Media/ImplementationDomainModel.png)

#### Notes 90

- Consumer as a injected part of the Reactive Application compliant with the OPC UA PubSub
- Embedded gateway part based on the Consumer functionality is a full functional member of the Cyber-physical Network

### Implementation Architecture

#### Slide 100

![Implementation Architecture](../.Media/ImplementationArchitecture.png)

#### Notes 100

### Cloud Communication Context

#### Slide 110

- `CommunicationContext` based on state machine
  - protocol selection and send Data Transfer Object to Cloud
  - security context
- `PartBindingFactory`: IDTOProvide
  - semantic context
    - data grouping
    - data mapping
    - data serialization (JSON)
- `PartConfigurationFactory`
  - Application configuration

#### Notes 110

### Proof of concept (pilot projects)

evidence, typically derived from an experiment or pilot project, which demonstrates that a design concept, business proposal, etc., is feasible.

the company was awarded the contract on the strength of evaluation, proof of concept, and budget

### Conclusions

- The discussion concludes that the embedded gateway software component best suits all requirements and thus has been implemented as a composable part of the selected reactive OPC UA framework which promotes separation of concerns and reusability.


## Future work

- OPC UA Server Embedded Gateway
- OPC UA Client Emended Gateway
- 