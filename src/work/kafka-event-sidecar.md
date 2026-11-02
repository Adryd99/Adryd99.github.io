---
layout: case.njk
order: 1
title: A Kafka sidecar at the core of an enterprise event platform
summary: Thousands of microservices needed one reliable way to produce and consume events. I designed the component that gave it to them.
where: Engineering Ingegneria Informatica, Core Platform Team
when: 2020–2022
role: Designer and main developer of the sidecar; co-author of version 2
stack: Java, Kafka, Avro, Schema Registry, Kubernetes
---
## The problem

The platform ran thousands of microservices on Kubernetes, written by many teams. Every one of them needed to publish and consume events. Left alone, each team would have wired Kafka in its own way: different serialization, different retry logic, different mistakes. The Core Platform Team, about fifty engineers building shared infrastructure, needed a single, dependable way in.

## What I did

I designed and built an **event sidecar** in Java: a component deployed next to every microservice that handled all event production and consumption on its behalf. Services talked to the sidecar; the sidecar talked to Kafka.

- **One contract for the whole platform.** I introduced Avro with a Schema Registry, so every event had a schema and schemas could evolve without breaking older consumers (backward compatibility enforced, not hoped for).
- **Payloads of every size.** The same path had to carry tiny notifications and documents up to about 100 MB, which meant thinking about memory, not only throughput.
- **A second version built for load.** With a colleague I re-architected the sidecar: multithreaded pools, tighter memory management, and a factory pattern that separated local-development behaviour from production behaviour, so latency stayed low under load and the code stayed testable.

## Outcome

Millions of events flowed through one shared component instead of hundreds of hand-rolled integrations. Teams stopped thinking about Kafka plumbing and focused on their own domain.
