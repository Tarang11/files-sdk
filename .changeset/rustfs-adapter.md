---
"files-sdk": minor
---

Add a RustFS adapter (`files-sdk/rustfs`). RustFS is the Apache-2.0 Rust object store that runs as a MinIO drop-in, and `rustfs()` mirrors the `minio()` adapter one-to-one: path-style addressing on by default (virtual-hosted needs `RUSTFS_SERVER_DOMAINS`), the `us-east-1` signing region matching the server's `RUSTFS_REGION` default, `"RustFS error"` provider labels, and the same `client: "aws-sdk" | "fetch"` engine choice with the `@aws-sdk`-free fetch engine defaulting on inside Cloudflare Workers. Credentials fall back to `RUSTFS_ACCESS_KEY_ID` / `RUSTFS_SECRET_ACCESS_KEY`, then to the `RUSTFS_ACCESS_KEY` / `RUSTFS_SECRET_KEY` names the server itself reads so one docker-compose `.env` configures both sides. Available to the CLI and MCP server as `--provider rustfs`.
