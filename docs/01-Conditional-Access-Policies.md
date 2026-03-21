# Conditional Access Policies

## Purpose

Conditional Access policies control how users and devices access cloud applications. They enforce security requirements such as multi-factor authentication (MFA), device compliance, and approved application usage based on conditions like user role, location, and client app type.

---

## Policy Summary

| Policy Name | Access Control | Enforcement State |
|---|---|---|
| Require MFA for admins | Require MFA | Enforced |
| Require MFA for external and guest users | Require MFA | Enforced |
| Block all legacy sign-ins that don't support MFA | Block Access | Enforced |
| Require MFA for internal users (admins not included) - Basic | Require MFA | Enforced |
| Require MDM-enrolled and compliant device (Preview) | Require Compliant Device | Report-Only |
| UserCompute - Conditional Access Policy | Require Approved Client App OR MFA | Report-Only |
| Require multifactor authentication for all users | Require MFA | Report-Only |
| Require MFA for Microsoft admin portals | Require MFA | Report-Only |
| Block legacy authentication | Block Access | Report-Only |
| Require MFA for guest access | Require MFA | Report-Only |
| Require compliant/hybrid joined device or MFA for all users | Require MFA OR Compliant Device OR Hybrid Joined Device | Report-Only |
| Require MFA for Azure management | Require MFA | Report-Only |
| Require approved client apps or app protection policies | Require Approved App OR App Protection Policy | Report-Only |
| Block access for unknown or unsupported device platform | Block Access | Report-Only |
| Require MFA for admins (template) | Require MFA | Report-Only |

---

## Policy Details

### Require MFA for admins

| Setting | Value |
|---|---|
| Enforcement State | Enforced |
| Target Applications | All Cloud Applications |
| Client App Types | All Client App Types |
| User Scope | Includes: 21 Admin Roles · Excludes: Break-glass account(s) |
| Access Control | Require MFA |

### Require MFA for external and guest users

| Setting | Value |
|---|---|
| Enforcement State | Enforced |
| Target Applications | All Cloud Applications |
| Client App Types | All Client App Types |
| User Scope | Includes: Guest / External Users · Excludes: Break-glass account(s) |
| Access Control | Require MFA |

### Block all legacy sign-ins that don't support MFA

| Setting | Value |
|---|---|
| Enforcement State | Enforced |
| Target Applications | All Cloud Applications |
| Client App Types | Exchange ActiveSync, Other Legacy Clients |
| User Scope | Includes: All Users · Excludes: Break-glass account(s) |
| Access Control | Block Access |

### Require MFA for internal users (admins not included) - Basic

| Setting | Value |
|---|---|
| Enforcement State | Enforced |
| Target Applications | All Cloud Applications |
| Client App Types | All Client App Types |
| User Scope | Includes: All Users · Excludes: Break-glass account(s), Guest / External Users, 21 Admin Roles |
| Access Control | Require MFA |

### Require MDM-enrolled and compliant device (Preview)

| Setting | Value |
|---|---|
| Enforcement State | Report-Only (Not Enforced) |
| Target Applications | All Cloud Applications |
| Client App Types | All Client App Types |
| User Scope | Includes: All Users · Excludes: Break-glass account(s), Directory Readers role |
| Access Control | Require Compliant Device |

### UserCompute - Conditional Access Policy

| Setting | Value |
|---|---|
| Enforcement State | Report-Only (Not Enforced) |
| Target Applications | All Cloud Applications |
| Client App Types | Exchange ActiveSync, Other Legacy Clients |
| User Scope | Includes: Specific Security Group(s) · Excludes: Break-glass account(s) |
| Platforms | All |
| Locations | All |
| Access Control | Require Approved Client App OR Authentication Strength: Multifactor authentication |

### Require multifactor authentication for all users

| Setting | Value |
|---|---|
| Enforcement State | Report-Only (Not Enforced) |
| Target Applications | All Cloud Applications |
| Client App Types | All Client App Types |
| User Scope | Includes: All Users · Excludes: Break-glass account(s), Directory Readers role |
| Access Control | Require MFA |

### Require MFA for Microsoft admin portals

| Setting | Value |
|---|---|
| Enforcement State | Report-Only (Not Enforced) |
| Target Applications | Microsoft Admin Portals |
| Client App Types | All Client App Types |
| User Scope | Includes: All Users · Excludes: Break-glass account(s), Directory Readers role |
| Access Control | Require MFA (via Authentication Strength) |

### Block legacy authentication

| Setting | Value |
|---|---|
| Enforcement State | Report-Only (Not Enforced) |
| Target Applications | All Cloud Applications |
| Client App Types | Exchange ActiveSync, Other Legacy Clients |
| User Scope | Includes: All Users · Excludes: Break-glass account(s), Directory Readers role |
| Access Control | Block Access |

### Require MFA for guest access

| Setting | Value |
|---|---|
| Enforcement State | Report-Only (Not Enforced) |
| Target Applications | All Cloud Applications |
| Client App Types | All Client App Types |
| User Scope | Includes: Guest / External Users · Excludes: Break-glass account(s) |
| Access Control | Require MFA |

### Require compliant/hybrid joined device or MFA for all users

| Setting | Value |
|---|---|
| Enforcement State | Report-Only (Not Enforced) |
| Target Applications | All Cloud Applications |
| Client App Types | All Client App Types |
| User Scope | Includes: All Users · Excludes: Break-glass account(s), Directory Readers role |
| Access Control | Require MFA OR Require Compliant Device OR Require Hybrid Azure AD Joined Device |

### Require MFA for Azure management

| Setting | Value |
|---|---|
| Enforcement State | Report-Only (Not Enforced) |
| Target Applications | Azure Management |
| Client App Types | All Client App Types |
| User Scope | Includes: All Users · Excludes: Break-glass account(s), Directory Readers role |
| Access Control | Require MFA |

### Require approved client apps or app protection policies

| Setting | Value |
|---|---|
| Enforcement State | Report-Only (Not Enforced) |
| Target Applications | Office 365 |
| Client App Types | All Client App Types |
| User Scope | Includes: All Users · Excludes: Break-glass account(s), Guest / External Users |
| Platforms | Android, iOS |
| Access Control | Require Approved Client App OR Require App Protection Policy |

### Block access for unknown or unsupported device platform

| Setting | Value |
|---|---|
| Enforcement State | Report-Only (Not Enforced) |
| Target Applications | All Cloud Applications |
| Client App Types | All Client App Types |
| User Scope | Includes: All Users · Excludes: Break-glass account(s), Directory Readers role |
| Platforms | Includes: All · Excludes: Android, iOS, Windows, macOS, Linux |
| Access Control | Block Access |

### Require MFA for admins (template)

| Setting | Value |
|---|---|
| Enforcement State | Report-Only (Not Enforced) |
| Target Applications | All Cloud Applications |
| Client App Types | All Client App Types |
| User Scope | Includes: 14 Admin Roles · Excludes: Break-glass account(s), Directory Readers role |
| Access Control | Require MFA |

---

## Risks and Considerations

- Several policies are currently in **Report-Only mode** and are not actively enforcing controls. These should be reviewed and transitioned to Enforced state after validation.
- A **break-glass (emergency access) account** is excluded from all policies. This account must be secured with strong credentials, monitored, and its usage audited regularly.
- The **legacy authentication block** policy is in Report-Only mode. Until enforced, legacy protocols remain a potential attack vector.
- The **compliant device requirement** policy is not yet enforced. Users may currently access cloud resources from non-compliant or unmanaged devices.
