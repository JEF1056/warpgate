# Vendored `russh` 0.65.0

Patched `src/server/encrypted.rs` (`read_userauth_request`):
- Reject `sk-*` security-key public key algorithms with `SSH_MSG_USERAUTH_FAILURE` (`reject_auth_request`) before certificate/key decoding.
- Treat `ssh_key::Error::Encoding(_)` as a rejected auth attempt (`reject_auth_request`) rather than aborting the SSH session.
