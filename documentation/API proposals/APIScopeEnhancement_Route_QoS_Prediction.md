# API Scope Enhancement Template
This template captures all the information that a partner should fill out when proposing a scope enhancement for an existing CAMARA API.

> **Important**
> Before submitting a scope enhancement, proposal owners shall review the CAMARA [Project Charter](https://github.com/camaraproject/Governance/blob/main/ProjectCharter.md), in particular the sections related to CAMARA scope.
>
> CAMARA scope is limited to telco APIs exposed as **customer-facing northbound APIs**. Only **Service APIs** and **Service Management APIs** are in scope. **Operate APIs** and **east-west / federation / roaming APIs** are out of scope.
>
> A scope enhancement requires API Backlog validation when it modifies the original scope of an existing API.
>
> If there is any doubt regarding scope fit or impact on the existing API, the proposal owner shall justify it explicitly in the sections below with reference to the Project Charter.

## API name
[Predictive Connectivity Data](https://github.com/camaraproject/PredictiveConnectivityData)

## New API name
Not applicable. The proposal remains within Predictive Connectivity Data (PCD); "Route QoS Prediction" is the working name for the added route-aware capability, not a separate API.

## Scope Enhancement owner
X Flow Software Technology LLC

## Scope Enhancement summary
Route QoS Prediction adds trajectory-aware, per-segment QoS forecasting to PCD. An application submits a planned route (an ordered list of waypoints) and receives a forecast of network conditions (latency, throughput, reliability) with a confidence value for each segment, before a device travels the route.

Example in-scope business cases:
- **Connected ambulance / emergency routing** — forecast QoS along candidate routes ahead of a time-critical journey, so the application can factor connectivity risk into route selection (route selection itself stays outside this API).
- **Autonomous vehicle / fleet route planning** — evaluate expected QoS along a planned path before committing a vehicle or fleet to it.
- **Drone corridor planning** — extend PCD's existing area/volume forecasting to a linear flight corridor with per-segment resolution, consistent with PCD's stated drone and autonomous-vehicle use cases.

## CAMARA scope alignment

### Northbound API type
- [x] Service API
- [ ] Service Management API

### Scope fit with CAMARA
This remains developer-facing service exposure: an application queries a forecast and optionally subscribes to forecast-change notifications. No radio or network provisioning, configuration, or management capability is exposed, consistent with the Project Charter's Service API scope. The API produces a forecast only — it does not invoke QoD, select or optimise a route, or adapt the application; those are shown only as composition examples.

### Telco capability exposed
The predictive network-analytics capability already underlying PCD (forecasting connectivity/service level over an area or time window), extended to accept a route/corridor as input and to return the forecast broken down per route segment in travel order.

### Overlap with existing CAMARA APIs
- [x] The CAMARA API portfolio has been reviewed, and it has been confirmed that there is no overlap.

Reviewed against:
- **Predictive Connectivity Data** — direct basis for this enhancement (see delta below); not overlapping since this proposal changes/extends PCD's own scope rather than duplicating it.
- **Connectivity Insights** — confirmed with @Eric-Murray/@Kevsy as non-overlapping: Connectivity Insights alerts on current channel quality at the device's current location, not predictive along a future/anticipated route.
- **QoD / Traffic Influence** — explicitly out of scope for this proposal; usable downstream via composition once a forecast is obtained.
- **TM Forum TMF759 (Private Optimized Binding) / Private Optimized Connectivity** — sit on the management/NaaS layer (selecting and binding connectivity), whereas this is a northbound predictive primitive whose output could feed such a decision. Public TM Forum material (Catalyst project C23.0.515, "Private Optimized Connectivity") describes a NaaS API that lets a third-party application bind to the most optimal broadband connection in real time based on device/customer location — consistent with this "selection and binding" characterization. Assessed as complementary rather than overlapping on that basis. **This remains a preliminary assessment**: TMF759 v5.0's full data model and operations are published to TM Forum members only (no public spec or repository exists), so a field-level comparison has not been possible and is pending review by a TM Forum member on the xFlow side.

#### Portfolio-fit gap analysis (per AP5)

**Gap addressed.** No existing CAMARA API today lets an application forecast expected network QoS along a specific planned route, broken down per segment, before a device travels it. That is the single concrete capability this enhancement adds.

**Already covered by existing APIs — not duplicated:**
- Predictive Connectivity Data already forecasts connectivity/service level for an area or volume over time. This enhancement reuses that model rather than duplicating it, adding a route-shaped input and a per-segment output on top of it.
- Connectivity Insights already reports/alerts on current channel quality at a device's *current* location. It does not forecast for a future or anticipated location along a route, so it does not cover this gap (confirmed with @Eric-Murray / @Kevsy).

**Composed from other APIs — not part of this enhancement's normative scope:**
- QoD — an application may call QoD after receiving a forecast (e.g. to request a session for a segment expected to degrade). The forecast only informs that decision; this API does not invoke QoD.
- Traffic Influence — similarly usable downstream by the calling application; out of this API's scope.

**Explicitly out of scope:** route optimisation/selection and application-level adaptation to the forecast (see "Explicit out-of-scope items" below) — kept out precisely so this remains a single horizontal building block rather than an L4 solution flow.

## Scope change justification

### Why backlog validation is required
The enhancement changes PCD's request/response model: it adds a new input shape (route/corridor vs. polygon or geohash area) and a new output shape (per-segment results in travel order vs. grid cells), plus new numeric fields (latency, throughput, confidence) alongside PCD's existing categorical service levels, and an optional ongoing subscription interaction pattern alongside PCD's one-shot asynchronous callback. These are additive but material changes to the existing API's contract, so Backlog validation is required rather than treating it as a non-normative implementation detail.

### Impact on the existing API scope
This extends the existing API with new functionality; it does not require a new repository or a broader API family. Concretely:
- adds route/corridor as an alternative input type to the existing polygon/geohash area input;
- adds a per-segment result array (in travel order) as an alternative output shape to the existing grid-cell output;
- adds optional numeric latency/throughput/confidence fields alongside the existing categorical service-level model;
- adds an optional forecast-change subscription, distinct from and in addition to PCD's existing one-shot asynchronous response callback.

### Explicit out-of-scope items for this enhancement
- Invoking QoD or any other API to act on the forecast.
- Route optimisation or route selection.
- Application-level adaptation to the forecast.

These may appear in supporting material only as examples of how an application could compose this capability with other CAMARA APIs.

## Subscription model (forecast-change notifications)

Two interaction patterns exist and are kept intentionally separate:

1. **Retrieval callback (unchanged PCD pattern).** `POST /retrieve` is a stateless, one-shot request: it returns a per-segment forecast for the submitted route directly in the response. Nothing is stored server-side and no resource identifier is issued. This is **not** a subscription.
2. **Forecast-change subscription (new in this enhancement).** A standing resource, created via `POST /subscriptions`, that notifies the caller when a previously-returned forecast changes materially for a route the caller already queried. Managed like any other CAMARA subscription resource: `POST`/`GET /subscriptions`, `GET`/`DELETE /subscriptions/{subscriptionId}`.

The subscription design follows the CAMARA/Commonalities explicit subscription model:

- **Event types** — versioned, reverse-DNS-style, per Commonalities convention: `org.camaraproject.route-qos-prediction.v0.qos-degradation-forecast`, `...qos-recovery-forecast`, `...prediction-expired`. A subscriber selects one or more via `types`.
- **Filtering / scoping** — `SubscriptionDetail.route` is mandatory and scopes the subscription to a specific route. Optional refinements: `qosRequirements` (thresholds that define what counts as a "change"), `segmentIds` (restrict to specific segments only), and `area` (an additional circular geofence).
- **Lifecycle** — created by `POST`, enumerable/readable via `GET`, explicitly cancelled via `DELETE`. Bounded either by time (`subscriptionExpireTime`) or by event count (`subscriptionMaxEvents`); `initialEvent` optionally fires one event reflecting current state at creation time, so subscribers don't need a separate first retrieval call.
- **Notification payload** — delivered to the subscriber's `sink` as a CloudEvents 1.0 envelope (`application/cloudevents+json`), consistent with Commonalities notification guidance. The typed `data` object (`EventData`) carries `subscriptionId`, `segmentId`, `location`, `predictedLatencyMs`, `confidenceLevel`, and `expectedAt` — no more than the base retrieval response already exposes.
- **Security** — sink delivery is authenticated via `sinkCredential` (`ACCESSTOKEN` / bearer). Subscription management uses its own OAuth2 scopes (`route-qos-prediction:subscriptions:read` / `:write`), kept separate from the base forecast scope (`route-qos-prediction:read`) so a client can be granted retrieval access without subscription management access, or vice versa.
- **Error handling** — reuses the standard CAMARA `ErrorInfo` model (`status`/`code`/`message`) via the generic 400/401/403/404/409/415/422/429 responses already used elsewhere in the API; `409 CONFLICT` covers a duplicate/conflicting subscription request.
- **Data minimisation** — subscription filtering state is limited to the route the caller already submitted; notifications carry predicted values and confidence per segment, not raw device identifiers. This is consistent with the base retrieval flow, where `deviceId` is optional and only used best-effort.

This model is already implemented in `route-qos-prediction.yaml` (`/subscriptions`, `/subscriptions/{subscriptionId}`, and the `SubscriptionRequest` / `Subscription` / `SubscriptionDetail` / `EventType` / `CloudEvent` schemas) — this section documents it for Backlog review rather than proposing new design.

## Technical viability
The forecasting capability relies on network analytics functions already assumed by PCD (e.g. network data-analytics capabilities such as 5GC NWDAF-class functions, or equivalent MEC/edge-based predictive analytics), extended to accept a route/corridor and to segment the forecast along it. A Transformation Function or equivalent adapter maps the underlying analytics source to the CAMARA northbound contract, consistent with how PCD itself is realised today.

## Commercial viability
An OpenAPI definition (`route-qos-prediction.yaml`) has been produced and is lint-clean against the CAMARA Commonalities ruleset. Supporting material referencing connected-mobility deployments (e.g. edge/MEC-based smart-mobility projects) is available as background for the composition use cases described above; these are cited as motivating context and are not themselves CAMARA-conformant reference implementations.

## YAML code available?
YES — `documentation/SupportingDocuments/route-qos-prediction.yaml`, lint-clean against the CAMARA Commonalities ruleset.

## Validated in lab/productive environments?
NO — not yet validated in a lab or production network environment. *(xFlow: please correct this if a lab validation has since been run.)*

## Validated with real customers?
NO

## Validated with operators?
NO

## Supporters in API Backlog Working Group
List of supporters.
*NOTE: That shall be added by the Working Group.*
