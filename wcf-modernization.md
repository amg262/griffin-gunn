# Case Study: WCF to Minimal APIs — Zero-Downtime Migration

**Engineer:** Tim Griffin
**Organization:** Workstate (Client: Paysafe)
**Domain:** Global payments platform

---

## Problem

Paysafe, a global payments company, was running legacy WCF (Windows Communication Foundation) services that were increasingly difficult to maintain, deploy, and scale. WCF is effectively end-of-life in the modern .NET ecosystem — no new development, limited cloud support, and a shrinking talent pool of engineers willing to work with it. The services needed to be modernized to .NET Minimal APIs, but a big-bang rewrite was unacceptable: this is a payments platform where downtime directly translates to lost revenue and regulatory risk.

## Approach

### Strangler Fig Pattern with YARP

Rather than rewriting all services at once, the migration used the **strangler fig pattern** — incrementally replacing WCF endpoints with Minimal API equivalents while keeping the legacy services running. **YARP (Yet Another Reverse Proxy)** served as the routing layer, directing traffic to either the legacy WCF service or the new Minimal API endpoint based on which routes had been migrated.

This was the **first WCF → Minimal APIs implementation at the company**. There was no internal playbook, no prior art to follow — the approach had to be designed, validated, and documented from scratch.

### Containerization & CI/CD Migration

Simultaneously, the team migrated the hosting infrastructure:
- **Azure App Services → Dockerized containers on AWS EKS** (Elastic Kubernetes Service)
- **Azure DevOps → GitLab CI/CD** pipelines
- Adopted **trunk-based development** practices

### Standardized Integration Libraries

Designed and NuGet-packaged reusable API client libraries with `IServiceCollection` extensions wrapping Refit clients. This standardized how every service in the platform integrates with others — rather than each team writing bespoke HTTP client code, they register a typed client from the shared package and get consistent retry policies, logging, and error handling.

## Result

Successful incremental migration from WCF to Minimal APIs with **zero downtime**. The YARP routing approach allowed the team to migrate one endpoint at a time, validate in production, and roll back instantly if needed. The migration also delivered:
- Modern, containerized deployment on Kubernetes
- Faster CI/CD pipeline (GitLab)
- Trunk-based development reducing merge complexity
- Shared client libraries reducing integration boilerplate across the platform

## Takeaway

WCF modernization is one of the most common pain points in the .NET ecosystem, and most teams approach it wrong — either attempting a risky big-bang rewrite or avoiding it until forced. The YARP-based strangler fig approach makes it incremental, reversible, and safe. This playbook is directly applicable to any organization running legacy WCF services.
