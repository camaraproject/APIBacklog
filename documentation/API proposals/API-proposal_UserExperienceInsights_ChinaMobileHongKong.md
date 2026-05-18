# API Proposal Template
This template captures all the information that a partner should fill out when proposing a new API (or API family) to CAMARA.


### API family name  
User Experience Insights (UEI)

### API family owner  
China Mobile Hong Kong, Huawei

### API summary  
The User Experience Insights API is designed to expose the internal network "vision". By leveraging real-time data from network elements, it provides developers with high-fidelity Quality of Experience (QoE) scores and predictive network trends. This API allows Application Functions (AF) to subscribe to real-time network experience notifications for specific users. The API leverages the analytics capabilities of the NWDAF (Network Data Analytics Function) and exposes them through the NEF (Network Exposure Function). When a user's network experience (e.g., throughput, latency, or reliability) falls below a predefined threshold or changes significantly, the network proactively notifies the AF.

In-scope business cases:

Adaptive Application Logic: Streaming or gaming applications can use this API to receive proactive alerts about user experience trends, allowing them to adjust application-level parameters (like bitrates or buffering strategies) ahead of time.

Quality-Guaranteed Premium Ad-Insertion: The OTT Ad-Server uses the API to assess the Real-time Experience Score just before the ad-break. High-value 4K ads are only served when UXI confirms a high-quality connection; otherwise, a lighter version is used to ensure uninterrupted playback.

SLA Monitoring for Enterprise Services: Enterprises can subscribe to experience insights for their workforce to ensure critical remote-working applications meet the required performance standards.

### Technical viability  
This API is technically viable based on 3GPP 5G core network standards:

3GPP TS 23.288 (NWDAF): Utilizes the "User Data Congestion" and "Service Experience" analytics ID.

3GPP TS 23.502 / TS 29.522 (NEF): Requires NEF to support the exposure of analytics via Nnef_EventExposure or Nnef_AnalyticsExposure services.

Maturity: These features are part of 3GPP Release 16/17, which are currently being deployed in commercial 5G SA networks.

### Commercial viability  
The underlying network capabilities (NEF and NWDAF) are now widely available as industrialized solutions. Many Tier-1 operators have already deployed NWDAF for internal network optimization and are moving towards external exposure of these insights to enhance ecosystem value.

### YAML code available?  
YES.

### Validated in lab/productive environments?  
YES. Validated in a lab environment simulating 5G SA core network signaling with actual NWDAF analytics triggers.

### Validated with real customers?  
No.

### Validated with operators?  
No.

### Supporters in API Backlog Working Group  
List of supporters.  
*NOTE: That shall be added by the Working Group. Supporting an API proposal means that the supporting company must provide at least 1 (one) Maintainer at the time of the Sub Project creation.*
