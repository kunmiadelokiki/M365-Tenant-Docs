# M365 Tenant Configuration Overview

Enterprise documentation for a Microsoft 365 tenant covering Conditional Access, Device Compliance, and Intune Configuration Profiles.

## Contents

| Document | Description |
|---|---|
| [Conditional Access Policies](docs/01-Conditional-Access-Policies.md) | 15 policies governing MFA, legacy auth blocking, device compliance, and app protection |
| [Device Compliance Policies](docs/02-Device-Compliance-Policies.md) | Windows 11, Android, and VM compliance requirements |
| [Configuration Profiles](docs/03-Configuration-Profiles.md) | Windows Update Ring policy and patching behaviour |
| [Tenant Overview (PDF)](M365-Tenant-Configuration-Overview.pdf) | Downloadable PDF — CA, Compliance, and Config Profiles |

## Key Highlights

- **4 Conditional Access policies actively enforced** covering admin MFA, guest MFA, internal user MFA, and legacy auth blocking
- **11 policies in Report-Only mode** pending validation before enforcement
- **Device compliance** requires BitLocker, Secure Boot, and encryption on Windows 11 endpoints
- **Windows Update Ring** defers quality and feature updates by 4 days with an 8-day deadline

## Author

Prepared by **Olu Adelokiki** — [LinkedIn](https://www.linkedin.com/in/olukunmi-adelokiki)

---

*Generated: 2026-03-22*
