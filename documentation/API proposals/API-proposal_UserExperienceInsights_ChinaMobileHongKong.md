# API Proposal Template
This template captures all the information that a partner should fill out when proposing a new API (or API family) to CAMARA.


### API family name  
User Experience Insights (UEI)

### API family owner  
China Mobile Hong Kong, Huawei

### API summary  
The User Experience Insights API is designed to expose the internal network "vision". By leveraging near-real-time data from network elements, it provides developers with high-fidelity Quality of Experience (QoE) scores and near-real-time degradation indicators for active or recent application usage. This API allows Application Functions (AF) to subscribe to network experience notifications for specific users. The API leverages the analytics capabilities of the NWDAF (Network Data Analytics Function) and exposes them through the NEF (Network Exposure Function). When a user's network experience (e.g., throughput, latency, or reliability) falls below a predefined threshold or changes significantly, the network proactively notifies the AF.

In-scope business cases:

Adaptive Application Logic: Streaming or gaming applications can use this API to receive proactive alerts about user experience trends, allowing them to adjust application-level parameters (like bitrates or buffering strategies).

Quality-Guaranteed Premium Ad-Insertion: The OTT Ad-Server uses the API to assess the Near-real-time Experience Score just before the ad-break. High-value 4K ads are only served when UXI confirms a high-quality connection; otherwise, a lighter version is used to ensure uninterrupted playback.

SLA Monitoring for Enterprise Services: Enterprises can subscribe to experience insights for their workforce to ensure critical remote-working applications meet the required performance standards.

### Relation to other APIs
The relation between the proposed User Experience Insights API and the Connectivity Insights API: The UEI API focuses on real-use QoE rather than network/application requirement fulfillment. Furthermore, UEI introduces an applicationProfile-free model, replacing custom threshold configurations to enforce unified detection rules and provides applicationType to detect a series of applications.

The relation between the proposed User Experience Insights API and the Session Insight API: UEI introduces new QoE information(e.g., precise stalling seconds, HD bitrate duration, etc.) captured directly from user-plane traffic, which are not in the current Session Insights scope. Besides, the same as Connectivity Insights, Session Insights requires a session resource with `applicationProfile` defined. UEI is applicationProfile-free, it can be applied to a broader range of applications without the need for predefined profiles, making it more flexible and easier to adopt. Besides, UEI doesn't rely on explicitly creating a session resource, it leverages the user's active, real-use network sessions.

The relation between the proposed User Experience Insights API and the Predictive Connectivity Data API: UEI is focused on observed or near-real-time real-use application QoE for an existing user/application context. “Prediction” or “trend” references are limited to short-term degradation detection within an active/recent session. Unlike Predictive Connectivity, which forecasts network capabilities for geographic areas, UEI performs no spatiotemporal mapping. It treats location data only as contextual metadata for the observed experience. Coverage forecasting, route/area planning, future service-level availability, and volume/altitude-based connectivity estimation remain out of scope and are covered by Predictive Connectivity Data.

### Technical viability  
This API is technically viable based on 3GPP 5G core network standards:

3GPP TS 23.288 (NWDAF): Utilizes the "User Data Congestion" and "Service Experience" analytics ID.

3GPP TS 23.502 / TS 29.522 (NEF): Requires NEF to support the exposure of analytics via Nnef_EventExposure or Nnef_AnalyticsExposure services.

Maturity: These features are part of 3GPP Release 16/17, which are currently being deployed in commercial 5G SA networks.

Near-real-time Notification: The statistics and calculations can be processed in near-real-time directly at the User Plane level for the live sessions.

QoE Metrics:
- avgQoe: Average score of experience analysis.Value range: 1 to 100 points.
- maxResolution: Maximum resolution in the experience analysis period. The value can be 2160, 1080, 720, or 480. 1080 indicates 1080p (1920 x 1080).
- mostResolution: The resolution with the highest duration ratio within the experience analysis period. The value can be 2160, 1080, 720, or 480. 1080 indicates 1080p (1920 x 1080).   
- maxBitRateUl: Maximum uplink bit rate (kbit/s).
- avgBitRateUl: Average uplink bit rate (kbit/s)  
- maxBitRateDl: Maximum downlink bit rate (kbit/s)
- avgBitRateDl: Average downlink bit rate (kbit/s)
- stallSec: Frame freezing duration, in seconds.
- stallNum: Number of frame freezing times. The detection period is 5 seconds.
- serviceDelay: Service latency, in seconds.
- initialDur: Initial service buffering duration, in seconds.

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
