---
layout: case.njk
order: 4
title: Recovering an undocumented legacy system and migrating its database
summary: No documentation, no version control, nobody left who knew the code, and a database that had to change vendor. I rebuilt the source from production and delivered the migration.
where: Horsa, contract engagement
when: 2023
role: Contractor, sole developer on the recovery and migration
stack: Java, Spring, MySQL, Oracle, Docker
---
## The problem

A business-critical system was running in production, and that was all anyone had. There was no repository, no documentation and no original developers. On top of that, its database had to move to a different vendor.

## What I did

- **Got the code back.** I reconstructed the source by decompiling the JARs running in production, then made it build again.
- **Rebuilt the knowledge.** From the running application I reverse-engineered the data model and the business rules, so we knew what the system actually did rather than what people remembered.
- **Moved the data.** I delivered a full cross-vendor migration between MySQL and Oracle, validated against the behaviour I had reconstructed.
- **Fixed what I found.** Along the way I analysed and fixed bugs in the Spring applications around it and containerised services with Docker.

The work took six months, while I was running a second engagement in parallel.

## Outcome

A black box became a system the client could understand, change and run on its new database.

It's the kind of situation where I'm at my best: understanding a system deeply before changing it, especially when it gives you nothing for free.
