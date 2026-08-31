# squirix

[![CI](https://github.com/squirix/squirix/actions/workflows/ci.yml/badge.svg?branch=main)](https://github.com/squirix/squirix/actions/workflows/ci.yml)
[![License: Apache 2.0](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
[![NuGet](https://img.shields.io/nuget/vpre/squirix?logo=nuget&logoColor=white&label=NuGet&color=004880)](https://www.nuget.org/profiles/squirix)
[![.NET](https://img.shields.io/badge/.NET-10.0-512BD4?logo=dotnet&logoColor=white)](https://dotnet.microsoft.com/download/dotnet/10.0)
[![Slack](https://img.shields.io/badge/Slack-join-4A154B?logo=slack&logoColor=white)](https://squirix.slack.com)

**squirix** — an open-source .NET organization building a distributed cache for .NET 10 (typed client SDK, gRPC
transport, journal-backed durability, operational surfaces) and developer tooling: deterministic concurrency testing
for .NET libraries and Roslyn analyzers.

[squirix.io](https://squirix.io) · [Documentation](https://github.com/squirix/squirix#documentation) ·
[Issues](https://github.com/squirix/squirix/issues) · [Slack](https://squirix.slack.com)

> Early preview — evaluation and contributor feedback welcome; not production-ready yet.

## Start Here

| Area | Where |
| --- | --- |
| **Repositories** | All projects are listed in [Public repositories](#public-repositories) below |
| **NuGet packages** | [NuGet profile](https://www.nuget.org/profiles/squirix) — all published packages |
| **Quick starts** | Each repository ships its own quick-start guide in its README |

### NuGet Packages

All packages are published under the [squirix NuGet profile](https://www.nuget.org/profiles/squirix).

| Package | Role |
| --- | --- |
| [`squirix`](https://www.nuget.org/packages/squirix/) | Client SDK — `SquirixClient`, `ICache<T>`, serialization |
| [`squirix.server`](https://www.nuget.org/packages/squirix.server/) | Server runtime — routing, durability, gRPC host |
| [`squirix.server.tool`](https://www.nuget.org/packages/squirix.server.tool/) | Standalone `squirix-server` global tool |
| [`squirix.analyzers`](https://www.nuget.org/packages/squirix.analyzers/) | Design-time Roslyn analyzers enforcing squirix coding conventions |
| [`braid`](https://www.nuget.org/packages/braid/) | Deterministic concurrency testing for .NET libraries |

## Public Repositories

| Repository | Description |
| --- | --- |
| [**squirix**](https://github.com/squirix/squirix) | Distributed cache — `Squirix` client, `Squirix.Server` runtime, durability, REST/gRPC |
| [**squirix.analyzers**](https://github.com/squirix/squirix.analyzers) | Design-time Roslyn analyzers enforcing squirix coding conventions |
| [**braid**](https://github.com/squirix/braid) | Deterministic async concurrency testing for .NET libraries |

Extension packages (advanced APIs, clustering, operations, serializers, arena) live in separate repositories and may be
private during early development.

## Get Involved

- Pick a repository above and open an issue or pull request there — bugs, API ideas, and docs improvements are always welcome.
- Each repository ships its own contributing guide.
- Community and support: [squirix.io](https://squirix.io) · [Slack](https://squirix.slack.com)
- Contact: [admin@squirix.io](mailto:admin@squirix.io)

## SAST Tools

[![Powered by NDepend](assets/powered-by-ndepend.png)](https://www.ndepend.com/)

[PVS-Studio](https://pvs-studio.com/pvs-studio/?utm_source=website&utm_medium=github&utm_campaign=open_source) - static code analyzer for Enterprise (C, C++, C#, Go, and Java) and Web (JS and TS) development.

## License

Apache-2.0 — see [squirix/LICENSE](https://github.com/squirix/squirix/blob/main/LICENSE).
