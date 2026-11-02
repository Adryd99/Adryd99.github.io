---
layout: case.njk
order: 3
title: Automatic network discovery for a national telecom operator
summary: Network devices had to be found, inventoried and set up for monitoring. Doing it by hand doesn't scale, so I built a service that does it.
where: Swisscom, through adesso
when: 2023–today
role: Solution design, development and production deployments
stack: Java, Spring Boot, SNMP4J, Telegraf, Kafka, Kubernetes
---
## The problem

Before a network device can be monitored, someone has to know it exists, what it is, and how to talk to it. At the scale of a national telecom operator, keeping that inventory and the monitoring configuration up to date by hand is slow and error-prone.

## What I did

- **A discovery service in Spring Boot** that finds devices over SNMP (v2c and v3) and inventories them.
- **Concurrent polling with SNMP4J.** One shared, thread-safe SNMP session for the whole application; targets and requests created per call; careful handling of SNMPv3 security (users, authentication, engine IDs), which is where concurrency bugs like to hide.
- **Monitoring set up automatically.** The service generates the Telegraf configuration needed to collect each device's metrics, removing a manual step.
- **End-to-end ownership.** I write the solution designs, agree them with the client, and carry out the production deployments myself. Around it: a Kafka consumer integrating a new data feed, a legacy data-processing component rewritten in Python, CI/CD pipelines in GitLab.

## Outcome

A task that depended on people remembering to do it became something the system does on its own, owned end to end from the first design document to production.
