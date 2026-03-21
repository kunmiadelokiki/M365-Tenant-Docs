# Configuration Profiles

## Purpose

Configuration profiles push device settings and policies to enrolled endpoints via Microsoft Intune. These profiles manage Windows Update behaviour, security baselines, and other device configurations.

---

## UserCompute - Windows Update Ring Policy

**Purpose:** Controls how Windows quality and feature updates are delivered, deferred, and enforced on managed devices.

| Setting | Value |
|---|---|
| Profile Type | Windows Update for Business |
| Automatic Update Mode | Notify Download |
| Quality Update Deferral | 4 days |
| Feature Update Deferral | 4 days |
| Quality Update Deadline | 8 days |
| Feature Update Deadline | 8 days |
| Grace Period After Deadline | 2 days |
| Postpone Reboot Until Deadline | Enabled |
| Feature Update Rollback Window | 10 days |
| Drivers Excluded from Updates | Enabled |
| Microsoft Update Service Allowed | Enabled |
| User Can Pause Updates | Enabled |
| Allow Windows 11 Upgrade | Enabled |

---

## Risks and Considerations

- Quality and feature updates are deferred by only **4 days**. While this provides a short buffer, organisations in regulated industries may require a longer deferral window (7-14 days) to allow for compatibility testing.
- **Users are permitted to pause updates.** This can delay critical security patches. Consider restricting pause access for high-risk user populations.
- **Driver updates are excluded** from Windows Update. Ensure an alternative driver management strategy is in place to prevent driver-related vulnerabilities.
- The automatic update mode is set to **Notify Download**, meaning users must initiate the download. This relies on user action and may result in delayed patching.
