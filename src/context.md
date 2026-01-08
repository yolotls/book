# Context

Context is the state machine that I/O "drivers" spin forward, typically with the given application & network I/O.

You might want to use these contextes when there is no driver for your environment e.g. in bare metal embedded environment that doesn't f.ex. use embassy or in a wasm environment with custom runtime etc.

The contextes are split between two depending on which end we are providing a state for: Server and Client.

Another example of these state machines can be found from [yaws](https://yaws-rs.github.io/book/yaws/architechture.html) architecture these contextes closely align to.
