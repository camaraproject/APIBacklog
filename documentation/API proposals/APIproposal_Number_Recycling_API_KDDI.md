# APIproposal_Number Recycling API_KDDI

| **Field** | Description | 
| ---- | ----- |
| API family name | Number Recycling |
| API family owner | KDDI |
| API summary | To know whether a phone number is linked to a subscriber, the Number Recycling API can be used to check whether the subscriber of the phone number has changed. <br>A common scenario is when a fraudster obtains a phone number that previously belonged to another person who did not properly deactivate or verify it. The fraudster can then use this number to commit identity theft or engage in fraudulent activities, such as obtaining access codes for accounts associated with that number. In some cases, fraudsters may also attempt to use services or avoid charges by leveraging old, no longer used numbers that were previously used by other users.|
| Technical viability | This API is applicable for 4G and 5G devices and not dependent on specific network functions or cloud capabilities.|
| Commercial viability | Check whether there has been a change in the subscriber associated with the specific phone number after the specified date. <br>Also, enterprise/app service providers want to prevent mis-delivery before sending messages to customers. <br>Furthermore, the enterprise may authenticate the user using SMS-OTP/phone as a means of account recovery. If the specific phone number is canceled and someone else is using it, the enterprise wants to prevent it from being reset. <br>Option 1: Response regarding whether there will be changes from the specified date <br>Input: MSISDN, Specified Date ("value": "2019-01-15") <br>Response: Boolean (True/False - Contract change) <br>Option2: Response regarding the start date of the current contract <br>Input: MSISDN <br>Response: Contract Start Date|
| YAML code available? | NO. <br><em> To be provided. </em> |
| Validated in lab/productive environments? | NO. |
| Validated with real customers? | NO. |
| Validated with operators? | NO. |
| Supporters in API Backlog Working Group | DT, Vodafone <br><em> NOTE: That shall be added by the Working Group. </em> |
