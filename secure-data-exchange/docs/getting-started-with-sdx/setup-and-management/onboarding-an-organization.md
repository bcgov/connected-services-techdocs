---
title: Onboarding an organization
---

# Onboarding an organization

## At a glance

**On this page:** The provider kickoff and initial setup process, followed by technical reference for setting up and managing an organization.

**When to use it:** When arranging provider onboarding or performing organization setup and administration.

**Who is involved:** Organization representatives, P2P operators, Organization Admins and System Admins.

## Initial organization setup

Organization onboarding establishes your organization in peer-to-peer (P2P)
data exchange and assigns the administrator access needed to manage its
systems and services.

!!! note "Initial setup is guided"
    The P2P operator performs the initial organization setup and administrator
    assignments in discussion with your organization. Organization
    representatives do not need to run the setup commands.

The API Program Services (APS) team uses Jira Service Management (JSM),
its support ticketing system, to track onboarding activities and communicate
with your team.

## Provider onboarding kickoff

The following diagram and kickoff guidance describe the provider entry route.
Consumer onboarding starts through a Common Hosted Single Sign-on (CSS)
integration request. See the
[Organization onboarding overview](organization-onboarding-overview.md)
for the different entry routes.

```mermaid
flowchart TD
    A["Organization representative requests a kickoff through JSM"] --> B["Discuss setup with a P2P operator"]
    B --> C["Identify organization representation and System Admins"]
    C --> D["Discuss Edge Runtime Group hosting"]
    D --> E["P2P operator completes organization setup"]
    E --> F["Operator updates the ticket and adds System Admins"]
    F --> G["System Admins follow the next setup instructions"]
    classDef default fill:#D8EAFD,stroke:#013366,color:#2D2D2D,stroke-width:2px;
    linkStyle default stroke:#013366,stroke-width:2px,color:#2D2D2D;
```

*Provider onboarding kickoff and initial setup*

### Request a provider onboarding kickoff meeting

