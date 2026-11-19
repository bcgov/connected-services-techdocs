---
title: Organization onboarding overview
---

# Organization onboarding overview

## At a glance

**On this page:** How provider and consumer onboarding starts, what organization setup includes and what happens next.

**When to use it:** When your organization needs to join P2P to publish or consume services.

**Who is involved:** Organization representatives, CSS integration requesters, P2P operators, Organization Admins and System Admins.

## How onboarding works

Before your organization can publish or consume services through peer-to-peer
(P2P) data exchange, it must be onboarded. Onboarding registers your organization
in P2P and establishes administrator access to manage its systems and services.

Providers and consumers enter onboarding differently, but share the initial
organization setup.

```mermaid
flowchart TD
    A["Provider: requests a kickoff through JSM"] --> D["Onboarding discussion with a P2P operator"]
    B["Consumer: CSS request identifies P2P setup is needed"] --> C["P2P operator opens a JSM ticket and arranges a kickoff"]
    C --> D
    D --> E["Operator registers the organization and assigns initial administrator access"]
    E --> F["Operator enables community hosting, if selected"]
    F --> G["Operator updates the JSM ticket, includes the relevant administrators and provides next steps"]
    G --> H["Continue with provider or consumer setup"]
    classDef default fill:#D8EAFD,stroke:#013366,color:#2D2D2D,stroke-width:2px;
    linkStyle default stroke:#013366,stroke-width:2px,color:#2D2D2D;
```

*Provider and consumer onboarding paths*

!!! note "Guided organization setup"
    The API Program Services (APS) team operates P2P. A P2P operator works
    with your organization and performs the initial organization setup
    and administrator assignments.

The APS team uses Jira Service Management (JSM), its support ticketing system,
to track onboarding activities and communicate with your team.

## How to get started

| Your organization's purpose | How onboarding starts |
|---|---|
| **Provide a service** | An organization representative requests an onboarding kickoff meeting through the [Support Portal](https://dpdd.atlassian.net/servicedesk/customer/portal/1/group/2/create/665). The Data Management & Interoperability (DMI) team may provide this link when referring your organization to APS |
| **Consume a service** | A Common Hosted Single Sign-on (CSS) integration request identifies that P2P organization setup is needed. A P2P operator is notified, opens a JSM ticket on behalf of the CSS integration requester and arranges an onboarding kickoff meeting. |

## What to expect

The P2P operator works with your organization's representatives to confirm legal
representation, identify System Admins and discuss community-hosted or
client-hosted Edge Runtime Group options.

Organization onboarding includes:

| Activity | What's involved |
|---|---|
| **Register the organization** | The P2P operator creates the organization in P2P |
| **Assign initial administrator access** | The operator assigns the organization's legal representative the initial Organization Admin role and sets up System Admin access |
| **Enable community hosting, if selected** | The operator grants the organization permission to use a community-hosted Edge Runtime Group |

The JSM conversation depends on how onboarding started:

- **Providers:** The operator works with the organization representative who initiated the request and brings the designated System Admins into the JSM conversation as needed.
- **Consumers:** The operator initially works with the CSS integration requester, then brings the Organization Admin and System Admins into the JSM conversation as they are identified.

The operator updates the JSM ticket with completed activities and next steps.
People new to the support environment may receive an email asking them to
set up an account.

Review [P2P roles and responsibilities](../sdx-roles-and-responsibilities.md)
to understand each role. Review the [environments](../environments.md)
when planning your setup.

## After organization onboarding

Your organization is registered and its designated administrators have access.

If your organization selected a client-hosted Edge Runtime Group, your team
sets it up next. For community hosting, the P2P operator enables access during
organization onboarding.

The System Admin then completes organization signing setup, if applicable,
and registers the subsystem. Subsystem setup includes different activities
for providers and consumers:

- **Providers:** The System Admin discusses the subsystem's privacy zone with the Identity Assurance Services (IAS) Access Manager, then records the agreed privacy zone in P2P.
- **Consumers:** The System Admin links the subsystem to the CSS integration and confirms completion through the JSM ticket. The P2P operator can then resume the held integration access request.

Organization onboarding alone does not grant access to another organization's
service.

## Next steps

- [Onboarding an organization](onboarding-an-organization.md): Review the onboarding responsibilities and organization setup instructions.
- [Publish a service](../publish-a-service/overview.md): Review the remaining provider activities.
- [Consume a service](../consume-a-service/overview.md): Review the remaining consumer activities.

## Get help

Use your JSM ticket to ask questions and coordinate onboarding with APS.
For ongoing assistance, see [Support](../../support.md).