# AZURE Research on Connectivity

## IoT Central Notes

IoT Central uses the Azure [IoT Hub Device Provisioning service (DPS)](https://docs.microsoft.com/en-us/azure/iot-dps/about-iot-dps) to manage the connection process. Using DPS enables:

- IoT Central to support onboarding and connecting devices at scale.
- You to generate device credentials and configure the devices offline without registering the devices through IoT Central UI.
- You to use your own device IDs to register devices in IoT Central. Using your own device IDs simplifies integration with existing back-office systems.
- A single, consistent way to connect devices to IoT Central.

To secure the communication between a device and your application, IoT Central supports both shared access signatures (SAS) and X.509 certificates. X.509 certificates are recommended in production environments.

IoT Central also enables OEMs to mass manufacture devices that can connect without first being registered. An OEM generates suitable device credentials, and configures the devices in the factory.

> **Conclusion** MP: authentication proces must
>
> - identify the device
> - associate the device with the service
> - associate the device with the appropriate IoT Central application.
> - associate the device with the device template
>

### Shared Access Signature (SAS)

## Software Development Kit
