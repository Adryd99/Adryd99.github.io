---
layout: case.njk
order: 2
title: Microservice templates adopted by hundreds of developers
summary: Every new service started by wiring the same databases, secrets and platform services. I turned that into a template so teams could start from business logic.
where: Engineering Ingegneria Informatica, Core Platform Team
when: 2020–2022
role: Author of the Spring Boot templates and their extensions
stack: Spring Boot, Quarkus, .NET, Rust, AWS, Azure, Kubernetes
---
## The problem

Before a team could write a single line of business logic, a new microservice had to be connected to the same things as every other: databases, secret stores, the event platform, observability. Each team repeated the work, and each repetition was a chance to get credentials or configuration subtly wrong.

## What I did

- **Reusable Spring Boot templates,** pre-wired to the platform: credentials resolved from AWS and Azure secret stores, connectors ready for PostgreSQL, HBase, DynamoDB and InfluxDB, and the event sidecar already in place.
- **The same idea beyond Java.** I extended the approach to .NET templates, so teams on a different stack got the same starting point.
- **Platform pieces around it:** event-management and auditing microservices (Quarkus, Kafka), one of which estimated the operational cost of platform services; an Envoy proxy filter written in Rust and compiled to WebAssembly; an evaluation of canary deployments with Spinnaker.
- **Support.** I helped other teams deploy their services to Kubernetes and get unstuck when the platform surprised them.

## Outcome

The templates became the foundation hundreds of developers started their services from. New services were consistent by default, and the platform team could change shared wiring in one place.
