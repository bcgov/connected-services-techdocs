---
title: Secure Data Exchange (P2P)
---
# Building trusted digital services

## Secure Data Exchange (P2P)

### What it is

_Secure Data Exchange_ (P2P) helps organizations safely share sensitive information with each other.

It protects information as it moves from one organization to another and ensures that only approved systems can send and receive it.

P2P protects exchanges by:

- Encrypting information while it is being exchanged
- Confirming that participating systems are approved
- Checking that information has not been changed in transit
- Applying rules that control access and permitted actions
- Keeping records of exchanges for auditing and review
- Recording who participated in an exchange when it happened

Together, these controls help organizations protect sensitive information and support B.C.'s security, privacy, and regulatory requirements.

### Who should use P2P

P2P is for organizations participating in Connected Services that need to share sensitive information with other organizations.

Participants may include B.C. government ministries and partner organizations such as LTSA and ICBC.

An organization can:

- Provide information or services to other approved organizations
- Consume information or services provided by another organization
- Do both

### When you should use P2P

Use P2P when information needs to be shared between organizations and the exchange needs stronger security, access control, or accountability.

P2P may be appropriate when:

- Personal, financial, or other sensitive information is being shared
- Access must be limited to approved organizations or systems
- The exchange must be logged or available for audit
- There must be a reliable record of who participated in the exchange

P2P is generally not needed for public or non-sensitive information that does not require these additional controls.

### How it works

Organizations complete the P2P onboarding process before exchanging information. Onboarding sets up the organization, its systems, roles, and secure connections.

Once onboarded:

- Providers make services available to approved consumers. API providers register their APIs using an OpenAPI Specification (OAS).
- Consumers request access to the services they need.
- P2P applies security, access, and logging controls to exchanges between participating systems.

P2P Edge Servers provide the secure connection used by participating organizations.

For more details including setup instructions, see [Getting started with P2P documentation](/docs/default/component/secure-data-exchange-techdocs/).

### Privacy and security responsibilities

P2P provides technical controls that help organizations meet privacy and security requirements.

Using P2P does not replace an organization's responsibility to meet its own privacy, security, governance, and data management requirements.

See [Privacy and security](privacy-and-security.md) for more information about organizational responsibilities and accountability.

### Where to go next
- [Getting started with P2P documentation](/docs/default/component/secure-data-exchange-techdocs/)
- Or go directly to [P2P onboarding documentation](/docs/default/component/aps-infra-platform-docs/how-to/P2P-org-onboarding/)
