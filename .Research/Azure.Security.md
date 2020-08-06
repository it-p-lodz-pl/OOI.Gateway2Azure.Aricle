# Azure Security

## Service Bus

### Service Bus authentication and authorization

There are two ways to authenticate and authorize access to Azure Service Bus resources: Azure Activity Directory (Azure AD) and Shared Access Signatures (SAS). This article gives you details on using these two types of security mechanisms.

#### Azure Active Directory

Azure AD integration for Service Bus resources provides role-based access control (RBAC) for fine-grained control over a client’s access to resources. You can use role-based access control (RBAC) to grant permissions to a security principal, which may be a user, a group, or an application service principal. The security principal is authenticated by Azure AD to return an OAuth 2.0 token. The token can be used to authorize a request to access an Service Bus resource (queue, topic, etc.).

#### Shared access signature

cryptographic key with associated rights on a Service Bus resource. Clients can then gain access to that resource by presenting a SAS token, which consists of the resource URI being accessed and an expiry signed with the configured key.

## Shared Access Signatures

SAS guards access to Service Bus based on authorization rules.

An authorization rule has a name, is associated with specific rights, and carries a pair of cryptographic keys. You use the rule's name and key via the Service Bus SDK or in your own code to generate a SAS token. A client can then pass the token to Service Bus to prove authorization for the requested operation.

Azure Service Bus supports authorizing access to a Service Bus namespace and its entities using Azure Active Directory (Azure AD). Authorizing users or applications using **OAuth 2.0** token returned by Azure AD provides superior security and ease of use over shared access signatures (SAS). 

Shared Access Signatures are a claims-based authorization (MP?? _authentication_ )mechanism using simple tokens. Using SAS, keys are never passed on the wire. Keys are used to cryptographically sign information that can later be verified by the service. SAS can be used similar to a username and password scheme where the client is in immediate possession of an authorization rule name and a matching key. SAS can also be used similar to a federated security model, where the client receives a time-limited and signed access token from a security token service without ever coming into possession of the signing key.

SAS authentication (MP?? authentication == authorization) in Service Bus is configured with named Shared Access Authorization Rules having associated access rights, and a pair of primary and secondary cryptographic keys. The keys are 256-bit values in Base64 representation. You can configure rules at the namespace level, on Service Bus relays, queues, and topics.

The Shared Access Signature token contains the name of the chosen authorization rule, the URI of the resource that shall be accessed, an expiry instant, and an HMAC-SHA256 cryptographic signature computed over these fields using either the primary or the secondary cryptographic key of the chosen authorization rule.

## IoT Hub

**TBD**

## Device Provisioning Services

**TBD**

## IoT Central

**TBD**

## See also

- [Service Bus access control with Shared Access Signatures](https://docs.microsoft.com/EN-us/azure/service-bus-messaging/service-bus-sas)