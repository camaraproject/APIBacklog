# API Scope Enhancement Template

This template captures all the information that a partner should fill out when proposing a scope enhancement for an existing CAMARA API.

## API name  
[Consent Info](https://github.com/camaraproject/IdentityAndConsentManagement/tree/main) 

## New API name  
No new name proposed at this stage. The enhancement is considered an evolution of the existing Consent Info API or could be a new API, to be decided during design phase. 

## Scope Enhancement owner  
Telefónica

## Scope Enhancement summary  
This scope enhancement aims to extend the capabilities offered by the existing **Consent Info API** to support a more flexible and user-friendly mechanism for **consent capture**, referred to as controlled delegation. 

Under the current implementation, the end-user provides consent directly through operator-managed channels or web interfaces. The proposed enhancement introduces the possibility for **trusted developers or aggregators** to present the consent interface within their own applications, using the consent texts and parameters provided by the operator. 

The operator remains fully responsible for consent registration, storage, and lifecycle management (including audit, traceability, and opt-out). The enhancement focuses on improving user experience and enabling new types of consent-driven interactions while maintaining operator control and compliance with privacy regulations. 

**In-scope business cases include**: 
- **App managed UX consent capture**: Developers collect end-user consent within their own app, their own look&feel and being free to choose the best moment to collect it by using operator-provided texts to later submit the use’s response. 
- **Integrated onboarding**: Consent capture is embedded within customer registration, verification flows or any other flow the developer may find most suitable, avoiding redirections to external operator portals. 
- **Consent renewal campaigns**: Applications can trigger consent renewal campaigns in their own interface while ensuring operator-level registration.

## Technical viability  
The proposed enhancement builds upon the existing Consent Info framework and its relationship with operator consent management systems. 

It reuses the existing operator infrastructure (Consent Master) for consent validation, registration, and transparency, while adding a new controlled mechanism for capturing consent externally via developer applications. 

Further analysis is ongoing regarding the secure identification and authentication of the subscriber during delegated consent capture. The proposal does not depend on any new 3GPP or TMForum feature, but aligns conceptually with identity and privacy control principles under development in the ICM scope. 

## Commercial viability  
The enhancement responds to developer and enterprise demand for smoother consent collection processes and reduced user friction in digital journeys. 

It also aligns with current commercial deployments of consent management systems across operators, which can be extended to support delegated consent registration. 

Several operators are already evaluating integration with trusted developers and aggregators under privacy-compliant frameworks. No dependency on commercial third-party technology is identified at this stage. 

## YAML code available?  
NO 

## Validated in lab/productive environments?  
Initial feasibility assessments and simulated flows have been conducted internally to validate integration feasibility with operator consent managers.

## Validated with real customers?  
Evaluation with selected customers is planned after initial review and alignment across operators.  

## Validated with operators?  
To be validated.

## Supporters in API Backlog Working Group  
To be confirmed.
