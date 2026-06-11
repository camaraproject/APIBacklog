# API Proposal Template
This template captures all the information that a partner should fill out when proposing a new API (or API family) to CAMARA.

> **Important**
> Before submitting a new API proposal, proposal owners shall review the CAMARA [Project Charter](https://github.com/camaraproject/Governance/blob/main/ProjectCharter.md), in particular the sections related to CAMARA scope.
>
> CAMARA scope is limited to telco APIs exposed as **customer-facing northbound APIs**. Only **Service APIs** and **Service Management APIs** are in scope. **Operate APIs** and **east-west / federation / roaming APIs** are out of scope.
>
> If there is any doubt regarding scope fit, the proposal owner shall justify it explicitly in the sections below with reference to the Project Charter.

### API family name  
Name of the API or API family.

### API family owner  
Company submitting the API proposal.

### API summary  
High level description / scope of the API or API family, and two/three examples of in-scope business cases.

### CAMARA scope alignment

#### Northbound API type  
Select the CAMARA northbound API type for this proposal:
- [ ] Service API
- [ ] Service Management API

#### Scope fit with CAMARA  
Explain why this proposal is in scope for CAMARA, with explicit reference to the [Project Charter](https://github.com/camaraproject/Governance/blob/main/ProjectCharter.md).

#### Telco capability exposed  
Describe the telco network capability, or telco-supporting capability, that is abstracted / exposed by this proposal.

#### Overlap with existing CAMARA APIs  
- [] The CAMARA API portfolio has been reviewed, and it has been confirmed that there is no overlap.  

#### Explicit out-of-scope items for this proposal  
List related capabilities, features, or functions that are explicitly out of scope for this proposal.

#### Proposal owner declaration  
- [ ] I confirm that this proposal has been reviewed against the current CAMARA Project Charter scope.

### Technical viability  
Identify the underlying network/cloud capabilities which are needed for the support of this API or API family, relating these capabilities to standards maturity.  
*Example: this API requires the availability of NEF with this Rel-15 "X" feature.*

### Commercial viability  
Specify the availability of commercial or (industrialized) open-source solutions for the identified network/cloud capabilities.  
*NOTE: If open-source, provide a publicly available reference/link to the actual solution, and specify the version under consideration.*

### YAML code available?  
YES / NO.

### Validated in lab/productive environments?  
YES / NO.  
If YES, specify if it was lab network or productive network.

### Validated with real customers?  
YES / NO.  
If YES, specify how many customers participated in the evaluation, and what their use cases were.  
*NOTE: It is not mandatory (though recommendable) to specify the name of the customers.*

### Validated with operators?  
YES / NO.  
If YES, specify how many operators participated in the evaluation.  
*NOTE: It is not mandatory (though recommendable) to specify the name of the operators.*

### Supporters in API Backlog Working Group  
List of supporters.  
*NOTE: That shall be added by the Working Group. Supporting an API proposal means that the supporting company must provide at least 1 (one) Maintainer at the time of the Sub Project creation.*