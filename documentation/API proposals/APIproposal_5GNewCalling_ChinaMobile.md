# 5G New Calling

| **Field** | Description | 
| ---- | ----- |
| API family name | 5G New Calling |
| API family owner | China Mobile |
| API summary |5G New Calling introduces a richer feature set beyond traditional voice and video calls. For example, it can convert spoken words into text and display it on the user's screen or directly send text to the user, etc. These features can be categorized based on their network requirements: those based on voice/video call and those requiring IMS Data Channel (DC, specified in 3GPP TS 26.114, TS 23.228 and GSMA NG.134), and the latter also necessitates terminal support for IMS DC. Although 5G New Calling could provide a rich variety of functions, at present, we hope to focus on a typical usage scenario first. Therefore, in this API family, we will focus on providing APIs for both voice/video call-based and IMS DC-based "AI Translation". Specifically, it mainly includes APIs for establishing a basic 5G New Calling connection and APIs for invoking the "AI translation" service.<br><br>Here is the example use case:<br>AI Translation: Enterprises can provide AI-based translation services for cross-language communication and assist the hearing impaired in scenarios where there is a language barrier. When a user subscribed to AI translation initiates a call, the operator network will notify the enterprise of the call initiation event through a call event notification API. At this point, the enterprise can instruct the operator network to initiate AI translation for the call via the AI translation function invocation API. Upon receiving the enterprise's request, the operator's network translates the user's voice into the specified language and displays the translated subtitles to the user in real time.|
| Technical viability | This API requires the MNO's network to support audio and video calls based on VoLTE and VoNR. If IMS DC-based "AI Translation" is to be used, it also requires the MNO's  network to support "IMS Data Channel" feature of Rel-18 and Rel-19.|
| Commercial viability | This API provides Brand/Vertical service provider with the ability to establish/modify/terminate 5G new calling service.|
| YAML code available? | NO.|
| Validated in lab/productive environments? | YES. <br>China Mobile has conducted pilot validations on  productive environments.|
| Validated with real customers? | NO.<br> China Mobile only has validated with pilot users.|
| Validated with operators? |  YES.<br> China Mobile has conducted pilot validations.|

