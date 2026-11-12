# Awesome-Revenue-Yield-Management-Optimization

# Awesome Revenue Yield Management & Optimization

> A curated list of top Revenue Yield Management and Optimization platforms — both SaaS/Hosted commercial solutions and open-source alternatives for maximizing revenue through dynamic pricing, demand forecasting, and inventory control in hospitality, travel, and subscription businesses.
> 🌟 Star this repo if you find it useful! 🌟

---

## 📋 Table of Contents

- [SaaS / Hosted Platforms](#-saas--hosted-platforms)
  - [IDeaS Revenue Solutions](#ideas-revenue-solutions)
  - [Duetto](#duetto)
  - [PROS Revenue Management](#pros-revenue-management)
  - [Flyr Labs](#flyr-labs)
  - [Beyond (Beyond Pricing)](#beyond-beyond-pricing)
  - [PriceLabs](#pricelabs)
  - [Wheelhouse](#wheelhouse)
  - [RoomPriceGenie](#roompricegenie)
- [Open-Source Software](#-open-source-software)
  - [HAIP (Hotel AI Platform)](#haip-hotel-ai-platform)
  - [revmng](#revmng)
  - [QloApps](#qloapps)
  - [OpenBRM](#openbrm)
  - [AWS AI Hotel Revenue Optimization](#aws-ai-hotel-revenue-optimization)
  - [RevNest](#revnest)
  - [Dynamic Pricing Simulator](#dynamic-pricing-simulator)
- [Comparison at a Glance](#-comparison-at-a-glance)
- [Contributing](#-contributing)

---

## 🟦 SaaS / Hosted Platforms

Commercial, cloud-hosted Revenue Yield Management and Optimization platforms. These are not open-source but are included as reference points for feature comparison.

### IDeaS Revenue Solutions
**Type:** Enterprise revenue management for hospitality
IDeaS (SAS) is a long-standing enterprise standard for hotel revenue management, offering automated pricing, demand forecasting, and inventory optimization across chain and independent properties. It is widely deployed in large hotel groups requiring sophisticated yield logic and integration with property management systems.

### Duetto
**Type:** Cloud-native revenue management for hotels and casinos
Duetto provides a cloud-native revenue management platform with open pricing, real-time demand forecasting, and group pricing optimization. It is positioned for hotels and casino resorts wanting modern, data-driven pricing without the rigidity of traditional rate fences.

### PROS Revenue Management
**Type:** AI-driven revenue and profit optimization for travel and B2B
PROS provides AI-powered revenue management and dynamic pricing for airlines, travel, and B2B commerce. It focuses on maximizing profit through demand forecasting, price optimization, and offer management across complex selling environments.

### Flyr Labs
**Type:** AI pricing and revenue optimization for airlines and travel
Flyr provides AI-driven pricing and revenue optimization, with a focus on continuous dynamic pricing and offer creation for airlines and travel companies. It is positioned for organizations wanting to move beyond traditional fare class structures.

### Beyond (Beyond Pricing)
**Type:** Dynamic pricing for vacation rentals and short-term rentals
Beyond provides dynamic pricing for Airbnb, Vrbo, and other short-term rental channels, automatically adjusting nightly rates based on demand, seasonality, local events, and booking pace. It is a leading choice for independent hosts and property managers.

### PriceLabs
**Type:** Dynamic pricing and revenue management for rentals
PriceLabs provides dynamic pricing, minimum-stay optimization, and revenue management for short-term rentals and vacation properties. It integrates with major PMS and channel managers, offering granular control over pricing strategies.

### Wheelhouse
**Type:** Dynamic pricing for short-term rentals
Wheelhouse provides dynamic pricing and revenue management for vacation rentals, with customizable strategies and market data. It is positioned for hosts and managers wanting automated pricing without constant manual intervention.

### RoomPriceGenie
**Type:** Automated pricing for independent hotels
RoomPriceGenie provides automated dynamic pricing for independent hotels and small chains, with a focus on simplicity and ease of use. It is positioned for properties that want revenue management without dedicated analyst resources.

---

## 🟩 Open-Source Software

Self-hosted, community-driven Revenue Yield Management and Optimization tools. The open-source ecosystem is **fragmented** across hotel PMS platforms with embedded revenue agents, airline/travel revenue libraries, and billing/revenue platforms rather than direct Duetto or IDeaS equivalents.

### HAIP (Hotel AI Platform)
**Stack:** TypeScript / NestJS / PostgreSQL / React / Redis / BullMQ | **License:** Apache-2.0
HAIP is an open-source hotel PMS with **built-in AI revenue agents**, positioned as infrastructure for independent hotels to compete with chains without $50K/year software [citation:10]. Key revenue features include:
- **Four revenue agents**: Dynamic Pricing, Demand Forecast, Channel Mix Optimizer, and Overbooking Intelligence — applying airline revenue management math adapted for hotels
- **Three operations agents**: Night Audit Anomaly Detection, Housekeeping Optimizer, Cancellation Predictor
- **Three autonomy modes**: manual, suggest, and autopilot — hotels control how much autonomy the AI gets
- **Channel distribution**: Booking.com direct adapter + SiteMinder adapter (450+ OTA/GDS channels)
- **Core PMS**: Reservations, rooms, guests, housekeeping, folios, night audit, rate management, reports
- **Payments**: Stripe integration with PCI compliance
- **Authentication**: Keycloak with 6 roles and property-scoped access

Fully containerized with 551 passing tests and ~100 API endpoints [citation:10]. **Note:** This is a comprehensive PMS with revenue management as one component, not a standalone revenue optimization tool.
**Best for:** Independent hotels and property managers wanting a full open-source PMS with embedded AI revenue agents, accepting the operational overhead of a complete PMS deployment.

### revmng
**Stack:** Python | **License:** MIT
revmng is an open-source revenue management library for Python with an accompanying MCP server (`revmng-mcp`) that exposes its capabilities as tools for AI agents [citation:4]. Key capabilities include:
- **Seat protection**: Littlewood, EMSR-a, EMSR-b, and exact dynamic program
- **Overbooking limits**: by service level or cost trade-off
- **Newsvendor**: critical-fractile stocking quantity
- **Optimal pricing**: profit-maximizing price for linear or constant-elasticity demand curves
- **Revenue opportunity metric (ROM)**: against perfect and no-control benchmarks
- **Group evaluation**: accept/reject by displacement analysis
- **Stay evaluation**: accept/reject multi-night stays against nightly bid prices
- **Network bid prices**: from deterministic LP
- **Metrics**: RevPAR, ADR, occupancy, yield, load factor

The library is validated against published worked examples (Phillips 2005) and cross-checked against an exact dynamic program. The MCP server is stateless and read-only, letting AI agents call deterministic, versioned calculations rather than doing the arithmetic themselves [citation:4].
**Best for:** Developers and data scientists wanting a rigorous, validated revenue management library for airline/travel applications, or AI agent integration via MCP.

### QloApps
**Stack:** PHP / MySQL | **License:** Open Source
QloApps is a free, open-source hotel management platform combining a PMS, booking engine, hotel website, and channel manager for hotels, B&Bs, and vacation rentals [citation:15]. Revenue management features include:
- **Dynamic pricing** adjusted based on real-time occupancy and demand trends
- **Reports and analytics** for performance insights across periods
- **Channel manager** for real-time rate and inventory sync across OTAs
- **Booking engine** with seasonal pricing and special offers

The core software is free, with optional paid add-ons for revenue management, housekeeping, and online check-in. Channel manager subscriptions cost approximately $25-30/month/property [citation:15].
**Best for:** Small hotels and B&Bs wanting a free, open-source PMS with basic revenue management features, accepting limited advanced reporting and optional paid add-ons.

### OpenBRM
**Stack:** Java 17 / Grails 6 / PostgreSQL | **License:** Open Source
OpenBRM is an open-source billing and revenue management platform for telecom, subscription, and usage-based businesses [citation:3]. It handles the full cycle — customer accounts, products and plans, orders, rating, invoicing, and payments — in one system you can run and extend yourself. It supports payment gateway integration, batch billing runs, web service APIs, and configurable workflows for provisioning and account management. Positioned as a practical alternative to proprietary BRM suites like Oracle BRM [citation:3].
**Best for:** Telecom and subscription businesses wanting open-source billing and revenue management, particularly those migrating from proprietary BRM systems.

### AWS AI Hotel Revenue Optimization
**Stack:** Python / CrewAI / Amazon Bedrock | **License:** MIT-0
An AWS sample implementation of an AI-powered hotel revenue optimization system using multi-agent architecture [citation:7]. Features include:
- **Multi-agent AI**: Specialized agents for demand forecasting, pricing optimization, and market analysis
- **Real-time market intelligence**: Competitor pricing analysis and trend monitoring
- **Demand forecasting**: Predictive analytics for occupancy and revenue projections
- **Interactive web interface**: Flask-based dashboard with natural language queries

Built on Amazon Bedrock AgentCore with support for Nova and Claude models, deployed on ECS Fargate with CloudFront CDN [citation:7]. **Note:** This is a sample/reference implementation rather than a production-ready product.
**Best for:** AWS-centric teams wanting a reference architecture for AI-driven hotel revenue optimization, accepting that it is a sample rather than a supported product.

### RevNest
**Stack:** Python / PostgreSQL / WebApp | **License:** Open Source (hackathon project)
RevNest is an AI-assisted revenue management platform for Airbnb hosts and small hotels, built as an NVIDIA hackathon project [citation:11]. Features include:
- **Pricing agent (Revy)** that writes forecast prices and conversation summaries back to PostgreSQL
- **Human approval flow** for live PMS sync — Revy does not directly mutate prices
- **MockHotel PMS** for testing with manager login
- **Airbnb pricing** support with min/max price and pricing horizon

The runtime splits between a sandboxed "NemoClaw" path for hotels (policy-enforced safety) and host "OpenClaw" for Airbnb browsing [citation:11]. **Note:** This is a hackathon project and should be evaluated carefully before any production use.
**Best for:** Developers interested in AI agent-based revenue management for short-term rentals, accepting early-stage maturity.

### Dynamic Pricing Simulator
**Stack:** Python / Flask / scikit-learn | **License:** Open Source
A dynamic pricing simulation project that predicts demand, revenue, and profit for products across categories and recommends optimal prices using Machine Learning [citation:9]. Features include:
- **ML-powered predictions** using Random Forest for demand, revenue, and profit
- **Optimal price recommendation** based on trained models
- **Interactive web interface** with Flask and Chart.js visualizations
- **Synthetic dataset generator** for real-world market simulation

Positioned as a retail pricing simulation rather than a hospitality/travel revenue management system [citation:9].
**Best for:** Developers and analysts wanting a simple ML-based pricing simulator for retail scenarios, not a production revenue management platform.

---

## 📊 Comparison at a Glance

| Software | License | Stack | Dynamic Pricing | Demand Forecast | Self-Hosted | Best For |
|----------|---------|-------|-----------------|-----------------|-------------|----------|
| **IDeaS** | Proprietary | Cloud | ✅ Enterprise | ✅ | ❌ | Large hotel chains |
| **Duetto** | Proprietary | Cloud | ✅ Open pricing | ✅ | ❌ | Hotels + casinos |
| **PROS** | Proprietary | Cloud | ✅ AI-driven | ✅ | ❌ | Airlines + B2B |
| **Beyond** | Proprietary | Cloud | ✅ Short-term rental | ✅ | ❌ | Airbnb hosts |
| **HAIP** | Apache-2.0 | TypeScript/NestJS | ✅ 4 AI agents | ✅ | ✅ | Full PMS + revenue agents |
| **revmng** | MIT | Python | ✅ Optimal pricing | (Caller-supplied) | ✅ (Library) | Airline/travel RM library |
| **QloApps** | Open Source | PHP/MySQL | ✅ Basic | (Reports) | ✅ | Small hotels/B&Bs |
| **OpenBRM** | Open Source | Java/PostgreSQL | (Billing) | ❌ | ✅ | Telecom/subscription billing |
| **RevNest** | Open Source | Python/Postgres | ✅ AI agent | (Check) | ✅ | Airbnb/small hotel (hackathon) |

---

## 🤝 Contributing

Contributions are welcome! If you know of an open-source Revenue Yield Management or Optimization tool that should be listed here, please open a pull request with:

- Project name and URL
- Brief description (1–2 sentences)
- Stack and license
- Why it stands out

Please ensure the project is actively maintained (releases within the last 12 months) and genuinely open-source. Note that the open-source ecosystem for **dedicated revenue yield management** is **very limited and fragmented**. **HAIP** is the most comprehensive open-source effort for hospitality, combining a full PMS with four AI revenue agents (Dynamic Pricing, Demand Forecast, Channel Mix Optimizer, Overbooking Intelligence) under Apache 2.0 [citation:10]. **revmng** fills a critical gap for airline/travel revenue management with a validated Python library and MCP server for AI agent integration [citation:4]. **QloApps** offers basic revenue management within a free hotel PMS [citation:15], while **OpenBRM** targets telecom/subscription billing rather than hospitality yield [citation:3]. Commercial platforms like IDeaS, Duetto, and PROS remain significantly more capable for enterprise-scale revenue optimization with sophisticated forecasting, competitive intelligence, and multi-property coordination.

---

## 📄 License

This list is released under CC0 1.0 Universal (Public Domain). The software projects listed retain their respective licenses.

---

⭐ **If this list helped you discover a useful tool, please star the repo!** ⭐
