---
title: Install an Edge Runtime Group
---

An edge runtime group provides the infrastructure your organization uses to connect systems to the SDX ecosystem. Organizations can either deploy a client-hosted runtime group in their own infrastructure or use a community-hosted runtime group provided through the SDX platform. This guide provides the technical steps for setting up a client-hosted runtime group, including registering the runtime group, configuring its gateway, deploying the required infrastructure, and completing verification. Organizations using a community-hosted runtime group should contact the APS team for guidance. This process is performed by the System Admin.

!!! note "Alternative names"

    SDX Edge Runtime Group is also referred to as “*Edge Runtime*”, “*Edge Runtime Group*”, or “*Runtime Group*”.

### Edge Runtime Group Hosting Options

Organizations can connect to Secure Data Exchange (SDX) using either a **community-hosted** or **client-hosted** Edge Runtime Group. Both options provide a secure connection to SDX, but differ in how the infrastructure is hosted and managed.

**Community-Hosted Runtime Group**

A community-hosted runtime group uses shared infrastructure provided through the SDX platform, reducing the need for organizations to deploy and maintain their own infrastructure.

- Infrastructure is hosted and managed through the SDX platform.
- Organizations do not need to deploy their own Edge Runtime Group.
- This option may be suitable for organizations that do not have the resources or infrastructure to host their own runtime group.
- Organizations interested in this option should contact the APS team to discuss availability and onboarding requirements.

**Client-Hosted Runtime Group**

A client-hosted runtime group is deployed and managed within an organization's own infrastructure, providing greater control over its configuration and operation.

- Infrastructure is hosted and managed by the organization.
- The organization's System Admin is responsible for coordinating the installation and configuration.
- This option may be suitable for organizations that have their own infrastructure and technical resources to manage it.
- Organizations choosing this option should follow the [Install an Edge Runtime Group] technical guide to complete setup and verification.

Both options support secure communication through SDX. The appropriate hosting option will depend on your organization's infrastructure, technical capabilities, and onboarding requirements.

Good to know: Some consumer organizations can use the shared Public Consumer Gateway (PZGW) instead of running their own public-facing Edge Runtime Group. This does not replace the provider’s runtime group; providers still need their own runtime group.

Technical guide: [Install an Edge Runtime Group](https://developer.gov.bc.ca/docs/default/component/aps-infra-platform-docs/how-to/sdx-edge-runtime-groups/)
