# Altium PLM integration SDK

Altium PLM integration SDK (referred to as the SDK) is a framework for building a custom PLM connector that exposes the gRPC endpoints used 
by Altium 365 to communicate with arbitrary PLM instances. It can be used to provide integration with the unsupported PLM systems. 

The resulting custom PLM connector works as a man-in-the-middle between Altium 365 and your PLM system, taking the role of an adapter. It is responsible
for translation of models and operations types used by Altium 365 into the format acceptable by your PLM system.
![Altium365 Connection](./images/ConnectorAsAdapter.png)

The SDK is distributed as a [C#](https://github.com/AltiumDeveloper/plm-integration-sdk-cs) service application with associated documentation and example configuration files.
The SDK comes with a working example of integration using a simple file system storage 
that can be deployed and connected to the Altium ecosystem, which is a great starting point 
for a custom implementation.

## Terminology

The documentation uses the following terms consistently:

 - **Altium PLM integration SDK** (or *the SDK*) — the C# framework in this repository. It provides the base gRPC service implementation and the middleware used to build a connector.
 - **Custom PLM connector** — the service you build with the SDK. It runs as an adapter (man-in-the-middle) between Altium 365 and your PLM system, translating models and operations between the two.
 - **PLM system** — the third-party PLM you are integrating with (for example, your enterprise PLM).
 - **gRPC endpoints / gRPC API** — the communication protocol, defined in `CustomPLM.proto`, that Altium 365 calls and the custom PLM connector implements.
 - **Generic Connector** — the driver name shown in the Altium 365 PLM Configuration UI that routes a PLM Connection to your custom PLM connector. It requires a dedicated license.

Please refer to [PLM Integration with an Altium 365 Workspace](https://www.altium.com/documentation/altium-365/plm-integration)
for detailed information on [Altium 365](https://www.altium.com/altium-365) integration options with PLM systems.

## References
 - [Articles](articles/intro.md)
 - [API Reference](api/index.md)
