---
name: 🔁 Repository Status Transition Request
about: Request a status change for an API repository (e.g., Sandbox → Incubating, Incubating → Stable)
title: '[Repository Transition]: <API Name>'
labels: 'repository-transition'
assignees: ''
---

## Transition Type

<!-- Please select the type of status change you are requesting by uncommenting the relevant line below -->

<!-- Sandbox → Incubating -->
<!-- Incubating → Stable -->
<!-- Any → Archived -->

---

## Problem description
<!-- A clear and concise description of why this transition is being proposed -->

---

## Expected action

<!-- Confirm that the API meets the required criteria and that approval is being requested -->
<!-- Please keep only the checklist that corresponds to the transition you are requesting. Delete the others to avoid confusion. -->

---

### Checklist for Sandbox → Incubating

#### SubProject Alignment

- [ ] Define if the API will:
  - [ ] Join an existing Sub Project  
    _e.g.:_ https://lf-camaraproject.atlassian.net/wiki/spaces/CAM/pages/123456789/SubProject-Example  
  - [ ] Require creation or expansion of a new Sub Project  
    _If so, has the process for creating the Sub Project been followed or agreed upon?_

#### General Criteria

- [ ] Initial API version released and implemented by at least one operator  
  _e.g.:_ https://opengateway.telefonica.com/apis/device-swap

- [ ] Participated in at least one CAMARA meta-release  
  _e.g.:_ https://github.com/camaraproject/DeviceSwap/releases/tag/r2.2

- [ ] API aligned with Commonalities and ICM guidelines  
  _e.g.:_ https://github.com/camaraproject/DeviceSwap/blob/r2.2/documentation/API_documentation/device-swap-API-Readiness-Checklist.md

- [ ] At least 3 maintainers from 3 different companies listed in `MAINTAINERS.md`  
  _e.g.:_ https://github.com/camaraproject/DeviceSwap/blob/r2.2/MAINTAINERS.md

- [ ] Issue opened in API Backlog WG  
  _e.g.:_ https://github.com/camaraproject/APIBacklog/issues/214

- [ ] Final approval from TSC pending

#### GitHub Repository Tasks

- [ ] Ensure `CODEOWNERS` and `MAINTAINERS.md` are aligned and updated  
- [ ] Update `README.md`:
  - Replace the status badge to "Incubating"
  - Modify intro sentence to reflect maturity
  - Add link to corresponding Sub Project

- [ ] Update GitHub repository topics:
  - Remove: `sandbox-api-repository`
  - Add: `incubating-api-repository`

#### Wiki Tasks

- [ ] Ensure all wiki information is up to date
- [ ] Change maturity label/flag from “Sandbox” to “Incubating”
- [ ] Move the wiki page tree under the appropriate Sub Project space

---

### 📋 Checklist for Incubating → Stable

- [ ] API implemented by at least 2 operators

- [ ] GSMA certification obtained (if applicable)

- [ ] Documentation, YAML, and release materials are production-ready

- [ ] Participated in at least 2 CAMARA meta-releases

- [ ] All required metadata files (`README.md`, `MAINTAINERS.md`, etc.) are complete

- [ ] No major open issues in the backlog

- [ ] Final validation and approval from TSC pending

---

### 📋 Checklist for Archiving Repository

- [ ] API is no longer maintained or used

- [ ] No significant activity in the last 6–12 months (or declared sunset)

- [ ] A formal deprecation or retirement reason is provided

- [ ] Decision acknowledged by API Backlog WG and/or TSC

---

## Additional context
<!-- Add links to API repository, documentation, certifications, previous discussions, or meeting minutes -->
