# API Proposal 


### API family name  
V2X Exposure API (Not Finalized)

### API family owner  
X Flow Software Technology LLC

### API summary  
The V2X Exposure API aims to expose Vehicle-to-Everything (V2X) capabilities to application developers through standardized CAMARA network APIs. The proposal leverages ETSI MEC V2X Information Service APIs and introduces a simplified CAMARA abstraction layer that hides underlying network and radio complexity.

The API enables applications to interact with vehicles, infrastructure, and edge platforms through operator-exposed APIs.

Example business cases:

Connected Ambulance Routing – Emergency vehicles receive hazard notifications and optimized routes through edge and network intelligence.

Collision Risk Detection – Nearby vehicles and vulnerable road users receive alerts based on real-time traffic and infrastructure data.

Smart City Mobility Services – Applications access V2X provisioning information and safety messages for traffic management and road safety.

### Technical viability  
The proposed API relies on existing and standardized technologies:

ETSI MEC V2X Information Service (MEC 030) for localized V2X interactions between vehicles, infrastructure, and MEC applications.

ETSI MEC platform for edge computing and low-latency service execution.

CAMARA Network APIs to expose simplified northbound APIs for developers.

A Transformation Function (TF) can map MEC southbound APIs to CAMARA northbound service APIs.

Relevant supporting standards:

ETSI MEC specifications (including V2X Information Service)

CAMARA API framework

ETSI MEC White Paper No. 68 (MEC application developer guidelines)

These technologies are already standardized and widely adopted in 5G and edge computing environments.

### Commercial viability  
The proposed API builds on existing edge computing and MEC-based deployments developed within ongoing smart mobility and smart city projects.

Relevant projects include:

CASCAD-e Project – Demonstrates connected ambulance services using edge computing, enabling real-time hazard notifications, remote medical triage, and secure transmission of patient data.

ToMOVE Project – ToMOVE Project – Provides an edge cloud platform with an API Gateway and ETSI-compliant MEC infrastructure, supporting smart mobility services like in City of Turin and V2X communication use cases using smart city datasets and infrastructure.

These projects demonstrate the feasibility of deploying V2X services using MEC platforms and API exposure layers, which can be extended with CAMARA APIs to provide standardized developer access.

### YAML code available?  
NO

### Validated in lab/productive environments?  
NO  

### Validated with real customers?  
NO 

### Validated with operators?  
NO


### Supporters in API Backlog Working Group  
List of supporters.  
*NOTE: That shall be added by the Working Group. Supporting an API proposal means that the supporting company must provide at least 1 (one) Maintainer at the time of the Sub Project creation.*
