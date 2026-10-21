# AVB Signing Keys — Xiaomi Redwood

Private key files (`*.pem`) are excluded from git via `.gitignore`.
**Never commit RSA private keys to a public repository.**

## Files
| File | Purpose |
|------|---------|
| `redwood_avb_recovery.pem`      | RSA-4096 private key — signs recovery vbmeta |
| `redwood_avb_vbmeta_system.pem` | RSA-4096 private key — signs vbmeta_system   |

## Extract the public key for distribution
```bash
avbtool extract_public_key \
    --key keys/redwood_avb_recovery.pem \
    --output keys/redwood_avb_recovery.pub
```

## Regenerate keys
```bash
openssl genrsa -out keys/redwood_avb_recovery.pem 4096
openssl genrsa -out keys/redwood_avb_vbmeta_system.pem 4096
```
