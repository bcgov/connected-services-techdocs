---
title: Overview
---

# Overview

## At a glance

**On this page:** The activities involved in publishing a service through P2P, from preparing your API to enabling consumer access.

**When to use it:** When planning to publish a service or finding guidance for your next activity.

**Who is involved:** Provider organization representatives, System Admins, Tech Leads, Access Managers and P2P operators.

## Publishing through P2P

Publishing your organization's API through peer-to-peer (P2P) data exchange
allows authorized consumers to discover it and request access. Your organization
must complete P2P onboarding before publishing, but your team can prepare
the API alongside onboarding.

The API Program Services (APS) team guides initial onboarding. Team members
acting as P2P operators perform the organization setup and help your team
identify its next steps.

Review [P2P roles and responsibilities](../sdx-roles-and-responsibilities.md)
to understand who needs to be involved.

## Activities and guidance

Use this table to understand the publishing activities and find guidance for
each one. If your organization has already completed some activities, work
with your P2P operator to confirm what remains.

| Activity | What's involved | Guidance |
|---|---|---|
| **Prepare your API** | Design and build your API using the API standard, validation rules and available testing tools | [Prepare your API](prepare-your-api.md) |
| **Onboard your organization** | Request a kickoff meeting to discuss organization representation, administrator access and hosting. The P2P operator performs the initial organization setup | [Onboarding an organization](../setup-and-management/onboarding-an-organization.md) |
| **Set up an Edge Runtime Group** | Learn about the hosting options and discuss the choice with APS. Work with a P2P operator for community hosting, or install a client-hosted Edge Runtime Group | [Install an Edge Runtime Group](../setup-and-management/install-an-edge-runtime-group.md) |
| **Set up organization signing (optional)** | Discuss applicable signing requirements with APS and, if needed, configure organization signing | [Set up organization signing](../setup-and-management/set-up-organization-signing.md) |
| **Register your subsystem** | Your System Admin registers the subsystem, assigns its runtime group and sets up team access. Discuss the privacy zone with Identity Assurance Services before recording it | [Managing subsystems](../setup-and-management/managing-subsystems.md) |
| **Register your service** | Register your API using an OpenAPI specification that meets the validation requirements, along with the target environment and upstream URL. Registration also adds the service to the SDX Catalogue | [Managing services](../setup-and-management/managing-services.md) |
| **Enable consumer access** | Your Access Manager reviews requests and coordinates discussions with the relevant provider and consumer team members. Approved requests proceed through connection provisioning | [Connecting a service](../setup-and-management/connecting-a-service.md) |

Throughout this process, P2P applies encryption, authentication, policy
enforcement and audit logging.

## Next steps

- [Prepare your API](prepare-your-api.md): Review the API preparation guidance.
- [Organization onboarding overview](../setup-and-management/organization-onboarding-overview.md): Understand the onboarding stages and who is involved.

## Get help

Use your onboarding ticket to ask questions and coordinate next steps with APS.
For ongoing assistance, see [Support](../../support.md).
