# API Scope Enhancement Template

## API name

Optimal Edge Discovery (OED)
[https://github.com/camaraproject/OptimalEdgeDiscovery](https://github.com/camaraproject/OptimalEdgeDiscovery)

## New API name

N/A (scope extension of OED)

## Scope Enhancement owner

University of Patras

## Scope Enhancement summary

This proposal explores extending Optimal Edge Discovery (OED) to support **pre-deployment viability discovery**, in addition to its current runtime optimization capabilities.

Today, OED focuses on selecting the optimal edge zone for an active device or session context. This enhancement introduces support for **deployment planning queries**, where no active device is present and the goal is to determine which edge options are viable in a target area given an application profile and constraints.

### Example use cases

* A cloud gaming provider evaluates whether a service can be launched in a specific geographic area based on latency constraints.
* An application provider compares multiple regions/operators to identify viable rollout locations before deployment.
* An aggregator platform provides developers with a unified interface to assess edge availability across multiple operators.

---

## Delimitation versus existing APIs

| API                      | Decision supported                | Timing                  | Input context                                   | Output                                            |
| ------------------------ | --------------------------------- | ----------------------- | ----------------------------------------------- | ------------------------------------------------- |
| **OED**                  | Best edge selection               | Runtime / near-runtime  | Active device / session                         | Single optimal edge zone                          |
| **AED**                  | Application connectivity          | Runtime                 | Deployed application                            | Endpoint information                              |
| **EAM**                  | Deployment & lifecycle            | Deployment / operations | Application package                             | Deployment actions                                |
| **Proposed enhancement** | Deployment feasibility (go/no-go) | Pre-deployment          | Target area + application profile + constraints | Set of viable edge options with estimated metrics |

**Key distinction:**
OED answers *“what is the best edge now?”*
This enhancement answers *“is deployment feasible here at all?”*

---

## Technical viability

The enhancement relies on capabilities already aligned with current CAMARA and 3GPP architectures:

* Exposure of network performance characteristics (e.g. latency estimates) through operator APIs (e.g. NEF-based exposure)
* Edge/cloud infrastructure awareness (edge zones, providers)
* Application profile–based constraint evaluation (already part of OED context)

No fundamentally new network capabilities are required. The proposal extends the discovery model from **runtime target selection** to **pre-deployment feasibility evaluation**, reusing:

* performance estimation mechanisms already used for edge discovery
* application profile constraints already present in OED
* operator or platform knowledge of edge zone capabilities

Standards alignment:

* 3GPP NEF (Rel-15+) for network exposure
* ETSI MEC / edge platform exposure models (where applicable)
* CAMARA Commonalities for geographic/context modeling

---

## Minimal API contract sketch

### Operation

`POST /edge-discovery/viability`

### Inputs

* `targetArea`: geographic area identifier (e.g. region, city)
* `applicationProfile`: application requirements or reference profile
* `constraints`: mandatory requirements (e.g. max latency p95)
* `preferences` (optional): preferred providers or deployment hints

### Outputs

* `edgeOptions`: list of candidate edge zones
* `viability`: whether the candidate satisfies all mandatory constraints
* `estimatedMetrics`: planning-oriented metrics (e.g. latency p95, latency range)
* `providerInfo`: developer-facing provider/operator identifiers

### Meaning of “viable”

A candidate is considered **viable** if all mandatory constraints defined in the request are satisfied based on available performance estimates.

### Metric characteristics

Returned metrics are:

* **estimated**, not guaranteed
* intended for **planning decisions**, not runtime routing

---

## Commercial viability

The required capabilities are already supported or emerging in commercial and pre-commercial platforms:

* Operator exposure platforms (e.g. NEF-based APIs)
* Edge computing platforms from hyperscalers and telecom vendors
* Aggregation platforms aligned with GSMA Open Gateway (e.g. Aduna-type models)

These platforms already expose or internally use:

* edge location information
* performance estimation
* application-aware routing or placement logic

The proposal does not require new infrastructure, but rather a **standardized developer-facing abstraction** for planning.

---

## YAML code available?

NO

---

## Validated in lab/productive environments?

NO

This proposal is currently at the **concept and API design stage**, motivated by identified gaps in the Edge Cloud API lifecycle.

---

## Validated with real customers?

NO

The proposal is based on analysis of developer and platform requirements for edge deployment planning, particularly for latency-sensitive applications.

---

## Validated with operators?

NO

The proposal has not yet been formally validated with operators and is submitted for Working Group discussion and evaluation.

---

## Supporters in API Backlog Working Group

To be added by the Working Group
