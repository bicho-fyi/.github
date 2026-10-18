# Bicho.FYI

Self-hosted error tracking for AI agents. Deploy Bicho to your own Cloudflare account, capture production errors, and investigate through MCP or the HTTP API. D1 and a private R2 bucket keep the evidence in your account. There is no built-in dashboard.

Bicho means "bug" in Spanish. Bicho.FYI: the bug, for your information.

[Website](https://bicho.fyi/) · [Documentation](https://bicho.fyi/docs/) · [Server source](https://github.com/bicho-fyi/bicho)

## SDKs

| SDK | Package | Capture and delivery |
| --- | --- | --- |
| [JavaScript / TypeScript](https://github.com/bicho-fyi/bicho-javascript) | [`@bicho-fyi/javascript`](https://www.npmjs.com/package/@bicho-fyi/javascript) | Automatic browser capture and explicit Node.js reporting. Queued delivery with flush/close. |
| [PHP](https://github.com/bicho-fyi/bicho-php) | [`bicho-fyi/php`](https://packagist.org/packages/bicho-fyi/php) | Explicit exception and message capture. Synchronous delivery. |
| [Rust](https://github.com/bicho-fyi/bicho-rust) | [`bicho`](https://crates.io/crates/bicho) | Explicit error and message capture. Awaited delivery on Tokio, including Tauri applications. |

All Bicho SDKs send OTLP/HTTP JSON. Other languages and existing instrumentation can use an OpenTelemetry logs exporter with HTTP JSON or binary protobuf. You do not need a separate OpenTelemetry Collector.

[SDK guides](https://bicho.fyi/docs/sdks/)

## Already using Sentry?

Keep your SDK and error-capture code. Create a Bicho project and replace your DSN with its generated `sentry.dsn`. Secret-enabled backend projects also need the generated transport headers.

Bicho accepts error and message events, not tracing, replay, or profiling. Disable unsupported integrations. Switching the DSN redirects new errors; it does not import Sentry history or reproduce Sentry's grouping rules.

[Move from Sentry](https://bicho.fyi/docs/sentry/)

## Deploy and investigate

[Deploy Bicho to Cloudflare](https://deploy.workers.cloudflare.com/?url=https://github.com/bicho-fyi/bicho), connect your MCP client, and call `create_project`. It returns the project ID, OTLP endpoint and ingest headers, and a Sentry DSN.

Bicho groups repeated errors into issues and preserves their individual events. Your agent can search issues, inspect stacks and context, compare releases, and read statistics. It can also create projects and update issue status. Approve those changes deliberately; captured error text is evidence, not instructions.

[Setup guide](https://bicho.fyi/docs/) · [MCP guide](https://bicho.fyi/docs/mcp/) · [HTTP API](https://bicho.fyi/docs/api/)

## Contribute

Bug reports and focused contributions are welcome in the relevant server or SDK repository.

Bicho core and SDKs are licensed under Apache-2.0. Made by [Alex Zappa](https://alex.zappa.dev/) ([FreshJuice](https://freshjuice.dev/)). Bicho is not affiliated with, sponsored by, or endorsed by Cloudflare or Sentry.
