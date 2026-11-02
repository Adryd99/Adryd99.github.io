---
layout: case.njk
order: 5
title: A fintech back end built for compliance from day one
summary: A financial platform for freelancers that connects to their bank accounts has to meet PSD2 and GDPR. I designed the back end with that as a starting point, not an afterthought.
where: Opex, co-founded project
when: 2025–2026
role: Co-founder and backend lead
stack: Java, Spring Boot, Keycloak, PostgreSQL, Salt Edge (PSD2)
---
## The problem

Opex helps freelancers manage their finances: open banking, invoicing, cash-flow and quarterly VAT forecasting. The moment a product reads people's bank accounts, security and regulation stop being features you add later. They decide the architecture.

## What I did

- **Back-end architecture** with Spring Boot, Keycloak for identity and PostgreSQL for storage.
- **Open banking** through Salt Edge under PSD2.
- **Strong customer authentication** with TOTP.
- **Encryption of sensitive data** with AES-256-GCM.
- **GDPR built in:** consent tracking and audit logging, so the system can answer who agreed to what, and who accessed what.

## Outcome

A back end where compliance is part of the design rather than a list of patches. The code is on [GitHub](https://github.com/Adryd99/Opex-main).
