# API Scope Enhancement

| **Field** | Description | 
| ---- | ----- |
| API name | [DeviceStatus](https://github.com/camaraproject/DeviceStatus) |
| New API name | NetworkInfo |
| Scope Enhancement owner | Vodafone |
| Scope Enhancement summary | Read-only API to return the name of the operator and network type for an identified network-connected device. Business cases (1) developers can account for the different behaviours they have historically encountered from different network operators (2) developers can determine if the connection is to a virtual operator, which may result in different network capabilities (3) knowing the type of the network the device is connected to (cellular network type, fixed/Wi-Fi, satellite) allows the developer to better estimate network stability. Overall each business case can help improve end user experience|
| Technical viability |  Operator name is static, connection type is available from via NEF. 
| Commercial viability | Server implementations not known - but MNC/MCC lookup available on the UE via programmatic lookup to OS libraries.|
| YAML code available? | YES |
| Validated in lab/productive environments? | NO. |
| Validated with real customers? | NO.|
| Validated with operators? |NO.  |
| Supporters in API Backlog Working Group | Vodafone, Deutsche Telekom  |
