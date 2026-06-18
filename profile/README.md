# squirix

[![CI](https://github.com/squirix/squirix/actions/workflows/ci.yml/badge.svg?branch=main)](https://github.com/squirix/squirix/actions/workflows/ci.yml)
[![License: Apache 2.0](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
[![NuGet](https://img.shields.io/badge/NuGet-0.1.0--preview.5-004880?logo=nuget&logoColor=white)](https://www.nuget.org/profiles/squirix)
[![.NET](https://img.shields.io/badge/.NET-10.0-512BD4?logo=dotnet&logoColor=white)](https://dotnet.microsoft.com/download/dotnet/10.0)
[![Slack](https://img.shields.io/badge/Slack-join-4A154B?logo=slack&logoColor=white)](https://squirix.slack.com)

**Experimental distributed cache for .NET 10** — typed client SDK, gRPC transport, journal-backed durability, and
operational surfaces on the server.

[squirix.io](https://squirix.io) · [Documentation](https://github.com/squirix/squirix#documentation) ·
[Issues](https://github.com/squirix/squirix/issues) · [Slack](https://squirix.slack.com)

> **0.1.0-preview.5** — early evaluation and contributor feedback welcome; not production-ready yet.
> [Release notes](https://github.com/squirix/squirix/blob/main/docs/release-notes/v0.1.0.md)

## Start here

| | |
| --- | --- |
| **Main repository** | [squirix/squirix](https://github.com/squirix/squirix) — client SDK, server runtime, docs, benchmarks |
| **NuGet packages** | [squirix profile on NuGet](https://www.nuget.org/profiles/squirix) — all published packages |
| **Quick start** | [README → Quick start](https://github.com/squirix/squirix#quick-start) |

```text
application  →  Squirix client SDK  →  squirix server node(s)
```

### NuGet packages

All packages are published under the [squirix NuGet profile](https://www.nuget.org/profiles/squirix):

| Package | Role |
| --- | --- |
| [`squirix`](https://www.nuget.org/packages/squirix/) | Client SDK — `SquirixClient`, `ICache<T>`, serialization |
| [`squirix.server`](https://www.nuget.org/packages/squirix.server/) | Server runtime — routing, durability, gRPC host |
| [`squirix.server.tool`](https://www.nuget.org/packages/squirix.server.tool/) | Standalone `squirix-server` global tool |

```bash
dotnet add package squirix --version 0.1.0-preview.5
dotnet tool install -g squirix.server.tool --version 0.1.0-preview.5
squirix-server run
```

Durable mode (WAL + snapshots):

```bash
squirix-server run --persist --data-dir ./data
```

```csharp
using Squirix;

await using var client = await SquirixClient.ConnectAsync("https://localhost:5001", cancellationToken);
var cache = await client.GetCacheAsync<string>("demo", cancellationToken);
await cache.SetAsync("greeting", "hello", cancellationToken: cancellationToken);
```

## Public repositories

| Repository | Description |
| --- | --- |
| [**squirix**](https://github.com/squirix/squirix) | Core cache — `Squirix` client, `Squirix.Server` runtime, durability, REST/gRPC |
| [**braid**](https://github.com/squirix/braid) | Deterministic async concurrency testing for .NET libraries |

Extension packages (advanced APIs, clustering, operations, serializers, arena) live in separate repositories and may be
private during early development.

## What squirix offers today

- Strongly typed `ICache<T>` with explicit read results and expiration on writes
- Strict client/server package boundaries over a shared gRPC contract
- Per-node WAL, snapshots, compaction, and recovery on startup
- Health, admin, Prometheus metrics, and OpenTelemetry tracing on the server
- Static consistent-hash routing with bootstrap client failover

## Get involved

- Report bugs or API ideas: [squirix/squirix issues](https://github.com/squirix/squirix/issues)
- Contributing guide: [contributing.md](https://github.com/squirix/squirix/blob/main/contributing.md)
- Contact: [admin@squirix.io](mailto:admin@squirix.io)

## License

Apache-2.0 — see [squirix/LICENSE](https://github.com/squirix/squirix/blob/main/LICENSE).
