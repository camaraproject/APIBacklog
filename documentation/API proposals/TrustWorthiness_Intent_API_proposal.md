# API Proposal Template

This template captures all the information that a partner should fill out when proposing a new API (or API family) to CAMARA.

### API family name

Name of the API or API family.

CAMARA TrustWorthiness INTENT API.

### API family owner

Company submitting the API proposal.

National Centre for Scientific Research Demokritos (NCSRD)
and Infolysis S.A.

### API summary

High level description / scope of the API or API family, and two/three examples of in-scope business cases.

A Trustworthiness Intent API enabling developers and applications to request and
monitor trust guarantees (security, privacy, reliability, resilience,safety) as
high-level intents without specifying low-level configurations.

### Technical viability

Identify the underlying network/cloud capabilities which are needed for the support of this API or API family, relating these capabilities to standards maturity.  
_Example: this API requires the availability of NEF with this Rel-15 "X" feature._

No network/cloud capabilities required. The API's bussiness logic is supported through an open-source
AI-native trust orchestrator acts as the backend to produce trust scores to feed them in the correspondent network.

### Commercial viability

Specify the availability of commercial or (industrialized) open-source solutions for the identified network/cloud capabilities.  
_NOTE: If open-source, provide a publicly available reference/link to the actual solution, and specify the version under consideration._

An open-source implementation is used called Cognitive Coordinator (CoCo), that is, an AI-native trust orchestrator.
It interprets user trust intents expressed in natural language and translates them into actionable system configurations,
dynamically computing a Level of Trustworthiness (LoT) that aligns with both semantic intent and real-world resource constraints.

This is part of the SAFE-6G European Horizon project. (https://safe-6g.eu/)

### YAML code available?

YES / NO.
YES

### Validated in lab/productive environments?

YES / NO.  
If YES, specify if it was lab network or productive network.

YES, lab network.

### Validated with real customers?

YES / NO.  
If YES, specify how many customers participated in the evaluation, and what their use cases were.  
_NOTE: It is not mandatory (though recommendable) to specify the name of the customers._
NO

### Validated with operators?

YES / NO.  
If YES, specify how many operators participated in the evaluation.  
_NOTE: It is not mandatory (though recommendable) to specify the name of the operators._
NO

### Supporters in API Backlog Working Group

List of supporters.  
_NOTE: That shall be added by the Working Group. Supporting an API proposal means that the supporting company must provide at least 1 (one) Maintainer at the time of the Sub Project creation._
