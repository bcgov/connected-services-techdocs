---
title: Experimental Features – LAB Only
---

The following features are currently experimental and available in the LAB environment only. They are not currently available for production use.

## Event Management

Event Management enables organizations to publish and consume event-based messages through SDX using AsyncAPI services. It supports scenarios where consumers need to receive information when an event occurs, rather than requesting information directly from an API.

This guide provides the technical steps for registering an AsyncAPI service, configuring an endpoint for publishing events, connecting consumers to the service, setting up webhooks to receive messages, and publishing messages.

This process is managed by the System Admin.

Technical guide: [Event Management](https://developer.gov.bc.ca/docs/default/component/aps-infra-platform-docs/how-to/sdx-ape-event-mgmt/)

## Policy Management

Policy Management enables organizations to define and apply rules that control access to services and data exchanged through SDX. These policies can use information about a request, such as the user, requested resource, or authorization data, to determine whether access should be permitted.

This guide provides the technical steps for creating and registering OPA and CEDAR policies, applying a policy to an SDX connection for enforcement, and registering data sources that can provide additional information for access decisions.

This process is managed by the System Admin.

Technical guide: [Policy Management](https://developer.gov.bc.ca/docs/default/component/aps-infra-platform-docs/how-to/sdx-ape-policy-mgmt/)
