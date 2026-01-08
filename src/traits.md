# Traits

Traits are the ❤️  of everything

In order to provide non-monolithic de-coupling, traits are everywhere.

## Builder traits

Builder traits are involved in the record generation and provides callbacks to provide data upon construction before they are pushed into the wire

You can find them here:
[traits/src/t_builder.rs](https://github.com/yolotls/yolotls/blob/main/traits/src/t_builder.rs)

| Trait                     | Description                            |
| :---                      | :---                                   |
| HandshakeBuilder          | Construct handshakes e.g. ServerHello  |
| WrappedApplicationBuilder | For the user (application) traffic     |
| WrappedHandshakeBuilder   | Wrapped (protected) handshakes         |
| Server[..]Builder         | Server protected handshake messages    |

## Cryptography traits

Found here: [traits/src/t_crypto.rs](https://github.com/yolotls/yolotls/blob/main/traits/src/t_crypto.rs)

Example impl: [crypto/rustcrypto](https://github.com/yolotls/yolotls/tree/main/crypto/rustcrypto)

Context usage example: [server/examples/listener.rs](https://github.com/yolotls/yolotls/blob/main/server/examples/listener.rs#L154)

Processor config example: [crypto/rustcrypto/src/lib.rs](https://github.com/yolotls/yolotls/blob/main/crypto/rustcrypto/src/lib.rs#L96)

Validation through trait impl. [validation/crypto](https://github.com/yolotls/yolotls/tree/main/validation/crypto)

| Trait        | Description                                       |
| :---         | :---                                              |
| CryptoConfig | Crypto processor implements for end-user to BYOC  |
| CryptoSignerP[..]Processor | Signature processors                |
| Crypto[..]HmacProcessor  | HMAC Processors                       |
| Crypto[..]HkdfExtractProcessor | HKDF Extract Processors         |
| Crypto[..]HkdfGenProcessor     | HKDF Expand Processors          |
| CryptoX25519Processor | ECDHE X25519 Processor                   |
| Crypto[..]TranscriptProcessor | Transcript hashing Processors    |
| CryptoChaCha20Poly1305Processor | ChaCha20Poly1305 AEAD Processor |

## Context

Context is the stateful TLS context that is wound forward with data providing the protocol state machine.

Found here: [traits/src/t_ctx.rs](https://github.com/yolotls/yolotls/blob/main/traits/src/t_ctx.rs)

Example impls: [server/src](https://github.com/yolotls/yolotls/tree/main/server/src)

These are implemented in the contextes but they are de-coupled.

| Trait                 | Description                                   |
| :---                  | :---                                          |
| CtxHandshakeProcessor | Implement to provide processing for handshake |
| CtxApplicationProcessor | Implement to provide processing for application traffic |

## Input / Output

We have Left and Right sides for I/O where typically the Left is the Ciphertext Network I/O side and the right being side being the Application I/O for Cleartext.

The traits can be found here: [traits/src/t_io.rs](https://github.com/yolotls/yolotls/blob/main/traits/src/t_io.rs)

Example naive I/O impl found here: [server/examples/listener.rs](https://github.com/yolotls/yolotls/blob/main/server/examples/listener.rs#L65)

The I/O reflects how Left/Right also works in [yaws](https://yaws-rs.github.io/book/).

To "hook" I/O or integration with the given I/O traits the following traits are implemented somewhere the I/O is concerned.

| Trait      | Description |
| :---       | :---        |
| TlsLeftOut | Left (Ciphertext) or "Network" I/O egress side |
| TlsLeftIn  | same as TlsLeftOut but Network ingress         |
| TlsRight   | Right (Cleartext) or "Application" I/O side    |

## Keying

Traits for keys provides key / schedule operations.

Found from here: [traits/src/t_keys.rs](https://github.com/yolotls/yolotls/blob/main/traits/src/t_keys.rs)

Implemented here for TLS 1.3: [keys/src/tls13_key_schedule.rs](https://github.com/yolotls/yolotls/blob/main/keys/src/tls13_key_schedule.rs)

| Trait | Description |
| :---  | :---        |
| SecretStore | Used to store derived Application traffic keys |
| Tls13KeySchedule[..] | Key schedule operation states |

## Parsing

Found here: [traits/src/t_parser.rs]

| Trait | Description |
| :---  | :---        |
| ClientHelloProcessor | Client Hello parsing |
