# API Scope Enhancement Template

## API name  
Optimal Edge Discovery (OED)  
https://github.com/camaraproject/OptimalEdgeDiscovery  

## New API name  
N/A (scope extension of OED)  

## Scope Enhancement owner  
University of Patras  

## Scope Enhancement summary  
This proposal extends Optimal Edge Discovery (OED) to support **pre-deployment viability discovery**, in addition to its current runtime optimization capabilities.

Today, OED focuses on selecting the optimal edge zone for an active device or session context. This enhancement introduces support for **deployment planning queries**, where no active device is present and the goal is to determine which edge options are viable in a target area given an application profile and constraints.

### Example use cases
- A cloud gaming provider evaluates whether a service can be launched in a specific geographic area based on latency constraints.
- An application provider compares multiple regions/operators to identify viable rollout locations before deployment.
- An aggregator platform provides developers with a unified interface to assess edge availability across multiple operators.

---

## Technical viability  
The enhancement relies on capabilities already aligned with current CAMARA and 3GPP architectures:

- Exposure of network performance characteristics (e.g. latency estimates) through operator APIs (e.g. NEF-based exposure)
- Edge/cloud infrastructure awareness (edge zones, providers)
- Application profile–based constraint evaluation (already part of OED context)

No fundamentally new network capabilities are required. The proposal primarily extends the **query model and response semantics** of OED.

Standards alignment:
- 3GPP NEF (Rel-15+) for network exposure
- ETSI MEC / edge platform exposure models (where applicable)
- CAMARA Commonalities for geographic/context modeling

---

## Commercial viability  
The required capabilities are already supported or emerging in commercial and pre-commercial platforms:

- Operator exposure platforms (e.g. NEF-based APIs)
- Edge computing platforms from hyperscalers and telecom vendors
- Aggregation platforms aligned with GSMA Open Gateway (e.g. Aduna-type models)

These platforms already expose or internally use:
- edge location information
- performance estimation
- application-aware routing or placement logic

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