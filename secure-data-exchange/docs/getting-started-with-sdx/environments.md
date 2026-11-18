---
title: Environments
---

# Environments

## At a glance

**On this page:** The P2P environments, what to expect from each and the technical details needed to use them.

**When to use it:** When planning setup, testing or production use, or checking environment-specific settings.

**Who is involved:** Service providers and consumers, System Admins, Tech Leads and runtime group operators.

## Available environments

P2P provides separate environments for learning, setup, and production use.

- **Playground:** Use the Playground to validate an installation and test new functionality before moving to Production. It does not provide data or service-quality guarantees.
- **Production:** Use Production for Test Data and Production Data P2P instances. The data and service quality are the same for both instances.

| Environment | Purpose | What to expect |
|---|---|---|
| Playground | Installation and testing | No data or service-quality guarantee |
| Production | Test Data and Production Data | Production-level data and service quality |

The Production environment also supports a `Staging` environment for runtime
group operators to stage infrastructure changes.

## Useful links

Links to the different services for each environment:

| Service | Playground | Production |
|---|---|---|
| SDX UI | [UI](https://sdx-api-gov-bc-ca.test.api.gov.bc.ca) | [UI](https://sdx.gov.bc.ca) |
| P2P Member API | [API](https://api-gov-bc-ca.test.api.gov.bc.ca/ds/api/sdx/v1/console) | [API](https://api.gov.bc.ca/ds/api/sdx/v1/console) |
| OpenAPI Specification | [OpenAPI](https://api-gov-bc-ca.test.api.gov.bc.ca/ds/api/sdx/v1/openapi.yaml) | [OpenAPI](https://api.gov.bc.ca/ds/api/sdx/v1/openapi.yaml) |
| API Services Portal | [APS Portal](https://api-gov-bc-ca.test.api.gov.bc.ca/login?identity=provider) | [APS Portal](https://api.gov.bc.ca/login?identity=provider) |
| Common SSO | [Common SSO](https://sso-requests-sandbox.apps.gold.devops.gov.bc.ca) | [Common SSO](https://sso-requests.apps.gold.devops.gov.bc.ca/) |

## Technical reference

The following sections are for System Admins, Tech Leads and runtime group
operators who need environment labels, public key locations and authentication
settings to configure or troubleshoot P2P.

If you're reviewing environments for planning or coordination, the
[Available environments](#available-environments) section provides the
high-level information.

### Environment labels

| APS Environment | P2P Environment | Purpose |
|---|---|---|
| APS Dev | `apsdev` | APS internal development |
| APS Test | `apstst` | P2P Playground |
| APS Prod | `stg` | P2P Staging |
| APS Prod | `bct` | P2P Non-Prod |
| APS Prod | `bc` | P2P Prod |

### Public key sets

A runtime group's public keys are published at:

```text
https://<public-sdx-host>/keysets/sdx.edge.<runtime-group>.<environment>/.well-known/jwks.json
```

`<environment>` is the P2P environment label in the table above. The
`info.details.endpoint` value returned by `sdx-keys.r1` is an address inside
the operator cluster. Use the public URL instead.

| P2P environment | Public host |
|---|---|
| `apsdev` | `https://pzgw-api-gov-bc-ca.dev.api.gov.bc.ca` |
| `apstst` | `https://pzgw-api-gov-bc-ca.test.api.gov.bc.ca` |
| `bct` | `https://pzgw.test.api.gov.bc.ca` |
| `bc` | `https://pzgw.api.gov.bc.ca` |

### Playground

#### P2P Playground

Subsystem authentication in P2P is performed using a token that is issued
by Common SSO.

For access to services in this `Playground` environment, the following token
issuers are accepted:

- `https://dev.sandbox.loginproxy.gov.bc.ca/auth/realms/standard`
- `https://test.sandbox.loginproxy.gov.bc.ca/auth/realms/standard`
- `https://sandbox.loginproxy.gov.bc.ca/auth/realms/standard`

### Production

#### P2P Staging

Subsystem authentication using tokens from Common SSO is not supported in `Staging`.

Clients can use the internal consumer endpoints of the relevant runtime groups
to call services in this environment.

#### P2P Non-Prod

For access to services in `Non-Prod`, the following token issuers are accepted:

- `https://dev.loginproxy.gov.bc.ca/auth/realms/standard`
- `https://test.loginproxy.gov.bc.ca/auth/realms/standard`

!!! note "BC Services Card `sub`"
    For BC Services Card login, both of these environments reference the
    BCSC Test environment, so they return the same `sub` when it
    comes to privacy zones.

Services that are running in `Non-Prod` can choose either `dev` or `test` tokens
from CSS.

!!! note "Token exchange"
    For cases where the service is also calling P2P services, the token is
    passed through as-is, and P2P performs the token exchange.

#### P2P Prod

For access to services in `Prod`, the following token issuers are accepted:

- `https://loginproxy.gov.bc.ca/auth/realms/standard`

## Choose your path

- [Publish a service](publish-a-service.md): Follow the provider path.
- [Consume a service](consume-a-service.md): Follow the consumer path.
