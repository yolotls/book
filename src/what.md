# What

- ⚠️  Currently experimental, non-audited / reviewed
- sans-io, no_std, no_alloc, non-monolithic & no arenas Core
- Minimal / no dependency
- De-coupled layers crypto, record, builder, server/client contextes.
- Bring your own crypto or use one of the providers - no defaults
- Ability to build protcol analyzers / your own suite using bits from
- Async optional & does not require Send+Sync
- Trait based callbacks over storing state
- Enum static dispatch over dynamic dispatch
- Atomics free
- TLS 1.3 Only (for now)
- ECDHE no-PSK only (for now)

## Todo Plan

- Client Context
- QUIC
- More integrations: Tokio, Yaws blueprint
- More crypto processors
- DTLS
