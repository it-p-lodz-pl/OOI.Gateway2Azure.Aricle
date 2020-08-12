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

## Digital Twin Description language

## [IModelParser Interface](https://docs.microsoft.com/en-us/dotnet/api/microsoft.azure.iot.digitaltwin.model.contracts.imodelparser?view=azure-dotnet-preview)


## See Also

- [Quickstart: Send telemetry from a device to an IoT hub and read it with a back-end application (.NET)](https://docs.microsoft.com/EN-us/azure/iot-hub/quickstart-send-telemetry-dotnet#clean-up-resources)
- [„Use the Azure Digital Twins APIs and SDKs - Azure Digital Twins”](https://docs.microsoft.com/EN-us/azure/digital-twins/how-to-use-apis-sdks)
- [„Azure/azure-sdk-for-net”, GitHub.](https://github.com/Azure/azure-sdk-for-net)
- [Microsoft.Azure.DigitalTwins.Parser](https://www.nuget.org/packages/Microsoft.Azure.DigitalTwins.Parser/)
- [Microsoft.Azure.IoT.DigitalTwin.Parser](https://www.nuget.org/packages/Microsoft.Azure.IoT.DigitalTwin.Parser/1.0.12-preview)
