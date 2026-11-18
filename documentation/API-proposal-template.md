# API Proposal Template
This template captures all the information that a partner should fill out when proposing a new API (or API family) to CAMARA.

> **Important**
> Before submitting a new API proposal, proposal owners shall review the CAMARA [Project Charter](https://github.com/camaraproject/Governance/blob/main/ProjectCharter.md), in particular the sections related to CAMARA scope.
>
> CAMARA scope is limited to telco APIs exposed as **customer-facing northbound APIs**. Only **Service APIs** and **Service Management APIs** are in scope. **Operate APIs** and **east-west / federation / roaming APIs** are out of scope.
>
> If there is any doubt regarding scope fit, the proposal owner shall justify it explicitly in the sections below with reference to the Project Charter.

### API family name  
Network Outage API

### API family owner  
EE

### API summary  
The Network Outage API provides a standard way for authorised devices, apps and support channels to check whether a customer is affected by a known mobile network outage, service degradation or planned maintenance event. It helps explain poor or lost connectivity using operator network data, so customers can be given clearer information instead of being pushed through unnecessary troubleshooting or support journeys.

### CAMARA scope alignment

#### Northbound API type  
Select the CAMARA northbound API type for this proposal:
- [X] Service API
- [ ] Service Management API

#### Scope fit with CAMARA  
This proposal is within the scope of CAMARA as defined in the Project Charter. The proposed Network Outage API is a customer-facing northbound API that exposes information about the operational status and availability of telecommunications network services in a simplified, standardised and developer-consumable format.
The CAMARA Charter explicitly identifies Service Management APIs as being in scope, describing them as APIs intended for end consumers to manage or obtain information about offered service APIs in runtime, including service availability and performance information. The Network Outage API aligns directly with this definition by providing developers and enterprises with visibility of network outages, service degradation and availability status affecting network services.
The proposal supports CAMARA's objectives to harmonise telecom APIs, abstract underlying network complexity and provide interoperable access to operator capabilities across markets. It enables consistent consumption of network status information without exposing operator-specific systems, processes or infrastructure implementations.
The proposal does not address service fulfilment, provisioning, fault management workflows, commercial arrangements, pricing, settlement, assurance processes or other Operate API functions that are explicitly identified in the Charter as being outside CAMARA scope. Instead, it focuses solely on the standardisation of a customer-facing Service Management API, which is a core deliverable of the CAMARA Project.

#### Telco capability exposed  
Exposure of real-time and planned mobile network outage information and service availability status for a given Tracking Area Code (TAC), sourced from operator network monitoring and operations systems.

#### Overlap with existing CAMARA APIs  
- [X] The CAMARA API portfolio has been reviewed, and it has been confirmed that there is no overlap.  

#### Explicit out-of-scope items for this proposal  
This API is limited to exposing operator-maintained information regarding active or planned network service disruptions within a specified geographic area (e.g., Tracking Area Code). It does not provide device-level diagnostics, signal quality measurements, user location capabilities, network control functions, fault remediation, network topology information, outage forecasting, or QoS management capabilities.

#### Proposal owner declaration  
- [X] I confirm that this proposal has been reviewed against the current CAMARA Project Charter scope.

### Technical viability  
Needs network incident monitoring and reporting system that has the visibility of operator's mobile network.

### Commercial viability  
Not applicable.

### YAML code available?  
YES.

### Validated in lab/productive environments?  
YES. Productive network.  

### Validated with real customers?  
YES.
1 OEM and multiple location based services customers.
Use case: Whether network services are currently available in an area.

### Validated with operators?  
NO.

### Supporters in API Backlog Working Group  
EE.
