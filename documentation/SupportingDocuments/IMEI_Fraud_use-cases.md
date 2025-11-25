# IMEI Fraud Check API – Use Cases

## 1. Trade-In Device Validation
Retailers and device refurbishers can use the IMEI Fraud Check API to confirm that a device offered for trade-in is not stolen, blacklisted, or reported as fraudulent.

**Flow:**
1. Customer provides device IMEI.
2. Retailer system calls IMEI Fraud Check API.
3. API returns `fraudStatus: Allowed` or a relevant flag.
4. Retailer accepts or rejects trade-in based on response.

---

## 2. Insurance Claim Verification
Insurance providers can use this API to validate a device’s fraud status before approving or renewing a policy or processing a claim.

**Example:**  
If a policyholder claims loss for an IMEI already reported as stolen before policy activation, the claim can be flagged for fraud investigation.

---

## 3. Marketplace Fraud Prevention
Consumer-to-consumer marketplaces (e.g., device resale platforms) can use the API to ensure listed devices are legitimate.

**Example:**  
Before publishing a listing, the marketplace app checks the IMEI via the API to ensure it’s not on the stolen or blacklisted list.

---

## 4. Regulatory or Customs Enforcement
Telecom regulators or customs systems can verify imported device IMEIs to detect grey-market or stolen devices.

---

## 5. Operator Self-Service
Operators themselves may expose this API to subscribers who want to check the status of their own devices for authenticity verification.
