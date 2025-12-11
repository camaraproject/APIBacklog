
### API family name  
Radio signal strength API (for rainfall analysis  use cases)

### API family owner  
Ericsson

### API summary  
The API exposes microwave link endpoints, carrier frequencies and the current attenuation level  for a given geographical area. Furthermore, the API provides near real-time rainfall data by leveraging radio links in the operator's network, which can be affected by rain.

The API may be used to estimate rain intensity over a given geographical area. Each CSP's microwave link has fixed coordinates which are the endpoints of a signal that fluctuates due to rain intensity. Rain absorbs the microwave signal energy in a deterministic manner for a given frequency. 

API Consumer can convert a link's attenuation in dB into mm/h of rain intensity and incorporate these sources into its rain geographical model.


### Technical viability  

Coverage proven by existing Ericsson microwave information sources. 
API exposes a streamed data source of dB attenuation per microwave link. Each link has a set frequency & 2 fixed geographical coordinates. Endpoints can be obfuscated by means of deviations of exact coordinates, to be discussed with operators in Camara.


### Commercial viability  
Service is in commercial operation already in some areas leveraging deployed microwave infrastructures.

The API can complement other data sources such as weather stations, radar and satellites. Also, it can be used for weather forecasting and to  improve the rain models.
Depending on links density and topology, a better spatial resolution can be achieved compared to normal weather radars. A better update frequency (e.g. every 10seconds) can be achieved. 

Weather information is needed for manned and unmanned flight management systems. Especially for drones on lower altitudes, ground radars have problems with the curvature of the earth. No other good source for rain intensity exists below 5000 feet. 

35% of drone flights don't take place because of weather uncertainties. This API can improve the data.


### YAML code available?  
NO.

### Validated in lab/productive environments?  
YES, productive environment 

### Validated with real customers?  
YES, with 2 universities and 2 weather companies

### Validated with operators?  
YES, with 2 operators

### Supporters in API Backlog Working Group  
List of supporters.  
*NOTE: That shall be added by the Working Group. Supporting an API proposal means that the supporting company must provide at least 1 (one) Maintainer at the time of the Sub Project creation.*
