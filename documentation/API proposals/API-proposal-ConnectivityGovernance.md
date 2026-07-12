## API Proposal Template

This template captures all the information that a partner should fill out when proposing a new API (or API family) to CAMARA.

#### API family name

Connectivity Governance

#### API family owner

Infosys Limited
*Contributors: @abd-abhisek, @bishnu-infy

#### API summary

The **Connectivity Governance API** is a network‑level policy enforcement API that enables telcos to provide enterprise customers with centralized control over application access, bandwidth optimization, productivity protection, and compliance enforcement across MPLS, SD‑WAN, broadband, and mobile networks—without requiring any device‑level software or agents.

**API benefit / scope:**
- Enforces policies directly at network gateways (PE routers, SD‑WAN edges, telco core), making controls consistent, tamper‑proof, and cross‑device.
- Supports multi‑tiered governance intents such as category-based restrictions, time-based rules, rate limits/throttling, and prioritization (e.g., UC traffic).

**Examples of in‑scope business cases:**
- Restrict streaming during work hours while allowing collaboration tools.
- Block VPN/proxy/TOR usage for regulated sites/user groups.
- Prioritize real‑time collaboration traffic to safeguard critical operations.

This API is proposed for enterprise customers; target use cases exist across Healthcare, Legal, and Media/Entertainment domains.

#### Technical viability

- Policies are translated by the operator into enforcement constructs using SD‑WAN controllers, router ACLs, firewall rules, DNS filters, or mobile core policy (e.g., PCF) configurations.
- Designed to operate across multi‑site, hybrid-network, and multi‑access environments (MPLS, SD‑WAN, broadband, mobile, and 5G slicing concepts) through a single intent-based API.

#### Commercial viability

- Provides an operator‑monetizable “governance‑as‑a‑service” add‑on that can be bundled with MPLS, SD‑WAN, enterprise broadband, mobile corporate plans, or 5G slicing offers.
- Reduces enterprise operational overhead compared to endpoint agents/MDMs and addresses privacy concerns by avoiding device installations.

#### YAML code available?

NO

#### Validated in lab/productive environments?

NO — Currently in design/proposal phase.

#### Validated with real customers?

NO — Use cases have been validated conceptually.

#### Validated with operators?

IN PROGRESS — Validation is currently underway.

#### Supporters in API Backlog Working Group

List of supporters.
- Infosys Limited (@abd-abhisek, @bishnu-infy)
- British Telecom (Pawan Kumar)
