---
title: Overview
---

# Overview

## At a glance

**On this page:** The activities involved in accessing a provider's service through P2P, including requesting access, completing setup and preparing to use the service.

**When to use it:** When your organization wants to connect an application to another organization's API through P2P.

**Who is involved:** Consumer organization representatives, CSS integration requesters, System Admins, Subsystem Owners, Tech Leads, P2P operators and provider Access Managers.

## Consuming a service through P2P

Peer-to-peer (P2P) data exchange lets your application securely access services
that other organizations have made available through P2P. Both the consumer
and provider organizations must be onboarded to P2P before exchanging data.

Start by identifying a provider and discussing the data you need and the
available access method. The provider may share its service details in the
SDX Catalogue or give you the scope information needed to request access
through Common Hosted Single Sign-on (CSS).

Your organization must complete P2P onboarding before consuming a service.
You can submit your CSS access request before that setup is complete.
If P2P organization setup is required, your request is held while a P2P
operator guides your organization through onboarding.

Review [P2P roles and responsibilities](../sdx-roles-and-responsibilities.md)
to understand who needs to be involved.

!!! note "Service naming in CSS"
    CSS uses **SDX** in its interface. In this guidance, SDX and P2P refer
    to the same service.

## Activities and guidance

Use this table to understand the main activities and find the related guidance.
If your organization is already onboarded, the P2P operator can help confirm
which setup activities remain.

| Activity | What's involved | Guidance |
|---|---|---|
| **Identify a service and discuss access** | Discuss your data needs with the provider. Confirm that access is available through P2P and identify the service and scopes your application needs | Service information supplied by the provider or listed in the SDX Catalogue |
| **Request access through CSS** | The CSS integration requester selects the service scopes needed by the application and submits the request. A request requiring P2P organization setup is held until that setup is complete | [Connecting a service](../setup-and-management/connecting-a-service.md) |
| **Complete organization onboarding, if needed** | The P2P operator coordinates onboarding through a JSM ticket, confirms organization representation and hosting arrangements, and sets up the organization and initial administrator access | [Organization onboarding overview](../setup-and-management/onboarding-process.md) |
| **Set up an Edge Runtime Group** | Learn about the hosting options and discuss the choice with the P2P operator. Work with the operator for community hosting, or install a client-hosted Edge Runtime Group | [Install an Edge Runtime Group](../setup-and-management/install-an-edge-runtime-group.md) |
| **Set up organization signing (optional)** | Discuss applicable signing requirements with the P2P operator. If needed, your System Admin configures organization signing | [Set up organization signing](../setup-and-management/set-up-organization-signing.md) |
| **Register and link your subsystem** | The System Admin registers the consumer subsystem, assigns its runtime group, arranges team access and links it to the CSS integration. They confirm completion through the JSM ticket so the operator can resume the held request | [Managing subsystems](../setup-and-management/managing-subsystems.md) |
| **Discuss access with the provider** | The provider Access Manager reviews the request and discusses it with the consumer Subsystem Owner and Tech Lead before approving or rejecting it | [Connecting a service](../setup-and-management/connecting-a-service.md) |
| **Confirm access and test your application** | Following approval, P2P and CSS provision access. Confirm that provisioning has succeeded before using the service to develop and test your application | [Connecting a service](../setup-and-management/connecting-a-service.md) |

When selecting access and planning setup, review the
[environments](../environments.md). Your application's environments and
the provider's non-prod or prod data access are separate considerations.

P2P applies security, authentication and governance controls to exchanges
made through the platform.

## Next steps

- **If you have identified a provider:** Review [Connecting a service](../setup-and-management/connecting-a-service.md) for access-request guidance.
- **If your request is held for P2P organization setup:** Work with your P2P operator and review the [Organization onboarding overview](../setup-and-management/onboarding-process.md).

## Get help

Use your onboarding JSM ticket to ask questions, confirm completed setup
and coordinate next steps with the P2P operator. For ongoing assistance,
see [Support](../../support.md).