# Conference notes

## Executive summary

The document contains notes to prepare a conference presentation.

## Presentation

### Domain description (assumptions)

- A reactive interoperability relationship of the communication parties is proposed to deal with the network traffic propagation asymmetry or assets’ mobility.
- Described solution based on the OPC Unified Architecture international standard relaxes issues related to the real-time multivendor environment.
- A typical human-centric approach is a web-service supporting, for example, a web user interface (UI) to monitor conditions and manage millions of devices and their data in a typical cloud-based IoT approach
- After dynamically attaching a new island of automation the control application (responsible for the data pulling) must be reconfigured for this interoperability scenario. In other words the interactive communication relationship cannot be directly applied because the control application must be informed on how to pull data from a new source.

## Assumptions

- Integration models
  - edge
  - field gateway
  - embedded gateway

### Thesis

For this integration, a new architecture is proposed to support the reactive relationship of communicating parties.

The proposals are backed by proof-of-concept reference implementations confirming the possibility of integrating selected cloud services with the OPC UA based cyber-physical system by applying the proposed architecture and deployment scenario. It is contrary to interconnecting cloud services with the selected OPC UA Server limiting the PubSub role to data export only.

### Cloud interoperability

- Standard protocols
- Frameworks

### Proof of concept (pilot projects)

evidence, typically derived from an experiment or pilot project, which demonstrates that a design concept, business proposal, etc., is feasible.
the company was awarded the contract on the strength of evaluation, proof of concept, and budget
### Conclusions

- The discussion concludes that the embedded gateway software component best suits all requirements and thus has been implemented as a composable part of the selected reactive OPC UA
framework which promotes separation of concerns and reusability.
