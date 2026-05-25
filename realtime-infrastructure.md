# Case Study: Real-Time Platform Infrastructure from Scratch

**Engineer:** Tim Griffin
**Organization:** Crisis Prevention Institute
**Domain:** Enterprise microservices platform (14+ services)

---

## Problem

CPI's microservices platform needed real-time communication capabilities — live dashboard updates, notification delivery, and synchronized state across browser clients. But the team didn't need just one real-time feature; they needed **infrastructure** that would support real-time features across the entire platform, built by multiple engineers, without each one having to understand the underlying SignalR plumbing and distributed coordination.

## Solution

### Shared Backend Package
Designed and built a shared **.NET NuGet package** consumed by backend microservices. The package encapsulates the SignalR hub configuration, connection management, and message routing — exposing a clean API that service authors use to broadcast events without managing connections directly.

### Modular Frontend Consumer
Built a modular **React/TypeScript consumer model** on `useSyncExternalStore` — React's primitive for subscribing to external data sources. This approach gives frontend engineers a declarative, hook-based API for consuming real-time events that integrates naturally with React's rendering model and avoids the common pitfalls of managing WebSocket connections in component lifecycle.

### Distributed Exactly-Once Completion
Solved the hard distributed systems problem: ensuring that operations triggered by real-time events complete **exactly once** across a distributed system. Used **Redis atomic operations** to coordinate between service instances, preventing duplicate processing when multiple instances receive the same event.

### Extension Patterns
Documented **three extension patterns** so engineers can ship real-time features without touching the core connection layer:
1. Subscribe to existing event streams
2. Define new event types with typed payloads
3. Implement custom aggregation/filtering on the client

## Result

A platform-wide real-time infrastructure that the entire engineering team builds on. Engineers ship real-time features by consuming the shared packages and following documented patterns — they don't need to understand SignalR internals, Redis coordination, or WebSocket lifecycle management. The infrastructure handles connection management, reconnection, and exactly-once delivery guarantees transparently.

## Takeaway

The difference between "we added SignalR" and "we built real-time infrastructure" is the difference between a feature and a platform capability. The value here isn't in the SignalR configuration — it's in the abstraction layer that lets other engineers ship real-time features safely and quickly without duplicating effort or introducing coordination bugs. This is platform engineering: building the tools your team uses to build products.
