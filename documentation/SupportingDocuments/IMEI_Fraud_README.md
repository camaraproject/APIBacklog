# IMEI Fraud Check API Proposal

## Summary
The **IMEI Fraud Check API** enables applications to verify the authenticity and fraud status of mobile devices using their International Mobile Equipment Identity (IMEI).  
It helps identify whether a device is reported as **lost, stolen, blacklisted, blocked, fraud, non-payment, regulatory** in operator or global equipment databases.

This API enhances trust and security in device trade-ins, insurance verification, and consumer marketplaces.

## Motivation
Device fraud and theft are major challenges for operators, OEMs, and businesses involved in mobile device resale and insurance.  
Operators maintain equipment registries (EIR, DHC, etc.) that contain this information, but these systems are not easily accessible to external applications.  

The IMEI Fraud Check API standardizes this access through a **CAMARA-compliant exposure model**, allowing authorized partners to verify device legitimacy securely.

## Goals
- Provide a simple, standardized API to check device fraud/blacklist status.
- Ensure privacy and compliance with regulatory frameworks.
- Promote interoperability between operators, OEMs, and third-party services.

## Status
🚀 Proposal submitted to **CAMARA API-Backlog Working Group**

## Version
Draft vwip

## Related APIs
- [Device Identifier API](https://github.com/camaraproject/DeviceIdentifier)
- [Device Status API](https://github.com/camaraproject/DeviceStatus)
