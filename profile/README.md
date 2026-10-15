<div align="center">

# 🪲 Bicho.FYI

### the bug, FYI.

Self-hosted error tracking on Cloudflare Workers.<br>
Capture errors with OpenTelemetry. Investigate them through MCP.<br>
Keep the data in your own Cloudflare account.

[![Cloudflare Workers](https://img.shields.io/badge/Cloudflare-Workers-F38020?logo=cloudflare&logoColor=white)](https://github.com/bicho-fyi/bicho)
[![OpenTelemetry](https://img.shields.io/badge/OpenTelemetry-OTLP-425CC7?logo=opentelemetry&logoColor=white)](https://opentelemetry.io/docs/specs/otlp/)
[![MCP](https://img.shields.io/badge/MCP-investigation-24292F)](https://github.com/bicho-fyi/bicho#mcp)
[![License](https://img.shields.io/badge/license-Apache--2.0-green)](https://github.com/bicho-fyi/bicho/blob/main/LICENSE)

[Website](https://bicho.fyi) · [Server documentation](https://github.com/bicho-fyi/bicho#readme) · [JavaScript SDK](https://github.com/bicho-fyi/bicho-javascript#readme)

</div>

---

## Errors in. Answers within reach.

Bicho groups exception and error logs into issues, stores the captured evidence in D1 and R2, and gives your tools an API to inspect it. You can use it without a dashboard or an OpenTelemetry Collector.

Connect an MCP client to search issues, inspect stack traces, compare releases and read event statistics. Agents can register projects and update issue status; captured events stay intact.

## Pick your starting point

| Project | What it does |
| :--- | :--- |
| [**bicho**](https://github.com/bicho-fyi/bicho) | The server: OTLP ingestion, issue grouping, D1/R2 storage, HTTP API and MCP tools. Deploy it to your Cloudflare account. |
| [**bicho-javascript**](https://github.com/bicho-fyi/bicho-javascript) | JavaScript and TypeScript SDK: automatic browser error capture and explicit Node.js reporting. Available as [`@bicho-fyi/javascript`](https://www.npmjs.com/package/@bicho-fyi/javascript). |

For other languages, send logs through an OpenTelemetry exporter using OTLP/HTTP JSON or binary protobuf.

## Run your own instance

[![Deploy to Cloudflare](https://deploy.workers.cloudflare.com/button)](https://deploy.workers.cloudflare.com/?url=https://github.com/bicho-fyi/bicho)

Deploy the server, connect your MCP client, and call `create_project`. Bicho returns a project ID and the OTLP endpoint and headers for your application. [Follow the setup instructions](https://github.com/bicho-fyi/bicho#deploy-to-cloudflare).

## Built in the open

Bug reports and focused contributions are welcome. [Open a server issue](https://github.com/bicho-fyi/bicho/issues) or [report an SDK issue](https://github.com/bicho-fyi/bicho-javascript/issues).

<sub>Made by [Alex Zappa](https://alex.zappa.dev/) at [FreshJuice](https://freshjuice.dev/). Apache-2.0.</sub>
