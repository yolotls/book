# Where

The main monorepo holding all the crates is here:
[https://github.com/yolotls/yolotls](https://github.com/yolotls/yolotls)

With this documentation being here:
[https://github.com/yolotls/book](https://github.com/yolotls/book)

Rendered into here:
[https://yolotls.github.io/book/](https://yolotls.github.io/book/)

And discord being here:
[https://discord.gg/rXVsmzhaZa](https://discord.gg/rXVsmzhaZa)

## Context

Typiclally people either use the integrations which in turn use these crates:

| Crate            | no_std | no-alloc | Description                   |
| :---             | :---   | :---     | :---                          |
| [ytls-server]    | ✅     | ✅       | Server Context                |
| ytls-client      | WIP    | ✅       | WIP Client Context            |

## Protocol

Which then use these crates to tie up the protocol context together:

| Crate             | no_std | no-alloc | Description                   |
| :---              | :---   | :---     | :---                          |
| [ytls-record]     | ✅     | ✅       | Record layer parser & builder |
| [ytls-traits]     | ✅     | ✅       | Traits used to de-couple      |
| [ytls-extensions] | ✅     | ✅       | TLS Extensions                |
| [ytls-typed]      | ✅     | ✅       | Rich protocol types           |
| [ytls-keys]       | ✅     | ✅       | Keying & schedule operations  |
| [ytls-util]       | ✅     | ✅       | Utilities used                |

## Crypto

And where user brings their own crypto or uses one of the processors:

| Crate            | no_std | no-alloc | Description                   |
| :---             | :---   | :---     | :---                          |
| [ytls-rustcrypto]| ✅     | ✅       | Rustcrypto primitives         |

[ytls-record]: https://github.com/yolotls/yolotls/tree/main/record
[ytls-traits]: https://github.com/yolotls/yolotls/tree/main/traits
[ytls-extensions]: https://github.com/yolotls/yolotls/tree/main/extensions
[ytls-typed]: https://github.com/yolotls/yolotls/tree/main/typed
[ytls-keys]: https://github.com/yolotls/yolotls/tree/main/keys
[ytls-util]: https://github.com/yolotls/yolotls/tree/main/util
[ytls-server]: https://github.com/yolotls/yolotls/tree/main/server
[ytls-rustcrypto]: https://github.com/yolotls/yolotls/tree/main/crypto/rustcrypto