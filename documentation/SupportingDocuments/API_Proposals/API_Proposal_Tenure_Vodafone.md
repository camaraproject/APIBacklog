| **Field** | Description | 
| ---- | ----- |
| API family name | Tenure |
| API family owner | Vodafone |
| API summary | Establish a level of trust against mobile ID by verifying the length of tenure for a mobile user bound to a mobile number; tenure means the period of time a MSISDN has been associated with a specific user. API checks whether the lifetime tenure of a given MSISDN is longer than an input date.<br><br>[Use Case]: Enterprises can use Tenure API to gauge and establish a level of trust (or Trust Score) with a mobile user who is associated with a specific mobile number, based on how long they have been associated with that number. |
| Technical viability | The data for this API comes from backend systems/sources (i.e. CRM). 
| Commercial viability | To Establish level of trust (or Trust Score) against a mobile ID (MSISDN). The Tenure API will return a True or False answer as to whether the customer's tenure with an operator has been longstanding.<br><br>[Example]: Customer submits MSISDN to understand if the mobile number has been registered to a CSP for longer than a specific date. <br><br>* Sample Request: {"tenure_before_date":{"value": "2019-01-15"}} <br>* API   Response: True/False -  if tenure is longer than specified date + billing segment  (PAYG/PAYM/Business) <br>* Sample   Response: "tenure_before_date_check":   true,    "billing_segment":   "PAYM" |
| YAML code available? | YES |
| Validated in lab/productive environments? | YES |
| Validated with real customers? | YES - TMT Analysis |
| Validated with operators? | YES - Telefonica, Hutchinson Group |
| Supporters in API Backlog Working Group | List of supporters - to be added in future. </em> |
