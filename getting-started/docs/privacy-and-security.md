---
title: Privacy and security
---
# Building trusted digital services

## Privacy and security

Secure Data Exchange (SDX) provides the secure, policy-driven trust foundation for data exchange that crosses privacy zones between organizations or that involves private information. For data exchange that doesn't meet that bar, the API Services Portal may be the right path instead. See [API Services Portal](api-services-portal.md) for its approach to access and security.

This page describes the privacy and security model that applies when SDX is used.

SDX does not centralize or store program data. Data remains with the ministry or public body that owns it. Instead, it enables secure, auditable exchange between trusted systems.

Privacy and security controls are embedded into the technical design, not added afterward.

### Secure exchange by design

When data exchange crosses privacy zones between organizations or involves private information, it goes through Secure Data Exchange (SDX). SDX enforces these controls:

- Authentication of participating systems
- Verification that requests are unaltered
- Real-time access control
- Timestamped logging of transactions

These controls ensure that only authorized, policy-compliant requests are fulfilled.

For technical details on how SDX implements these controls, including request verification and Edge Server architecture, see [Secure Data Exchange (SDX)](secure-data-exchange.md).

### Data ownership and control

SDX does not take ownership of ministry or public body data, such as ICBC data.

- Ministries and public bodies remain custodians of their data
- Access decisions are enforced based on predefined policies
- Data is exchanged directly between approved participants
- No centralized data repository is created

This model supports working across systems while preserving program accountability.

### Identity and access enforcement

Access is controlled at request time using short-lived, scoped tokens.

Each request must meet these conditions:

- Be authenticated
- Meet defined access policies
- Be validated before any data is exchanged

Access enforcement is automated and consistent across participants.

### Logging, audit, and transparency

All transactions are logged automatically.

- Requests are timestamped
- Actions are auditable
- Records support compliance and oversight
- Logging enables accountability without exposing underlying data

This design supports transparency while minimizing data exposure.

### Scaling securely

As more capabilities and partners are added over time, the same trust and security foundation applies.

- New partners onboard under shared trust rules
- Policies are enforced consistently
- Security controls do not need to be rebuilt for each integration

This helps this work grow securely across ministries.

### How decisions are defined

Privacy and security controls enforce rules, but those rules are established through governance and policy direction.

Oversight, accountability, and decision-making structures shape how these building blocks are governed. Review [Governance and policy](governance-and-policy.md) to learn more.