Use the [Support Portal](https://dpdd.atlassian.net/servicedesk/customer/portal/1/group/2/create/665)
to request a P2P onboarding kickoff meeting. A P2P operator from the APS team
contacts you to arrange the session.

If the Data Management & Interoperability (DMI) team is supporting your
organization, they may provide this link as part of the handoff to APS.

Your initial contact may be an organization representative or product owner.
They do not need an assigned P2P administrator role to request the meeting.

### Discuss your organization's setup

The kickoff establishes who represents your organization, who will administer
its systems and which hosting option it will use.

| Discussion topic | What's involved |
|---|---|
| **Organization representation** | Identify the person authorized to represent your organization |
| **System administrators** | Identify the people who need System Admin access |
| **Technical capability** | Identify someone who can perform the technical setup activities that follow |
| **Edge Runtime Group hosting** | Discuss community-hosted and client-hosted options |

At least one System Admin needs the technical knowledge to perform the setup
activities that follow. Some activities require command line tools.

See [Install an Edge Runtime Group](install-an-edge-runtime-group.md)
for the hosting options.

### What the P2P operator sets up

| Activity | What's involved |
|---|---|
| **Register the organization** | Create the organization in P2P |
| **Assign initial administrator access** | Assign the organization's legal representative the initial Organization Admin role and set up System Admin access |
| **Enable community hosting, if selected** | Grant the organization permission to use a community-hosted Edge Runtime Group |

The operator updates the JSM ticket to confirm what has been set up, record
the hosting decision and provide next-step instructions. They also bring
the designated System Admins into the ticket conversation.

## Technical reference

The following sections are for P2P operators, Organization Admins and
System Admins performing organization setup and administration.

During initial onboarding, the P2P operator performs the organization setup
and initial administrator assignments. The role permissions below also
support subsequent administration.

| Role | Function |
|---|---|
| P2P operator | Establish member organizations and assign legal representatives Org Admin role |
| Organization Admin | Manage System Admin role assignment for the organization |
| System Admin | Manage subsystem onboarding for the particular organization |

Use cases:

- Register new organization
- System Admin role assignment
- List organizations
- Assign gateway for organization

### Register new organization

This is performed by the P2P operator to onboard a new organization.

=== "Restish CLI"

    Help information about the organization creation/update operation:

    ```sh
    restish aps put-organization
    ```

    Example:

    ```sh
    echo '
    {
      "name": "my-org",
      "title": "My Org",
      "description": "It is an organization for me",
      "extSource": "custom",
      "extRecordHash": "0000",
      "tags": [
        "member_class:MIN", "member_id:MYORG"
      ],
      "orgUnits": []
    }
    ' | restish aps put-organization ca.bc.gov
    ```

=== "Reference"

    - **API** `PUT /organizations/{org}`

    Parameters: `{org}=ca.bc.gov`

    ```json
    {
      "name": "ministry-of-food",
      "title": "Ministry of Food",
      "description": "It is a ministry concerned with food",
      "extSource": "custom",
      "extRecordHash": "0000",
      "tags": [
        "member_class:MIN",
        "member_id:FOOD"
      ],
      "publicBodyId": null,
      "orgUnits": []
    }
    ```

    `tags` is `array<string>`. An array containing an object is rejected by
    the live request schema.

### System Admin role assignment

This is performed by the Organization Admin to assign system
administrators access to manage their systems.

The organization-scoped role that grants this access is `system-admin`, which
carries permission `System.Manage` for the organization. This is distinct from any
system-level roles and from `organization-admin`, which carries
`GroupAccess.Manage`, `Namespace.Assign`, and `Dataset.Manage` instead.

=== "Restish CLI"

    Help information about the organization role membership synchronization operation:

    ```sh
    restish aps put-organization-access
    ```

    Example:

    ```sh
    echo '
    {
      "name": "my-org",
      "parent": "/ca.bc.gov",
      "members": [
        {
          "member": {
            "email": "aidan.cope@gov.bc.ca"
          },
          "roles": ["system-admin"]
        }
      ]
    }
    ' | restish aps put-organization-access ca.bc.gov
    ```

=== "Reference"

    - API `PUT /organizations/{org}/access`

    Parameters: `{org}=ministry-of-food`

    ```json
    {
      "name": "ministry-of-food",
      "parent": "/ca.bc.gov",
      "members": [
        {
          "member": {
            "email": "janis@testmail.com"
          },
          "roles": ["system-admin"]
        }
      ]
    }
    ```

### List organizations

Retrieve the list of organizations available in the SDX Catalogue.

=== "Restish CLI"

    ```sh
    restish sdx organization-list
    ```

=== "Reference"

    - **API** `GET /catalog/organizations`

    ```json title="Response Body"
    [
      {
        "name": "ministry-of-food",
        "title": "Ministry of Food",
        "description": "It is a ministry concerned with food",
        "member": {
          "memberClass": "MIN",
          "memberId": "FOOD"
        }
      }
    ]
    ```

### Get organization details

Retrieve the details of an organization available in the SDX Catalogue,
optionally including the organization's role-based access control (RBAC)
role membership.

=== "Restish CLI"

    Help information about the operation:

    ```sh
    restish sdx organization-get
    ```

    Example call:

    ```sh
    restish sdx organization-get my-org
    ```

    Include role membership:

    ```sh
    restish sdx organization-get my-org --include-access
    ```

<!-- prettier-ignore -->
!!! note "`includeAccess` does not require authentication"
    `organization-get` has always been callable without a bearer token, and
    `includeAccess` does not change that: role membership is resolved using
    the platform's own Keycloak service credentials, not the caller's - so
    passing `includeAccess=true` returns the organization's role members
    to anonymous callers, the same way the base listing already returns
    every organization's name/title/member details to anonymous callers.

### Assign gateway for organization

An organization will have public keys that it will use for organization signing
of traffic through P2P. Each organization is assigned a unique gateway where
the public keys are managed.

=== "Restish CLI"

    Help information about the operation to assign a runtime group:

    ```sh
    restish sdx register-organization-gateway
    ```

    Example:

    ```sh
    restish sdx register-organization-gateway \
      my-org
    ```

## Next steps

Your System Admin follows the instructions provided through the onboarding ticket.

- [Install an Edge Runtime Group](install-an-edge-runtime-group.md): Set up a client-hosted Edge Runtime Group, if selected.
- [Set up organization signing](set-up-organization-signing.md): Complete organization signing setup, if applicable.
- [Managing subsystems](managing-subsystems.md): Register a subsystem and complete the applicable provider or consumer setup.

Use your JSM ticket to ask questions and clarify which activities apply to
your organization. Return to [Publish a service](../publish-a-service/overview.md)
for the full provider journey.