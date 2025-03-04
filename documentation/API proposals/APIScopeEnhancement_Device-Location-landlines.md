| **Field** | Description | 
| ---- | ----- |
| API name | [Location Verification](https://github.com/camaraproject/DeviceLocation) [Location Retrieval](https://github.com/camaraproject/DeviceLocation) |
| New API name | (No name change) Support for fixed landlines |
| Scope Enhancement owner | Telefonica |
| Scope Enhancement summary | Including the support for fixed devices as part of the location services |
| Technical viability | Currently only mobile lines are explicitly or implicitly considered along the Location (verification/retrieval) services in CAMARA. Adding the ability to support landlines is a natural evolution of the APIs, being able to: <br> - Support Fixed Phone Number identifications <br> - Support IP addresses assigned to fixed lines <br> In comparison to mobile lines, the location of fixed lines can be easily deducted based on the installation location, allowing a simple and precise location of those devices connected to the fixed line (and the proper line location).<br>|
| Commercial viability | Users expend extensive periods connected to Wi-Fi networks. Allowing applications to locate users based on their Wi-Fi connection (identified by its IP) will broadly help to enhance the location services. Additionally, for those use cases where the residence is the important identity (e.g. delivery) this enhancement will also help applications ensure the user's location when enabling their services.|
| YAML code available? | YES |
| Validated in lab/productive environments? | YES <br>Productive network. |
| Validated with real customers? | YES |
| Validated with operators? |  NO|
| Supporters in API Backlog Working Group | List of supporters. <br><em> NOTE: That shall be added by the Working Group. </em> |
