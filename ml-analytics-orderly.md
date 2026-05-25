# Case Study: ML-Powered Customer Analytics from Zero

**Engineer:** Andrew Gunn
**Organization:** Crisis Prevention Institute
**Domain:** B2B training e-commerce (1,250+ accounts)

---

## Problem

CPI is the world's leading provider of de-escalation and crisis prevention training, serving organizations across education, healthcare, and human services. Despite having 1,250+ B2B accounts generating significant recurring revenue, the company had **zero customer analytics infrastructure**. There was no way to identify which accounts were at risk of churning, which were primed for expansion, or how customer behavior was trending over time. All customer intelligence was tribal knowledge in salespeople's heads.

## Solution

Built **"Orderly"** — a full ML-powered customer analytics platform from scratch using React 18, TypeScript, and Chart.js on the frontend with .NET 8 backend services.

### RFM Segmentation Engine
Implemented Recency, Frequency, Monetary (RFM) analysis algorithms that automatically scored and segmented all 1,250+ B2B accounts. Each account received dynamic scores based on:
- **Recency** — How recently they purchased training materials or renewed certifications
- **Frequency** — How often they transact and engage with the platform
- **Monetary** — Total revenue contribution and average order value

### Churn Prediction
Built ML models that identified accounts showing behavioral patterns correlated with churn — declining order frequency, reduced engagement, lapsed certification renewals. The system flagged at-risk accounts before human intuition would catch them.

### Real-Time Business Intelligence
Designed interactive dashboards with Chart.js providing real-time visibility into customer health metrics, segment distributions, revenue trends, and risk indicators. The dashboards were built for business users (sales and account management), not engineers.

### Data Pipeline
Connected to the existing e-commerce platform and CRM (Dynamics 365) to pull transaction history, engagement data, and account metadata. Automated data synchronization with bulk processing and error recovery.

## Result

Transformed the organization from **zero customer analytics** to **automated intelligence with proactive risk identification**. Account managers could now see at a glance which of their accounts needed attention, which were growing, and which were at risk — backed by data rather than gut feel.

## Takeaway

The highest-impact AI work isn't always the most technically complex. RFM segmentation is a well-understood technique — the value was in building the complete system: data pipeline, ML models, real-time dashboards, and user-facing interface, integrated into the company's existing .NET/Dynamics 365 ecosystem. The transformation from "nothing" to "automated intelligence" is the story that resonates with mid-market companies who know they're flying blind on customer data.
