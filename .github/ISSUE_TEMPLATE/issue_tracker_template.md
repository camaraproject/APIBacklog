---
name: API Repository Onboarding Tracker ⛴️
about: Use this template after a new API repository is approved to track onboarding steps.
title: '[Onboarding Tracker] $repo_name$'
labels: 'API Onboarding Tracker'
assignees: ''
---
<!-- API & Repository Onboarding Tracker -->

## API Repository Information
- **API Repository Name:** XXXX  
- **Sub Project (or "Independent"):** XXXX  
- **Mailing List:** XXXX  
- **Repository:** XXXX  
- **Wiki Page:** XXXX  
- **API Owner:** TBD  
- **API Proposal:** https://github.com/camaraproject/APIBacklog/blob/main/documentation/XXXX.md  
- **Original Approval Issue:** https://github.com/camaraproject/APIBacklog/issues/XXXX  

> ⚠️ Progress to the next gate only after completing all items in the current one.

---

## GATE 0 – Codeowner Validation (must be completed before repository creation)

- [ ] Code owner(s) **nominated and confirmed** by API Backlog WG  
- [ ] **LF account** active and **Confluence access** granted  
- [ ] Subscribed to `all@lists.camaraproject.org`  
- [ ] **GitHub account** active with notifications enabled  
- [ ] Invitation to **CAMARA GitHub Organization** accepted  
- [ ] **EasyCLA** validation successfully completed via **test PR** in `camaraproject/EasyCLA`  

> Once all items are complete, repository creation can proceed.

---

## GATE 1 – Repository Onboarding (infrastructure established)

- [ ] Update `APIBacklog.md` with status: `Onboarding`  
- [ ] Request **wiki page** and **mailing list** (email `support@camaraproject.org`, specify details)  
- [ ] Confirm **mailing list creation** (only if Independent Sandbox) _(LF Admin)_  
- [ ] Confirm **wiki page creation** _(LF Admin)_  
- [ ] **Repository created** _(LF Admin via automation)_  
- [ ] Add repository link to the API wiki page _(LF Admin)_  
- [ ] Update `README.md` in the repository with API details _(API owner)_  
- [ ] File issue in **Marketing repo** to update CAMARA website and presentation deck  
- [ ] Update `APIBacklog.md` with status: `Onboarded`  
- [ ] (Optional) Nominate initial **Maintainers** _(API owner)_  
- [ ] (Optional) Submit PR to update `MAINTAINERS.md` and `CODEOWNERS`  

---

## GATE 2 – Initial Codeowner Tasks (first activities within the repository)

- [ ] Confirm that the `CODEOWNERS` file is correct and up to date  
- [ ] Update the **Scope** section within `README.md` to reflect the agreed API purpose  
- [ ] Create the **first GitHub issues** (e.g. for drafting the initial API specification or defining next milestones)  
- [ ] Announce the start of development and share planned next steps via the API mailing list  

**Additional for new Independent Sandbox repositories:**  
- [ ] Agree on a **regular meeting schedule** with your team (via mailing list or initial call)  
- [ ] Request a **meeting link** from `support@camaraproject.org` to be added to your recurring calendar invite  
- [ ] Review and update the **repository wiki page** accordingly  

---

**Notifications:**  
CC: @camaraproject/admins @camaraproject/api-backlog_maintainers @camaraproject/marketing_maintainers