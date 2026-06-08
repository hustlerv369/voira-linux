# Security Policy

## Supported versions

Voira receives security patches for the **latest stable release** only.

| Version | Supported          |
| ------- | ------------------ |
| 0.1.x   | :white_check_mark: |
| < 0.1.0 | :x:                |

Major releases will follow this matrix going forward.

## Reporting a vulnerability

**Please do NOT open public GitHub issues for security vulnerabilities.**

### How to report

Send an email to **vojtech.horava@gmail.com** (will be migrated to
`security@voiravoice.cz` in Q3 2026) with:

1. **Subject:** `[Voira Security] Brief description`
2. **Body:**
   - Affected component (binary version, Linux distro, install method)
   - Steps to reproduce
   - Impact assessment (data exposure, RCE, privilege escalation, etc.)
   - Proof of concept (if applicable)
   - Your suggested fix (if you have one)

### Encryption (optional)

If you want to encrypt the report:

- GPG key fingerprint: *To be published* (Q3 2026)
- Until then, send encrypted via Signal: ask via email for handle

### Response timeline

| Step | Target SLA |
|---|---|
| **Acknowledgment** | 48 hours |
| **Initial assessment** | 7 days |
| **Fix released** | 30 days for high/critical, 90 days for medium/low |
| **Public disclosure** | 7 days after fix released (coordinated) |

## Scope

### In scope

- Voira binaries (.AppImage, .deb, .rpm) distributed via this repository
- Backend API (`https://voira-api.46-36-39-161.nip.io`)
- Web application (`https://voiravoice.cz`)
- Tauri update verification (Ed25519 signature handling)
- Authentication flows (magic-link, Google OAuth)
- Payment flows (Lemon Squeezy integration)

### Out of scope

- Vulnerabilities in third-party dependencies (report directly to upstream)
- Social engineering attacks
- DoS/DDoS (we use cloud WAF; tell us if you have a creative bypass)
- Self-XSS, broken CORS without exploitable impact
- Disclosure of public information

## Recognition

Researchers who report valid vulnerabilities will be:

1. Acknowledged in [HALL-OF-FAME.md](docs/HALL-OF-FAME.md) (opt-in)
2. Offered free Voira Pro lifetime subscription
3. For critical findings: monetary reward at our discretion ($50-$500)

## Signature verification

Voira binaries are signed with **Ed25519** via Tauri 2 updater.

**Public key:**

```
dW50cnVzdGVkIGNvbW1lbnQ6IG1pbmlzaWduIHB1YmxpYyBrZXk6IEQ3OEEwNDg4NTFDMDRDNjgKUldSb1RNQlJpQVNLMSs4cWZlbUhuNGVuUjJMdHJ6TmFLaC9mb29RSndxaStxS04zeW1wdFZnN1QK
```

(base64-encoded, key ID: `D78A048851C04C68`)

### Verify a release

```bash
# Download artifact + signature
curl -LO https://github.com/hustlerv369/voira-linux/releases/latest/download/Voira-linux.AppImage
curl -LO https://github.com/hustlerv369/voira-linux/releases/latest/download/Voira-linux.AppImage.sig

# Verify with minisign
minisign -Vm Voira-linux.AppImage -P RWRoTMBRiASK1+8qfemHn4enR2LtrzNaKh/fooQJwqi+qKN3ympt
```

If verification fails, **do not run the binary** and report to security
contact above.

## Past advisories

None yet. (Will be listed here as `docs/advisories/CVE-YYYY-XXXXX.md`)
