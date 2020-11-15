# Part 1 PubSub Description Inconsistency

Describe the [PubSub Architecture  Part 1, 6.6 Synergy of models](https://reference.opcfoundation.org/v104/Core/docs/Part1/6.6/)

- The specification states "PubSub and Client-Server are both based on the OPC UA Information Model. " but in `Figure 8 – Integrated Client-Server and PubSub models`  there is Address Space. From this statement, someone could derive that the AS and IM are the same terms (are synonyms), but parts 3 and 5 states something different.
- Parts 3, 4, 5 of the OPC UA spec describes interoperability between OPC UA Client and OPC UA Server Address Space, and it makes sense because the client uses many services (including but not limiting to [7.11 Subscription Service Set](https://reference.opcfoundation.org/v104/Core/docs/Part1/7.11/) against Address Space exposed by the server.
- There are no similar services available for Subscribers, therefore the Publisher dependency on the Address Space doesn't make any sense - the specification doesn't describe interoperability between Subscriber and Address Space.
- Additionally, the `Publisher` dependency on Address Space makes it impossible to support interoperability between the Cyber-Physical Network based on PubSub and cloud-based services. Instead, interoperability must be deployed based on a Server concept alone.
- Subscriber and published should mirror the functionality. Why only the Publisher is an embedded module of the OPC UA server.
- One box cannot represent OPC UA Server, OPC UA Application, and Publisher at the same time - the fig is inconsistent.
