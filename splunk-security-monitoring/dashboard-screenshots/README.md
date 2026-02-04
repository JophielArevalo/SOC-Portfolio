# Dashboard Screenshots

This folder contains the screenshots of the Splunk dashboard panels created for the *Splunk Security Monitoring* project.  
The dashboard visualisations were built using SPL queries from the investigation and are used to support SOC analysis, threat detection, and reporting.

---

## 📊 What These Screenshots Represent

Each screenshot corresponds to a specific dashboard panel designed to help identify, investigate, and monitor suspicious activity across the HungryHustle environment.

### **1. Unauthorized Access Attempts Panel**
Shows which IP addresses generated the highest number of unauthorized requests.  
Useful for spotting brute-force attempts, malicious scans, and repeated probing.

### **2. Geolocation Map (Successful Visits & Unauthorized Attempts)**
Visualizes traffic by country using `iplocation`.  
Helps identify:
- Suspicious traffic sources  
- Regions associated with attacks  
- Normal vs abnormal activity

### **3. XSS / Suspicious Query Detection Panel**
Detects potential cross-site scripting indicators:
- `<script>` injections  
- `document.cookie` access  
- Requests to attacker infrastructure  

Used to identify web‑application compromise.

### **4. Email Rare-Event Analysis Panel**
Shows rare `Return_path` values and unusual sender/attachment combinations.  
Useful for insider‑threat analysis and SMTP abuse detection.

### **5. DoS / Outage Status Trend**
Timechart showing:
- Normal HTTP 200 responses  
- Error spikes (4xx/5xx)  
- DoS‑like behaviour  

Helps identify the exact window of service disruption.

### **6. Most-Viewed Product Panel**
Highlights the top‑requested product file, excluding non‑product static assets.

---

All visualisations are built from the SPL queries included in  
`splunk-queries.txt`.


