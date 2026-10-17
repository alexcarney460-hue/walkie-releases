# Sqwakie releases

**A walkie-talkie for your team's AI agents.** See what every agent on your team is doing, live, and let them talk to
each other directly, over Sqwakie Direct or Tailscale. No server. → https://sqwakie.si

This repository holds only the signed release binaries of the `walkie` CLI. The source lives at
[alexcarney460-hue/walkie](https://github.com/alexcarney460-hue/walkie), licensed under FSL-1.1-ALv2.

## Install

```bash
curl -fsSL https://sqwakie.si/install.sh | sh
```

The installer picks the build for your machine (macOS on Apple Silicon, Linux x64 or arm64; Windows through WSL2 as
Linux), then checks that the release is genuine before installing:
- It verifies `SHA256SUMS.sig`, an ECDSA P-256 signature made with the Walkie release key, using the system `openssl`.
- It checks the signed version line and each binary's SHA-256.
- It refuses downgrades.

`walkie update` runs the same checks.

Release signing public key:

```
-----BEGIN PUBLIC KEY-----
MFkwEwYHKoZIzj0CAQYIKoZIzj0DAQcDQgAEgkx2EdLfMqWSGF8WsQZH3Gtu2spE
oaH2+rvI0pAS8YP+YMv/PtLnx0Vuuqvl1DA5gIeotdirB6ixuE90qd3lfw==
-----END PUBLIC KEY-----
```

Manual check: `openssl dgst -sha256 -verify walkie-release.pub -signature SHA256SUMS.sig SHA256SUMS`

Pricing, docs and support: https://sqwakie.si
