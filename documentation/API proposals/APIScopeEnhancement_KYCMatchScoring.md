| **Field** | Description | 
| ---- | ----- |
| API family name | KYC_Match Scoring | 
| API family owner | Vodafone - Telefonica |
| API summary |  Current KYC-Match service validates if the information reported by the developer matches with the information that the operator has registered in its systems. Scoring proposal (aka fuzzy logic) is proposed to allow a wider response in which, for the current "false" responses, it will provide a scoring of how close to the actual value is the requested field. <br> E.g. if developer is reporting the name "Clara" while the registered name by operator is "Carla". User may have suffered a typo, and currently the API will directly respond "false", while the scoring mechanism will also report that the requested name is 88% close to the actual name.|
| Technical viability | As API evolution, the only change will be including score as response and the selection of the algorythm used by the operators to calculate the distance between the requested and stored values. Proposals (to be discussed in WG): <br>  - Include score response as optional parameter, to be reported in case the current reported value is not "true" <br> - Only string parameters will include this scoring, since "distance" calculation is not valid for numerical parameters <br> - Normalization of parameters shall be done before algorithm is used to calculate the difference/distance <br> - Algorithm to calculate the distance is proposed to be Jaro–Winkler distance, as tested to be the most valued when differenciating these sets of words/expressions (names, addresses...)|
| Commercial viability | Already in place in some operators enhancing basic true/false mechanism for developers to consume enhanced information, allowing to report useful information for cases that currently are reported directly as "false"| 
| YAML code available? | Yes<br> To be provided  |
| Validated in lab/productive environments? | YES |
| Validated with real customers? | YES |
| Validated with operators? | Yes<br> Over previous service |
| Supporters in API Backlog Working Group | Vodafone - Telefonica |
