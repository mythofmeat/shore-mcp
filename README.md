# shore-mcp

MCP (Model Context Protocol) server that exposes the
[Shore](https://github.com/mythofmeat/shore-core) chat daemon's CLI
surface for debugging and programmatic use. Talks to `shore-daemon` over the
Shore Wire Protocol (SWP) using the published
[`shore-swp-client`](https://crates.io/crates/shore-swp-client) and
[`shore-protocol`](https://crates.io/crates/shore-protocol) crates.

This is debug/development tooling. The intended consumer is an MCP-aware client
(Claude Code, MCP Inspector, etc.) talking JSON-RPC over stdio.

## Build

```sh
cargo build --release
```

The resulting binary is `target/release/shore-mcp`.

## Use

Point your MCP client at the binary; it speaks JSON-RPC on stdin/stdout. The
exposed tools mirror the `shore` CLI: status, send, log, memory, character,
config, model, usage, debug.

Reads daemon connection settings from `~/.config/shore/client.toml`.

## License

Dual-licensed under either of:

- Apache License, Version 2.0 ([LICENSE-APACHE-2.0](LICENSE-APACHE-2.0))
- MIT License ([LICENSE-MIT](LICENSE-MIT))

at your option.
