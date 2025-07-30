---
title: API Proposal_Communication Risk Check

---

| **Field** | Description | 
| ---- | ----- |
| API family name | Fraud Hotzone Report |
| API family owner | Chunghwa Telecom |
| API summary | This API analyzes recent SMS activity patterns for a suspected fraud victim's phone number. It detects anomalies based on adaptive AI models, taking into account fraud-prone countries or regions (fraud hotzones) specified by the user. The result helps determine whether the observed behavior indicates potential high-risk fraudulent targeting within the given lookback period. |
| Technical viability | This API utilizes call and SMS activity data retrieved from mobile core network sources (e.g., IMS information) and applies our custom-designed adaptive AI algorithms, along with other detection methods, to identify abnormal communication behaviors associated with fraud hotspots and determine the dates on which such anomalies occurred. 
| Commercial viability | In current situation many scam organizations use phone call and SMS interactions to carry out fraudulent activities. <br><br> Challenges in Anti-Fraud Application Design:<br> •Accurately identifying whether a target number is high risk is difficult.<br> •Anti-fraud applications can only make educated guesses based on limited scenarios.<br><br>We propose the Communication Risk Check API, which provides anti-fraud indicators of target phone numbers. This enables anti-fraud applications to assess the risk from two perspectives: detecting potential scammers and protecting potential victims.|
| YAML code available? | NO. |
| Validated in lab/productive environments? | NO. |
| Validated with real customers? | NO.  |
| Validated with operators? | NO. |
| Supporters in API Backlog Working Group | Chunghwa Telecom |
