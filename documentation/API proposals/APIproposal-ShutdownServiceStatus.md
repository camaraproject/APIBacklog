| **Field** | Description | 
| ---- | ----- |
| API family name | Shutdown Service Status |
| API family owner | ChinaUnicom |
| API summary | This API allows users to obtain the current shutdown status of a certain phone number, including Voice/SMS in shutdown, Voice/SMS out shutdown, and data service shutdown.<br>Payment System and Risk Management: In scenarios where payment or identity verification relies on phone numbers, such as e-commerce platforms or financial service providers, this API can be used to verify whether user accounts are functioning properly. This helps to reduce fraud and payment risks, ensuring that only normal accounts can conduct transactions.<br>Customer Service Support: If a user reports that they are unable to receive calls or text messages, customer service personnel can determine whether the problem is caused by the phone voice function being shut down by checking the phone's status. |
| Technical viability | Operators can obtain the shutdown and resumption status of mobile network users by querying the information in the UDM/HSS contracted network element devices of the mobile network. 
| Commercial viability | For use in anti fraud, customer service support and other scenarios|
| YAML code available? | NO |
| Validated in lab/productive environments? | YES , it was in lab network. |
| Validated with real customers? | NO |
| Validated with operators? | YES , one operators participated in the evaluation. |
| Supporters in API Backlog Working Group | China Unicom, China Telecom, Huawei |
