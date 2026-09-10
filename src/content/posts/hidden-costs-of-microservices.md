---
title: "The Hidden Costs of Microservices"
date: "Sep 2026"
tags: ["Architecture"]
excerpt: "Lessons from building payment platforms, healthcare systems, and project management tools about the operational, data, and team costs of distributed architectures."
description: "The hidden costs of microservices architecture, learned from building real systems."
---

Microservices have been the darling of architecture discussions for years. They promise scalability, independent deployments, and the freedom to use different tech stacks for different problems. But after building systems like payment platforms, healthcare systems, and project management tools, I've learned that the hidden costs of microservices are real — and most teams don't see them until it's too late.

## The Operational Complexity No One Warns You About

When I migrated AWAN's PPOB system from CodeIgniter 3 to FastAPI, it was already a significant undertaking. Now imagine doing that migration across 10 separate services, each with its own deployment pipeline, its own logs, and its own dependencies.

With a monolith, if a transaction fails, you trace it through one codebase. With microservices, that same transaction might touch an authentication service, a payment gateway service, a wallet service, and an escrow service. Suddenly, you need distributed tracing tools like Jaeger or Zipkin — not because you want them, but because you can't debug without them.

For high-volume financial systems like AWAN, where concurrent transactions are the norm, this complexity isn't theoretical. It's a daily reality that slows down your team and increases the surface area for bugs.

## Data Consistency Becomes Your Nightmare

One of the hardest lessons in distributed systems is that you can't just JOIN tables across services. In TST, our project management system has over 20 entities — customers, agreements, projects, purchase orders, work orders, SPK, collections, and invoices. They're deeply interconnected.

Now imagine splitting these into separate microservices. Want to show a project dashboard with customer info, invoice status, and SPK progress? You're making four API calls, waiting for eventual consistency, and hoping the data hasn't changed between requests.

For AWAN's escrow and wallet systems, strong consistency isn't optional — it's a regulatory requirement. Microservices make strong consistency painfully difficult. You end up implementing complex saga patterns or distributed transactions that are hard to get right and even harder to maintain.

## The Infrastructure Tax

When I built Taskflow, I chose a pnpm monorepo with Turborepo. The API, the web app, and shared packages all live together. I get the benefits of code sharing and independent testing without the operational overhead of separate deployments.

Compare that to a full microservices setup: you'd need a container orchestrator like Kubernetes, a service mesh for communication, an API gateway for routing, message brokers for async communication, and monitoring for each service. Each of these adds cost — not just in dollars, but in expertise your team needs to acquire and maintain.

The cloud bills alone can surprise you. What was one server running a monolith becomes ten containers, each with their own memory and CPU allocations, plus the orchestration layer on top.

## Team Overhead and Conway's Law

Working on SMILE, Indonesia's national healthcare information system, taught me something about team structure. Conway's Law is real: your system architecture will mirror your organization's communication structure.

With microservices, onboarding becomes harder. New developers can't just understand "the codebase" — they need to understand service boundaries, API contracts, and how data flows between services. "Who owns this bug?" becomes a common question when a feature spans three services maintained by different teams.

Cross-team collaboration, which was already challenging, becomes even more complex when each team deploys independently and can break each other's services in subtle ways.

## When Microservices Actually Make Sense

Microservices aren't bad — they're just not always the right answer. They make sense when:

- You have large teams that genuinely need to work independently
- You need to scale different parts of your system differently
- You've already maxed out a well-structured monolith

Taskflow's monorepo approach gave me most of the benefits of microservices (independent packages, clear separation) without the operational costs. That's often the sweet spot for most projects.

## Conclusion

The best architecture is the one your team can actually manage. Microservices solve real problems, but they introduce hidden costs that can overwhelm teams that aren't ready for them.

Start with a modular monolith. Keep your code organized, your boundaries clear, and your deployment simple. When you genuinely need to split — and you'll know when that time comes — you'll do it from a position of strength rather than desperation.

The hidden costs of microservices aren't a reason to avoid them. They're a reason to be intentional about when and why you adopt them.