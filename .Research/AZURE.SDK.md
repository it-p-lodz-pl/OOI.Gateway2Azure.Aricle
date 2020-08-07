# Research on the awaitable Azure SDK for .NET

## Quickstart: Send telemetry from a device to an IoT hub and read it with a back-end application (.NET)

A device must be registered with your IoT hub before it can connect. In this quickstart, you use the Azure Cloud Shell to register a simulated device.

## Azure IoT Central

### [Sample device code](https://docs.microsoft.com/EN-us/azure/iot-central/core/concepts-get-connected#sample-device-code)

```C#
    console.log('deviceId=' + result.deviceId);
    var connectionString = 'HostName=' + result.assignedHub + ';DeviceId=' + result.deviceId + ';x509=true';
    var hubClient = Client.fromConnectionString(connectionString, iotHubTransport);
```

From the code we must derive that the `connectionString` can be calculated using the information provided by the Cloud Shell

## See Also

- [Quickstart: Send telemetry from a device to an IoT hub and read it with a back-end application (.NET)](https://docs.microsoft.com/EN-us/azure/iot-hub/quickstart-send-telemetry-dotnet#clean-up-resources)