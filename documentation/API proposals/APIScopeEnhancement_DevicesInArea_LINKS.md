# API Scope Enhancement - Devices in Area Query

## API name

[Device Location](https://github.com/camaraproject/DeviceLocation).

## Scope Enhancement owner

LINKS Foundation.

## Scope Enhancement summary

Enable applications to identify which devices from a known set of authorized devices were detected in a geographical area during a specified time interval, without querying each device individually. The response would return the identifiers of the matching authorized devices.

Example use cases:
- **Fleet management:** identify which connected vehicles were detected in a specific area during a given period.
- **Managed IoT:** identify which authorized connected assets were detected within an operational area.

## CAMARA scope alignment

### Northbound API type

- [x] Service API
- [ ] Service Management API

### Scope fit with CAMARA

The proposal exposes a location-related capability to applications through a customer-facing northbound Service API, consistent with the [CAMARA Project Charter](https://github.com/camaraproject/Governance/blob/main/ProjectCharter.md).

### Telco capability exposed

An area- and time-based query over device-location information available through the network or supporting location services, limited to devices the application is authorized to access.

### Overlap with existing CAMARA APIs

- [ ] The CAMARA API portfolio has been reviewed, and it has been confirmed that there is no overlap.

No directly equivalent capability has been identified among the related APIs reviewed: **RegionDeviceCount** returns aggregated counts, **DeviceVisitLocation** concerns a specified device, and **Geofencing Subscriptions** provides event notifications. Portfolio alignment remains subject to CAMARA review.

## Scope change justification

### Why backlog validation is required

The proposal extends device-centric location capabilities with an area-based query that can return identifiers of multiple authorized devices.

### Impact on the existing API scope

This would enhance the Device Location scope without changing existing device-specific operations. Whether the functionality belongs in an existing API or a related API can be discussed with the Sub-Project maintainers.

### Explicit out-of-scope items for this enhancement

- Identifying or disclosing devices outside the authorized set.
- Defining a new general-purpose group-management or authorization system.
- Geofencing event subscriptions, addressed by a separate proposal.

## Technical viability

An initial implementation was developed and tested in the ENVELOPE Italian trial site, using an outdoor private 5G SA network with real smartphones and on-board units (OBUs).

Supporting this capability requires access to device location observations for the requested time interval, including historical data, and appropriate access controls.

A CAMARA-aligned mechanism to determine the authorized device set and apply the relevant consent requirements remains to be defined and was not implemented in the research prototype.

## Commercial viability

The ENVELOPE implementation is a research prototype. Commercial availability of this specific functionality has not been established. Availability of production-grade location services and suitable authorization mechanisms for commercial deployments remains to be assessed.

## YAML code available?

Yes, a draft OpenAPI specification is available for discussion. It is not yet a final CAMARA-compliant specification.

## Validated in lab/productive environments?

Yes, in a research testbed. Tested on the ENVELOPE outdoor private 5G SA network with real devices; not validated in a commercial production network.

## Validated with real customers?

No commercial customer validation claimed. Evaluations involved participants in the ENVELOPE project.

## Validated with operators?

No operator-specific validation confirmed for the proposed API.

## Supporters in API Backlog Working Group
