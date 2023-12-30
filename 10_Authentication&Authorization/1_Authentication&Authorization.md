# Authentication and Authorization in Linux

<br>

## Introduction

In this guide, we delve into the roles of authentication and authorization in Linux, highlighting their importance in resource access control.

<br>

## Understanding Authentication in Linux

**Concept of Authentication**:

- Authentication is the proof of identity.
- Methods include:
  - Local user accounts in `/etc/passwd`.
  - Centralized LDAP-based or cloud-based accounts.

**Forms of Authentication**:

- **Single-factor Authentication**: Involves something you know, like a username and password.
- **Multi-factor Authentication (MFA)**:
  - Combines different factors:
    - Something you know (e.g., password, PIN).
    - Something you have (e.g., key fob, smart card).
    - Something you are (e.g., biometrics like facial recognition).
  - Utilizes public key infrastructure (PKI) certificates.
  - In cloud environments, like Microsoft Azure, authentication is centralized with Azure AD.

**MFA in Azure AD**:

- Azure AD MFA user settings manage the authentication status.
- MFA status categories:
  - **Disabled**: MFA not active.
  - **Enabled**: MFA activated but not yet completed by the user.
  - **Enforced**: MFA fully configured and operational.

<br>

## Understanding Authorization in Linux

**Concept of Authorization**:

- Authorization determines access to resources.
- Methods include file permissions using `chmod` and other system-level permissions.
- It extends to various levels like email access, VPN usage, and web app access.

<br>

### Linux Pluggable Authentication Modules (PAM)

- **Purpose of PAM**:
  - Separates authentication from application-level tasks.
  - Enables external authentication, such as Azure AD or standard Linux mechanisms.

- **Configuration**:
  - Indirectly configured by Linux technicians.
  - Affects files in `/etc/pam.d`, influencing SSH authentication and more.

<br>

## Conclusion

This guide covers the critical aspects of authentication and authorization in Linux, focusing on how these mechanisms ensure secure access to resources. Understanding and implementing these concepts are crucial for maintaining a robust and secure Linux environment.
