# Case Study: 523× Query Performance Improvement

**Engineer:** Tim Griffin
**Organization:** Crisis Prevention Institute
**Domain:** Enterprise e-commerce / training platform (300K+ users)

---

## Problem

A certification query was timing out for users with large organizational trees, breaking core platform features. The query powered certification status lookups across a hierarchical org structure — a critical path for the platform's primary business function. Users in organizations with deep or wide trees (hundreds to thousands of nodes) were experiencing complete feature failures.

## Diagnosis

Rather than applying surface-level fixes, the approach was systematic root-cause analysis across the application and database tiers:

1. **Application Layer** — Identified O(n²) in-memory lookups as the primary bottleneck. The existing code was performing nested iterations over collections that grew quadratically with org tree size.

2. **Database Layer** — The queries backing this feature lacked appropriate indexes for the access patterns being used. LIKE-based text matching on the Accounts table was forcing full table scans.

3. **Cross-Service Impact** — The query's performance was degraded not just by its own service, but by cascading lookups across the Organization, Certification, and Profile microservices.

## Solution

Five layers of optimization, coordinated across service boundaries:

| Layer | Change | Impact |
|---|---|---|
| Algorithm | Replaced O(n²) in-memory lookups with `.ToLookup()` (hash-based) | Eliminated quadratic growth |
| Indexing | Added composite covering indexes on the primary query | Reduced I/O and eliminated key lookups |
| Cross-Service | Coordinated indexing across Organization, Certification, and Profile services | Eliminated cascading slow queries |
| Text Search | Replaced LIKE matching with indexed Full-Text Search on Accounts table | Eliminated full table scans |
| Query Design | Restructured the query to align with the new index strategy | Ensured the optimizer could use the indexes |

## Result

**523× performance improvement.** Queries that were timing out now complete in milliseconds. The fix was deployed with no breaking changes to the API contract, and the approach was documented for the team to apply to similar patterns across other services.

## Takeaway

Performance problems in distributed systems are rarely single-cause. This required understanding the algorithmic complexity at the application layer, the indexing strategy at the database layer, and the interaction patterns across service boundaries — then coordinating fixes across all three. The diagnostic method is repeatable: profile → identify the dominant cost → fix it → measure → repeat.
