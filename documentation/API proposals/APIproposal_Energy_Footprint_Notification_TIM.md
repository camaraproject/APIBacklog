

# API Proposal Energy Footprint Notification



| **Field** | Description | 
| ---- | ----- |
| API family name | Energy Footprint Notification |
| API family owner | TIM |
| API summary | The reference scenario foresees a Service provided by Application instances running in different locations, in the Public or Private Cloud or at the Edge. The Application is onboarded by the Service Provider in a distributed infrastructure managed by a Telco Operator. The Energy Footprint Notification (EFN) API provides the Service Provider with the information about the E2E energy consumption and carbon footprint (CO2 emissions) of the Application instances hosted by the Operator. The reported energy consumption and carbon footprint consider the energy used to run the Application instances in the Data Centers and the energy absorbed along the network to provide the Service (e.g., RAN and Core Network energy consumption).<br>Business Use Case: A Service Provider has requested the Telco Operator to instantiate an Application in different Edge Data Centers. These application instances, altogether, provide a Service offered to End Users via a mobile network. The Service Provider wants to know the E2E energy consumption and CO2 emission of its Service in a certain period of time. A system of the Service Provider invokes the Energy Footprint Notification API to get the above-mentioned information. The reported energy consumption and CO2 emissions consider the energy used to run the Application instances in the Data Centers and the energy consumption along the network to provide the Service (e.g., RAN and Core Network consumption) in the specified period of time.|
| Technical viability | This API can leverage on Rel 18 5G Slice monitoring as defined in 3GPP TS 28.554(5G end to end Key Performance Indicators). The API can also leverage on cloud infrastructure metrics retrieval (e.g. Project Sylva) and analysis</em>. 
| Commercial viability | Under development in IPCEI (www.ipcei-cis.eu).</em>|
| YAML code available? | YES. |
| Validated in lab/productive environments? | NO. |
| Validated with real customers? | NO. |
| Validated with operators? | NO. |
| Supporters in API Backlog Working Group | List of supporters. <br><em> NOTE: That shall be added by the Working Group. </em> |