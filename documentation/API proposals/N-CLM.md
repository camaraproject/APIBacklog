# API Proposal Template
This template captures all the information that a partner should fill out when proposing a new API (or API family) to CAMARA.

### API family name  
Network Contract Lifecycle Management

### API family owner  
Infosys Limited
*Contributors: @hemantagogoi-infy, @vijaymurthyn 

### API summary  
N-CLM is a CAMARA API that enables real-time SLA governance for live network services by binding measurable SLA policies to CAMARA service instances (e.g., QoD, Dedicated Networks), continuously evaluating compliance, and triggering instant breach notifications via CloudEvents. 

In-scope examples:

Low-latency SLA enforcement for fintech apps
Availability assurance for healthcare/critical systems
Multi-metric SLA control for autonomous logistics

### Technical viability  
Uses CAMARA service binding + operator telemetry (CQM) for real-time evaluation 
Closed-loop lifecycle: bind → evaluate → notify → amend → close 
CloudEvents-based event model (no polling) 
Supports mid-lifecycle SLA updates (PATCH) without reprovisioning 
Cross-operator portable SLA model aligned with CAMARA 


### Commercial viability  
Built on existing CAMARA APIs (QoD, CQM, Dedicated Networks) → low adoption barrier
Enables SLA-backed premium network offerings
Supports API monetization via programmable guarantees & breach events
CAMARA-aligned → interoperable and open ecosystem


### YAML code available?  
NO
Sequence diagram is available in deck

### Validated in lab/productive environments?  
NO.  
NO — Currently in design/proposal phase. Lab validation can be planned as a next step after CAMARA backlog acceptance

### Validated with real customers?  
NO.  
NO — Use cases have been validated conceptually

### Validated with operators?  
YES
IN PROGRESS — Validation is currently underway

### Supporters in API Backlog Working Group  
List of supporters.  
- Infosys Limited (@abd-abhisek, @bishnu-infy, @hemantagogoi-infy, @vijaymurthyn)
- BT (Pavan Kumar)
- Telstra (Shyam)
