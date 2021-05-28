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

### Smart factory (Industry 4.0) muli-vendor environment

#### Slide 2

- Human-centric - information origin or ultimate information destination is an operator
  - Human Machine Interface (HMI)
  - Robustness (errors tolerance) depends on human interaction
  - Cloud-base IoT front-end
- Machine-centric
  - Machine to Machine Communication (M2M) - information creation, consumption, networking, and processing are achieved entirely without human interaction
  - No human interaction possible to improve solution robustness
  - Cyber-physical systems base on Machine to Machine communication

#### Notes 2

Based on the role humans take while deploying smart factory concept the embedded applications can be grouped as follows Human-centric and Machine-centric. To promote multi-vendor smart factory components supply chain the standardization is especially important. Industry 4.0 is an initiative that address this application domain. Smart factory concept is recognized as forth industrial revolution.

- communication: interconnection and interoperability
- OPC UA is required 
- proposed solutions ar compliant with this requirements

A typical human-centric approach is a web-service supporting, for example, a web user interface (UI) to monitor conditions and manage millions of devices and their data in a typical cloud-based IoT approach. In this case, it is characteristic that any uncertainty and necessity to make a decision can be relaxed by human interaction.

An example of the machine-centric scenario is the coordination of robot behavior in a work-cell. In this case, any human interaction must be recognized as impractical or even impossible. This interconnection scenario requires the machine to machine communication (M2M) demanding multi-vendor devices integration. In this case, the solution must be robust enough because no human interaction is expected.

### Interoperability Scenario - Direct interconnection

#### Slide 30

![Direct Interconnection](../.Media/DirectInterconnetion.png)

#### Notes 30

To promote reusability the research must be conducted atop of a formal description. The proposed solution and all intermediate steps illustrating how to derive the final solution from the selected domain fetuses are described by means of the UML that is well known and widely used for this purpose language. Finally the workout is abstract enough to be reused in any development environment. As a proof of concept we published two implementations as the open source.

By design, the direct interconnection approach requires that the cloud has to be compliant with the interoperability standard the CPS uses. As a result, it becomes a consistent communication node of the CPS. The decision to follow the direct interconnection scenario must be derived from an analysis of the capabilities of available services in concern. However, for the development strategy of this type of solution, the analysis can be done partially taking into account the following features that can be considered invariable. By design, the cloud-based services must be virtual - they are used to handle many solutions at the same time. Furthermore, M2M communication is usually constrained by real-time requirements. The virtualization of cloud services means that they must be very flexible to handle the attachment of new assets proactively (acting in advance) at run time. As a result, the cloud services must be responsible to register and authenticate devices by exposing endpoints in the public network to allow the device to access a provisioning cloud service. It requires that a session over the Internet has to be established by the data holding asset at a preparation step.

To meet the requirements of real-time distributed control the CPS may use protocols applicable only to local computer networks (e.g. multicast IP, Ethernet, TSN 1, etc.). Because the cloud services support only protocols handling inter connection over the Internet the direct interconnection cannot be applied in a general case.

### Edge interconnection Interoperability Scenario

#### Slide 40

![Edge interconnection](../.Media/EdgeInterconnection.png)

#### Notes 40

a remote cloud agent acting as an intermediary for nodes of the CPS

### Interoperability Scenario - Field level gateway

#### Slide 50

![Field level gateway](../.Media/FieldLevelGateway.png)

#### Notes

Field level gateway is a dedicated custom agent acting as an intermediary for nodes of the CPS

### Interoperability Scenario - Embedded Gateway

#### Slide 60

![Embedded Gateway](../.Media/StrategyDomainModel.png)

#### Notes 60

For this integration, a new architecture is proposed to support the reactive relationship of communicating parties.

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

- Consumer as a injected part of the Reactive Application complinat wit the OPC UA PubSub
- Embedded gateway part based on the Consumer functionality is a full functional member of the Cyber-physical Network

### Implementation Architecture

#### Slide 100

![Implementation Architecture](../.Media/ImplementationArchitecture.png)

#### Notes 100

### Cloud Communication Context

#### Slide 110

- Standard protocols
- Frameworks

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