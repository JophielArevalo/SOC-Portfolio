# Splunk Security Monitoring – Project Summary

This project demonstrates my ability to perform **SOC-level log analysis**, threat detection, and incident investigation using Splunk Enterprise. It includes hands-on work with web server logs, SMTP email logs, geolocation analysis, dashboard creation, and a complete incident response plan.

---

## 🔍 Project Objectives
- Detect suspicious activity using SPL (Splunk Processing Language).
- Investigate insider threats, attempted credential harvesting, and unauthorized access.
- Use HTTP and SMTP logs to reconstruct security incidents.
- Build dashboards to visualize threats in real time.
- Produce an Incident Response Plan aligned with SOC workflows.

---

## 📁 Project Contents
This folder includes:

- **report.pdf** – Full analysis and written investigation.
- **splunk-queries.txt** – All SPL queries used.
- **dashboard-screenshots/** – Panels, geolocation maps, anomaly charts.
- **incident-response-plan.pdf** – A structured IR plan based on the findings.
- **summary.md** – (This file) Overview of the project.

---

## 🧠 Key Investigations Performed

### **1. Unauthorized Access Attempts**
Used Splunk to identify the top offending IPs, associated user agents, and geolocation of suspicious traffic.

### **2. Website Activity & Visitor Mapping**
Identified the top countries visiting the site and the top countries attempting unauthorized access using `iplocation`.

### **3. Insider Threat Detection**
Analysed SMTP logs to detect:
- Unusual sender `Return_path` values  
- Rare email behaviours  
- Suspicious attachment transfers  
- Potential HR‑related misuse

### **4. Threat Indicators (XSS + Credential Harvesting)**
Detected:
- Injected `<script>` payloads  
- `document.cookie` access  
- Requests sent to attacker infrastructure  
- Suspicious `POST` login attempts

### **5. Productivity & Bandwidth Abuse**
Flagged spikes in data consumption and correlated them with high‑volume web browsing destinations.

### **6. Outage / DoS Timeline Analysis**
Used timechart visualisations to determine error‑rate spikes during the downtime window.

---

## 🧩 SPL Queries Used
All queries are stored in `splunk-queries.txt`, including:

- Top unauthorized IPs  
- Rare senders (insider threat)  
- Geolocation analysis  
- Auth failure detection  
- XSS indicators  
- Bandwidth analysis  
- DoS status code comparison  
- Maintenance downtime duration  
- Most‑viewed product detection  

These demonstrate proficiency with:
- `stats`, `top`, `sort`, `rare`, `transaction`
- `iplocation`
- `eval`, `timechart`
- Custom field extraction

---

## 📊 Dashboards Created
The dashboard panels (screenshots in `/dashboard-screenshots`) include:

- Single-value KPIs  
- Unauthorized access attempts  
- Geolocation map (country hotspots)  
- XSS detection indicators  
- Email abuse monitoring  
- DoS trend timeline  
- Browser/user-agent overview  

These were built using custom SPL searches and visualisations.

---

## 📄 Incident Response Plan
A complete IR plan is included (`incident-response-plan.pdf`), covering:

1. Preparation  
2. Identification  
3. Containment  
4. Eradication  
5. Recovery  
6. Lessons Learned  

This document converts Splunk findings into a structured SOC response workflow.

---

## 🛠️ Skills Demonstrated
- SOC Tier 1 / Tier 2 investigation workflows  
- SPL search writing  
- Log parsing & enrichment  
- Threat detection & analysis  
- Dashboard design  
- Incident response planning  
- Email & web log forensics  
- Geolocation & anomaly detection  

---

## ✅ Conclusion
This Splunk project showcases my ability to investigate multi‑layered security incidents using logs, dashboards, and structured SOC methodologies. It highlights not only technical SPL skills but also analytical thinking, incident reconstruction, and the ability to communicate findings in a real-world security operations context.
