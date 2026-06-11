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
Name of the API or API family whose scope is proposed to be enhanced.  
*(Include link if available)*  

## New API name  
New API name proposed to encompass the new scope (if applies).  

## Scope Enhancement owner  
Company submitting the API enhancement.  

## Scope Enhancement summary  
High level description / scope of the API or API family, and two or three examples of in-scope business cases.  

## CAMARA scope alignment

### Northbound API type  
Select the CAMARA northbound API type for this proposal:
- [ ] Service API
- [ ] Service Management API

### Scope fit with CAMARA  
Explain why the enhanced scope remains in scope for CAMARA, with explicit reference to the [Project Charter](https://github.com/camaraproject/Governance/blob/main/ProjectCharter.md).

### Telco capability exposed  
Describe the telco network capability, or telco-supporting capability, that is abstracted / exposed by the proposed enhancement.

### Overlap with existing CAMARA APIs  
- [] The CAMARA API portfolio has been reviewed, and it has been confirmed that there is no overlap. 

## Scope change justification

### Why backlog validation is required  
Explain how this proposal modifies the original scope of the API and why it therefore requires API Backlog validation.

### Impact on the existing API scope  
Explain how the current API scope would change. Indicate whether the proposal:
- extends the existing API with new functionality,
- adds a new API in the same repository,
- requires a broader API family scope,
- or may be better handled through a new repository.

### Explicit out-of-scope items for this enhancement  
List related capabilities, features, or functions that are explicitly out of scope for this enhancement.

## Technical viability  
Identify the underlying network/cloud capabilities which are needed for the support of this API or API family, relating these capabilities to standards maturity.  
*Example: this API requires the availability of NEF with this Rel-15 “X” feature.*  

## Commercial viability  
Specify the availability of commercial or (industrialized) open-source solutions for the identified network/cloud capabilities.  
*NOTE: If open-source, provide a publicly available reference/link to the actual solution, and specify the version under consideration.*  

## YAML code available?  
YES / NO.  

## Validated in lab/productive environments?  
YES / NO.  
If YES, specify if it was lab network or productive network.  

## Validated with real customers?  
YES / NO.  
If YES, specify how many customers participated in the evaluation, and what their use cases were.  
*NOTE: It is not mandatory (though recommendable) to specify the name of the customers.*  

## Validated with operators?  
YES / NO.  
If YES, specify how many operators participated in the evaluation.  
*NOTE: It is not mandatory (though recommendable) to specify the name of the operators.*  

## Supporters in API Backlog Working Group  
List of supporters.  
*NOTE: That shall be added by the Working Group.*  
