# Device Compliance Policies

## Purpose

Compliance policies define the minimum security requirements a device must meet to be considered healthy and allowed access to corporate resources. Non-compliant devices can be blocked from accessing email, files, and other cloud services when combined with Conditional Access.

---

## UserCompute - Win 11 Compliance Policy

**Purpose:** Defines what makes a device compliant (healthy and secure).

| Setting | Value |
|---|---|
| Platform | Windows 10/11 |
| Password Required | Enabled |
| Minimum Password Length | 8 characters |
| Password Type | Alphanumeric |
| Block Simple Passwords | Enabled |
| Password Expiration | 60 days |
| Inactivity Lock | 15 minutes |
| BitLocker Encryption | Enabled |
| Secure Boot | Enabled |
| Code Integrity | Enabled |
| Storage Encryption Required | Enabled |

---

## Default Compliance Policy for Android

| Setting | Value |
|---|---|
| Platform | Android |
| Password Required | Disabled |
| Block Jailbroken/Rooted Devices | Enabled |
| Device Threat Protection | Disabled |
| Storage Encryption Required | Disabled |
| Require Google Play Services | Disabled |
| Block Unknown Sources | Disabled |

---

## UserCompute - VM Compliance Policy

| Setting | Value |
|---|---|
| Platform | Windows 10/11 |
| Password Required | Enabled |
| Minimum Password Length | 8 characters |
| Password Type | Alphanumeric |
| Block Simple Passwords | Enabled |
| Password Expiration | 60 days |
| Inactivity Lock | 15 minutes |
| BitLocker Encryption | Disabled |
| Secure Boot | Disabled |
| Code Integrity | Enabled |
| Storage Encryption Required | Disabled |

---

## Risks and Considerations

- The **default Android compliance policy** has minimal security enforcement. Password is not required and most security checks are disabled. This should be reviewed if Android devices access corporate data.
- The **VM Compliance Policy** does not require BitLocker or Secure Boot. While acceptable for virtual machines, ensure this policy is not inadvertently applied to physical endpoints.
- Password expiration is set to **60 days** for Windows policies. NIST SP 800-63B recommends against periodic password changes unless there is evidence of compromise. Consider aligning with current best practice.
