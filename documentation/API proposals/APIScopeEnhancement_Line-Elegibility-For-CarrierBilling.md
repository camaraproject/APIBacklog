
| **Field** | Description | 
| ---- | ----- |
| API name | [Carrier Billing CheckOut](https://github.com/camaraproject/CarrierBillingCheckOut) |
| New API name | (New API) Line Elegibility Check for Carrier Billing |
| Scope Enhancement owner | Telefonica |
| Scope Enhancement summary | Including the functionality of elegibility check for Carrier Billing API |
| Technical viability | Operators usually check the subscriber's elegibility when a third party applciation (merchant) requests access to a sensitive service like Carrier Billing. Basically, the operator implements some business rules to enable (or not) a given subscriber to be elegible for a given service. The business rules are specific to each operator and shall be kept as an internal policy. This validation is commonly executed during the proper service consumption, so that an error response is raised if user is not elegible for this service. The proposal is to separate such funcionality in an specific API that can help differencing the proper service execution from the prior elegibility check, taking advantage of the same validations that operators already do in the service. Thus, mechants can customize their paywalls so the "carrier billing" payment option is not presented for those users that are non-elegible.|
| Commercial viability | By validating subscriber's eligibility before execution, applications can improve user experience, reduce operational costs, enhance efficiency, utilize data for future optimization and build customer loyalty. This approach prevents late-stage errors, saves resources, and promotes a smoother, more effective digital service.|
| YAML code available? | No |
| Validated in lab/productive environments? | No |
| Validated with real customers? | YES |
| Validated with operators? |  NO|
| Supporters in API Backlog Working Group | List of supporters. <br><em> NOTE: That shall be added by the Working Group. </em> |
