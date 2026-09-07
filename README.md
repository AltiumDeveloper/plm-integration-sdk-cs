# Altium PLM integration SDK

The Altium PLM integration SDK is a C# framework for building a **custom PLM connector** — a
service that integrates a third-party PLM system with an [Altium 365](https://www.altium.com/altium-365)
Workspace. The connector acts as an adapter between Altium 365 and your PLM: Altium 365 communicates
with it over gRPC, and it translates Altium's models and operations into calls your PLM understands.
Use it to add PLM integration for systems that Altium 365 does not support out of the box.

![Altium 365 connecting to a PLM through a custom connector](Documentation/images/ConnectorAsAdapter.png)

**Full documentation:** https://altiumdeveloper.github.io/plm-integration-sdk-cs/

## Features

- Provides the base gRPC service and middleware (auth context, exception handling, model mapping,
  logging) — you implement just two interfaces: `ICustomPlmService` and `ICustomPlmMetadataService`.
- Translates between the Altium 365 data model and your PLM's native types and operations.
- Supports component sync (to and from PLM), part choices, project and BOM publishing,
  relationships, and lifecycle state changes.
- Ships with a working, file-based example connector (`FilesystemPLMDriver`) for learning and debugging.
- Targets .NET 8 / C#.

## Prerequisites

- [.NET 8.0 SDK](https://dotnet.microsoft.com/en-us/download/dotnet/8.0)
- An Altium 365 Workspace with an Enterprise license, plus a license for the **Generic Connector**
  PLM driver (required to configure a PLM Integration).
- Altium Designer — to exercise the sync and publish workflows.

## Getting started

1. Read the [Introduction](Documentation/articles/intro.md) and [Solution Description](Documentation/articles/solution.md)
   to understand the architecture and the two interfaces you implement.
2. Run the included [`FilesystemPLMDriver`](FilesystemPLMDriver) example to see a working connector
   and observe the flow of typical operations.
3. Follow [Testing with Altium 365](Documentation/articles/testing.md) to configure a PLM Connection
   and run sync/publish end to end.

## Documentation

- [Introduction](Documentation/articles/intro.md)
- [Solution Description](Documentation/articles/solution.md)
- [Operational Flows](Documentation/articles/operations-flow.md)
- [gRPC Interface](Documentation/articles/interface.md)
- [Testing with Altium 365](Documentation/articles/testing.md)
- [FAQ](Documentation/articles/faq.md)
- [API Reference](https://altiumdeveloper.github.io/plm-integration-sdk-cs/) (generated)

## License

Licensed under the [MIT License](LICENSE). Copyright (c) Altium LLC.
