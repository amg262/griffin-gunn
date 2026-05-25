# Tim Griffin

**Distributed Systems Engineer · Tech Lead · Platform Architect**

tim@timgriffin.dev · [LinkedIn](https://www.linkedin.com/in/tim-griffin-770ab6192)

---

## Summary

Software engineer with 6+ years building and modernizing enterprise .NET applications. I specialize in distributed systems, event-driven architectures, and microservices — the kind of infrastructure that has to work at scale, under pressure, and without downtime. I've carried tech-lead scope across two companies with a consistent pattern of end-to-end ownership: architecture, implementation, performance tuning, and production incident response.

---

## Core Competencies

### Distributed Systems Architecture
I design and build systems that communicate reliably at scale. My toolkit includes event sourcing (Streamstone), CQRS, NServiceBus, MediatR, Azure Service Bus, and SignalR for real-time communication. I don't just use these tools — I build the shared infrastructure layers that other engineers consume, including NuGet-packaged client libraries and modular frontend consumer models.

### Cloud Migration & Modernization
I've led the full lifecycle of cloud migration work: Azure App Services → Dockerized containers on AWS EKS, WCF → Minimal APIs (the first such implementation at the company), Azure DevOps → GitLab CI/CD. I use YARP reverse proxy for incremental, zero-downtime migration — the strangler fig pattern applied to real production traffic.

### Performance Engineering
I approach performance problems methodically. My most significant result: a **523× improvement** on a timing-out certification query. The fix involved replacing O(n²) in-memory lookups with `.ToLookup()`, adding composite covering indexes, coordinating cross-service indexing across Organization/Certification/Profile services, and replacing LIKE matching with indexed Full-Text Search. Not a single silver bullet — systematic root-cause analysis.

### Real-Time Platform Infrastructure
At CPI, I architected the platform-wide real-time infrastructure from scratch: a shared .NET NuGet package consumed by backend services paired with a modular React/TypeScript consumer model built on `useSyncExternalStore`. I solved distributed exactly-once completion with Redis atomic operations and documented three extension patterns so engineers can ship real-time features without touching the core connection layer.

### Production Observability & Incident Response
I author KQL queries across Application Insights and Log Analytics for production incident response, surfacing exception hotspots by file and type. Observability isn't an afterthought — it's how I give teams a shared, data-driven view into platform reliability.

---

## Experience

### Software Engineer II / Tech Lead — Crisis Prevention Institute
**Milwaukee, WI · March 2025 – Present**

CPI is the world leader in de-escalation and crisis prevention training, serving 17M+ professionals across education, healthcare, and human services. The engineering team builds the enterprise e-commerce and training platform on a .NET/microservices stack.

- Architected platform-wide real-time infrastructure from scratch (shared .NET NuGet package + modular React/TypeScript consumer model on `useSyncExternalStore`), solving distributed exactly-once completion with Redis atomic operations.
- Major contributor to the Dashboard microservice: 90+ production commits spanning query handlers, event handlers, caching, and auth. Shipped code across **14 microservices in 13 months**.
- Drove a **523× performance improvement** on a timing-out certification query breaking features for users with large org trees.
- Shipped RBAC across backend APIs by redesigning access-token handling with backward-compatible auth flow; configured Ping Identity for role-gated beta-testing rollouts.
- Authored KQL queries used in production incident response, surfacing exception hotspots by file and type.
- Contributed to **Project Golden Eye**, a company-wide initiative implementing agentic AI for engineers.

### Senior Software Engineer / Tech Lead — Workstate (Client: Paysafe)
**Columbus, OH · October 2022 – January 2025**

Paysafe is a global payments platform. Workstate provided the engineering team for core platform modernization.

- Led a team of 4 on a **microservices replatforming**: migrated .NET apps from Azure App Services to Dockerized AWS EKS, transitioned CI/CD from Azure DevOps to GitLab, drove adoption of trunk-based development.
- Spearheaded .NET modernization: the **first WCF → Minimal APIs implementation** at the company, using YARP for incremental, zero-downtime migration.
- Designed and NuGet-packaged reusable API client libraries with `IServiceCollection` extensions wrapping Refit clients, standardizing service integration across the platform.
- Executed a Zendesk → Salesforce migration under aggressive deadlines (replacement service implementations + custom data-migration console apps).

### Software Developer — Performance Foodservice
**La Crosse, WI · January 2020 – October 2022**

- Built backend APIs for the **CustomerFirst e-commerce platform** serving 300,000+ users (ASP.NET Web API, SQL Server, Azure).
- Partnered with a Solutions Architect on a full-stack admin portal.
- Presented technical specs to leadership and business stakeholders.

---

## Education

**University of Wisconsin – La Crosse**
B.S. Computer Science & Mathematics · 2020

**Western Technical College**
A.A.S. Electronic & Computer Engineering Technology · 2017

---

## Technical Skills

| Category | Technologies |
|---|---|
| **Backend** | C#, .NET, Minimal APIs, Azure Functions, NServiceBus, MediatR, SignalR, Event Sourcing (Streamstone), YARP |
| **Data** | SQL Server, Entity Framework, Redis, AWS DocumentDB |
| **Cloud** | Azure (APIM, App Insights, SignalR Service, Service Bus), AWS EKS, Docker |
| **Frontend** | React, Redux, RTK Query, TypeScript, JavaScript |
| **CI/CD** | Azure Pipelines, GitLab CI/CD |
| **Architecture** | Microservices, Event-Driven Architecture, CQRS, Domain-Driven Design, Trunk-Based Development |

---

## What I Bring to the Partnership

My strength is building the **internal infrastructure** that makes complex systems work reliably. I'm the person who designs the message bus topology, builds the shared NuGet packages, tunes the queries that are timing out in production, and architects the real-time communication layer that other engineers extend. I've done this at a payments company (zero tolerance for downtime) and at a platform serving 300K+ users. I lead small teams effectively, I document thoroughly, and I communicate technical decisions to business stakeholders.

Where Andrew extends my range: he brings the CMS/commerce platform expertise (Optimizely), the applied AI/ML integration depth, the frontend design breadth (Vue, Next.js, Tailwind, mobile), and 7+ years of independent consulting experience — which means he knows how to find clients, scope work, and run a business.
