# AZURE Research on Connectivity <!-- omit in toc -->

## Table of content <!-- omit in toc -->

- [IoT Central Notes](#iot-central-notes)
  - [Get connected to Azure IoT Central](#get-connected-to-azure-iot-central)
  - [IoT Hub](#iot-hub)
  - [IoT Hub Device Provisioning](#iot-hub-device-provisioning)
  - [Shared Access Signature (SAS)](#shared-access-signature-sas)
  - [Implement the device](#implement-the-device)
  - [Software Development Kit](#software-development-kit)

## IoT Central Notes

### Get connected to Azure IoT Central

Types of device:

- **Standalone device**: a standalone device connects directly to IoT Central. A standalone device typically sends telemetry from its onboard or connected sensors to your IoT Central application. Standalone devices can also report property values, receive writable property values, and respond to commands.
- **Gateway device**: A gateway device manages one or more downstream devices that connect to your IoT Central application. You use IoT Central to configure the relationships between the downstream devices and the gateway device. To learn more, see Define a new IoT gateway device type in your Azure IoT Central application.
- **Edge device** - An edge device connects directly to IoT Central, but acts as an intermediary for other devices known as leaf devices. An edge device is typically located close to the leaf devices for which it's acting as an intermediary. IoT Central only sees the edge device, not the leaf devices connected to the edge device.

> MP Comment: to fulfill our assumption we must implement **Gateway device**.

Typically, a device must be registered in the IoT Central application before it can connect. However, IoT Central does support scenarios where devices can connect without first being registered.

### IoT Hub

Azure IoT Central uses Azure IoT Hub as a cloud gateway that enables device connectivity. IoT Hub enables:

- Data ingestion at scale in the cloud.
- Device management.
- Secure device connectivity.

To learn more about IoT Hub, see [Azure IoT Hub Documentation](https://docs.microsoft.com/en-us/azure/iot-hub/)

### IoT Hub Device Provisioning

IoT Central uses the Azure [IoT Hub Device Provisioning service (DPS)](https://docs.microsoft.com/en-us/azure/iot-dps/about-iot-dps) to manage the connection process. Using DPS enables:

- IoT Central to support onboarding and connecting devices at scale.
- You to generate device credentials and configure the devices offline without registering the devices through IoT Central UI.
- You to use your own device IDs to register devices in IoT Central. Using your own device IDs simplifies integration with existing back-office systems.
- A single, consistent way to connect devices to IoT Central.

To secure the communication between a device and your application, IoT Central supports both Shared Access Signatures (SAS) and X.509 certificates. X.509 certificates are recommended in production environments.

IoT Central also enables OEMs to mass manufacture devices that can connect without first being registered. An OEM generates suitable device credentials, and configures the devices in the factory.

> **Conclusion** MP: authentication proces must
>
> - identify the device
> - associate the device with the service
> - associate the device with the appropriate IoT Central application.
> - associate the device with the device template
>

### Shared Access Signature (SAS)

To secure the communication between a device and your application, IoT Central supports both shared access signatures (SAS) and X.509 certificates. X.509 certificates are recommended in production environments.

> MP Comments - documentation doesn't cover the topic how it works.

### Implement the device

Use one of the Azure IoT device SDKs to implement the behavior of your device. The code should:

- Register the device with DPS and use the information from DPS to connect to the internal IoT hub in your IoT Central application.
- Send telemetry in the format that the device template in IoT Central specifies. IoT Central uses the device template to determine how to use the telemetry for visualizations and analysis.
- Synchronize property values between the device and IoT Central. The device template specifies the property names and data types so that IoT Central can display the information.
- Implement command handlers for the commands specifies in the device template. The device template specifies the command names and parameters that the device should use.

### Software Development Kit

For more information about the supported languages and SDKs, see [Understand and use Azure IoT Hub device SDKs](https://docs.microsoft.com/en-us/azure/iot-hub/iot-hub-devguide-sdks#azure-iot-hub-device-sdks).

- [Microsoft Azure IoT SDK for .NET](https://github.com/azure/azure-iot-sdk-csharp#microsoft-azure-iot-sdk-for-net)
