### API name
Eligibility Info

### API family owner  
AT&T, T-Mobile, Verizon

### API summary  
The Eligibility-Info/Check or the Pre-flight API enables API consumers to determine whether a subscriber is eligible for one or more service API scopes and a purpose. A single request can check eligibility across multiple scopes and multiple APIs simultaneously. Each scope receives an independent eligibility determination in the response. The response also returns an eligibilityResponseId — a short-lived token that can be passed as a request header (x-eligibility-response-id) in subsequent service API calls, allowing downstream providers to skip redundant validation, reduce end-user friction, and prevent failed API calls.

### Technical viability  
Scope-to-product mapping — The operator must maintain a mapping of CAMARA API scopes (e.g., number-verification:verify) to internal service eligibility rules. This is an operational configuration, not a network standards requirement. The eligibility check can be performed in the context of a registered application, enabling application-level eligibility rules.

### Commercial viability  
This API is already deployed and serving production traffic at T-Mobile. 

### YAML code available?  
YES 

### Validated in lab/productive environments?  
YES 

### Validated with real customers?  
YES 

### Validated with operators?  
YES 

### Supporters in API Backlog Working Group  
AT&T, T-Mobile and Verizon.
