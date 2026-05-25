# Case Study: Enterprise E-Commerce Platform Build

**Engineer:** Andrew Gunn
**Organization:** Crisis Prevention Institute
**Domain:** B2B training e-commerce (300K+ users, US/CA markets)

---

## Problem

CPI needed a modern, full-stack enterprise e-commerce platform to sell training programs, certifications, and materials to organizations across education, healthcare, and human services. The platform had to support multi-currency transactions (US/CA), integrate with existing enterprise systems (CRM, identity, email), and handle the complexity of B2B sales cycles — organizational purchasing, bulk orders, and certification tracking.

## Solution

### Platform Architecture
Led full-stack development on .NET 8, C#, ASP.NET Core with **Optimizely CMS & Commerce 14+**. The architecture balanced the content management needs of the marketing team (pages, promotions, catalogs managed in Optimizely) with the engineering requirements of a high-traffic transactional platform (performance, security, reliability).

### Payment Processor Migration
Managed the code refactoring and migration when CPI switched payment processors. Implemented **PayFabric/Cybersource** gateway with:
- Multi-currency transaction support (US and Canadian markets)
- Fraud detection and prevention rules
- PCI-compliant payment flow architecture
- Backward-compatible migration (no disruption to existing customers)

### Enterprise Integration Layer
Built integrations connecting:
- **Microsoft Dynamics 365 CRM** — Bidirectional customer and order data sync
- **PingOne Identity Management** — SSO and user provisioning
- **Azure AD Authentication** — Enterprise identity federation
- **SendGrid** — Transactional and marketing email automation

Each integration included bulk data processing, automated job scheduling, and error recovery mechanisms to handle the realities of enterprise data synchronization (API rate limits, partial failures, data conflicts).

### Scalable Frontend
Designed the frontend with server-side rendering for SEO and performance, Tailwind CSS for consistent styling, and custom React hooks for reusable component logic. Optimized for high-traffic e-commerce patterns: product catalog browsing, search, cart management, and checkout flows.

### Data Synchronization
Managed complex data synchronization between CRM, commerce, and analytics systems. Built bulk processing pipelines with job scheduling and automated error recovery to keep customer, order, and product data consistent across all systems.

## Result

A production enterprise e-commerce platform serving **300,000+ users** across US and Canadian markets, with integrated CRM, identity, payment processing, and email automation. The marketing team manages content through Optimizely's CMS interface while the platform handles the transactional complexity under the hood.

## Takeaway

Enterprise e-commerce isn't just "build a store." It's the integration layer — connecting CMS, commerce engine, CRM, identity provider, payment processor, and email platform into a coherent system where data flows reliably between all of them. The platform expertise (Optimizely), the integration experience (Dynamics 365, PingOne, Azure AD, SendGrid), and the payment domain knowledge (multi-currency, fraud detection) are the differentiators.
