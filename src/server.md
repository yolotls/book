# Server

Server context is driven with the chosen crypto processor and implementing the required configuration trait.

A combined non-detached example is provided here:
[server/examples/listener.rs](https://github.com/yolotls/yolotls/blob/main/server/examples/listener.rs)

You can also implement the handshake and application contextes separately providing an opportunity to free the memory from handshake context.
