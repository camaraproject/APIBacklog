# API Proposal Template
This template captures all the information that a partner should fill out when proposing a new API (or API family) to CAMARA.

### API family name  
Network Authenticated Assembly

### API family owner  
Infosys Limited
*Contributors: @abd-abhisek, @bishnu-infy*

### API summary  
High level description / scope of the API or API family, and two/three examples of in-scope business cases.
NAA is a lightweight CAMARA API that verifies whether a defined group of devices is physically co-present within a specific geographic zone and within a recent time window. Unlike Device Location Verification (single-device, coordinate-based) and Geofencing Subscriptions (individual monitoring), NAA performs a **batch relational co-presence check** across a device cluster and returns a group-level verdict

### Technical viability  
Identify the underlying network/cloud capabilities which are needed for the support of this API or API family, relating these capabilities to standards maturity.  
- Relies on **operator network-level device location capabilities** (e.g., 3GPP NEF/SCEF location services, Rel-15+).
- k-of-n threshold evaluation and group verdict aggregation are performed server-side by the NAA Group Evaluator component.
- Subscription/event model aligns with existing CAMARA CloudEvent patterns (same lifecycle as Geofencing Subscriptions).
- Attestation token provides a tamper-evident, privacy-preserving proof of co-presence for downstream workflow consumption.
- **Scope clarification:** cluster members are restricted to operator-addressable (SIM/eSIM/line-based) devices to ensure interoperability; non-SIM beacons/tags are out of scope.

### Commercial viability  
- No proprietary components required beyond standard network APIs already consumed by CAMARA Device Location
- Open-source reference: CAMARA DeviceLocation API implementation available in the CAMARA GitHub organization

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
