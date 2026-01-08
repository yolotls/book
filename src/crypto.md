# Crypto

CryptoConfig (trait) is provided for:
- Crypto processor (e.g. rustcrypto) to implement configured initialization
- End-user to bring their desired crypto through the CryptoConfig

No context makes the choice of crypto for the end-user by default.

End-user can even implement their own crypto configuration.

Validation of all the crypto processors are done through trait impl.
