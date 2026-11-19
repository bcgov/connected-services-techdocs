---
title: Prepare your API
---

# Prepare your API

## At a glance

**On this page:** Resources to help providers design, validate and test an API for P2P.

**When to use it:** During provider API development, before registering your service.

**Who is involved:** API developers and Tech Leads preparing an API that their organization will provide to consumers through P2P.

## Preparing for P2P

This guidance is for teams preparing an API that other organizations will
access through peer-to-peer (P2P) data exchange. Your team writes the OpenAPI
specification and builds the API.

You can begin preparing your API before your organization is onboarded to P2P.
API development and organization onboarding can happen alongside each other.

If your team is connecting an application to another organization's API listed
in the SDX Catalogue, follow [Consume a service](../consume-a-service/overview.md).

## API preparation resources

API style guides help teams write consistent OpenAPI specifications and check
them using automated rules. For APIs provided through P2P, the SDX API Standard
defines the requirements, and the SDX API Standard Ruleset provides the
automated validation rules.

| Resource | What it helps you understand or do | When to use it |
|---|---|---|
| [API style guides](/docs/default/component/api-style-guides) | Understand the available guides and how their rules help teams write consistent, valid OpenAPI specifications | Before using the P2P-specific standard and ruleset |
| [SDX API Standard](docs/default/component/sdx-api-standards-techdocs) | Understand the requirements your API and OpenAPI specification must meet to be published through P2P | When designing your API and specification |
| [SDX API Standard Ruleset](/docs/default/component/api-style-guides/sdx-style-guide/) | Understand the automated validation rules and use examples to resolve issues | When writing and validating your specification |
| P2P emulator: [Request access](https://api.gov.bc.ca/devportal/api-directory/4443) · [Development app](https://sdx-p2p-emu-api-gov-bc-ca.dev.api.gov.bc.ca/) | Generate sample tokens and headers to use when testing your provider API. Development is ongoing, with additional functionality scheduled before the end of 2026 | During development and testing |

The standard and ruleset are maintained separately from this onboarding
guidance. Their current titles use SDX.

### Apply the API standard

Review the SDX API Standard when designing your API. It defines requirements
for the OpenAPI specification, supported features and security declarations.

If your API must meet additional program or data standards, confirm those
requirements with the responsible team early in development.

### Validate your specification

Use the SDX API Standard Ruleset to understand the rules used to validate your
OpenAPI specification. It provides explanations and examples of valid and
invalid patterns.

Your specification must pass validation with zero errors. Warnings identify
improvements but do not prevent provisioning.

### Test with the P2P emulator

The P2P emulator generates sample subject tokens, Edge Runtime tokens and
request headers. Your team uses these when calling its test API.

Use synthetic identities and test data. Confirm signing-key trust and setup
requirements with your P2P operator before testing.

Development is ongoing. Contact the APS team to confirm which emulator
features are available for your testing needs.

## Next steps

- [Organization onboarding overview](../setup-and-management/onboarding-process.md): If your organization has not started onboarding, review the stages and who needs to be involved.
- [Managing services](../setup-and-management/managing-services.md): When the required setup is complete and your API is ready, follow the guidance to register your service.
- [Publish a service overview](overview.md): Return to the full provider journey.