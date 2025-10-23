
# IMEI Fraud Check API Proposal

## API family name
IMEI Fraud Check API

## API family owner
xFlow Research — Ali Iqbal

## API summary
The IMEI Fraud Check API enables clients to verify the authenticity and fraud status of mobile devices by querying operator-managed IMEI registers.  
These registers may include:

- **Allowed lists** — devices authorized for network use  
- **Prohibited lists** — devices blacklisted due to theft or fraud  
- **Tracked lists** — devices under investigation or monitoring  

### Example business cases
- Prevent activation of stolen or blacklisted devices  
- Enable device verification during resale, insurance, or repair  
- Support fraud detection and risk management for enterprises and operators  

## Technical viability
This API leverages IMEI information maintained by Mobile Network Operators (MNOs).  
It requires access to operator systems that store device identity data and fraud status indicators.  

The technical feasibility depends on MNOs’ ability to expose IMEI registry data through NEF or equivalent network exposure functions.  
For example, this may require integration between NEF and the Equipment Identity Register (EIR) or GSMA IMEI Database.  

*Example reference:* Requires MNO exposure of IMEI registry data through standardized interfaces (e.g., NEF → EIR).

## Commercial viability
Customer demand for IMEI verification has been validated, particularly among device resellers, insurers, and fraud prevention platforms.  
Commercial and industrialized solutions exist for IMEI registry management (e.g., GSMA’s IMEI Database), which can be integrated with this API framework.  

*Version under consideration:* To be defined during the implementation phase.

## YAML code available?
**YES**

## Validated in lab/productive environments?
**NO**

## Validated with real customers?
**NO**

## Validated with operators?
**NO**

## Supporters in API Backlog Working Group
*(To be filled in by the Working Group. xFlow Research expresses readiness to provide at least one Maintainer at the time of Sub Project creation.)*
