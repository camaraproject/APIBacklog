IMEI Fraud API submission

| **Field** | Description |
| ---- | ----- |
| API name | IMEI Fraud|
| API owner | MTN - Waseem Amra |
| Initial API Contributors | MTN - Waseem Amra | 
| API summary | This API enables the API Consumer to determine whether fraud has been reported for the connected device. It will use the MSISDN or/ IMEI to check if the associated device has been reported as lost, suspended, stolen, blacklisted. 

Use case – account takeover, online registration  |
| Technical viability | This API uses IMEI info, usually stored by the MNO, to determine whether any fraud logs are associated with the device. 

Input: MSISDN & or IMEI number 

Output:  

Status: e.g. Blocked, lost,stolen, blacklisted etc 
Date_reported:10-01-2023  |
| Commercial viability | Customer demand has been validated |
| YAML code available? | yes Updated yaml provided |
| Validated in lab/productive environments? | No In Commercial network |
| Validated with real customers? | YES – Banks from different markets as part of GSMA fintech stream in SA markets  |
| Validated with operators? | yes South African MNOs will support |
