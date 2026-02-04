# Evidence Workflow (Acquisition → Validation → Analysis)

This document captures exactly how evidence was handled to preserve integrity and support repeatability.

---

## 1) Acquisition & Intake
- Received four artifacts (Windows disk image split parts, PCAP, VMEM, Android image).
- Created case structure:
- /cases/
EvidenceA/  # Windows disk
EvidenceB/  # PCAP
EvidenceC/  # Memory dump
EvidenceD/  # Android image

Unpacked ZIP/7z parts and **validated hashes** (e.g., `md5sum`).

## 2) Verification & Mounting
- **Disk (Evidence A)**
- `img_stat`, `mmls` → identify partitions & offset.
- Read‑only mount with calculated byte offset.
- **PCAP (Evidence B)**
- Opened in Wireshark; validated metadata.
- **Memory (Evidence C)**
- Determined profile; prepared Volatility workspace.
- **Android (Evidence D)**
- Loop‑mounted; copied relevant SQLite DBs for analysis.

## 3) Forensic Workflow
- **Windows Disk**
- Registry parsing: SYSTEM, SOFTWARE, SAM (RegRipper).
- Recycle Bin: `$I/$R` correlation; recovered deleted items.
- Passworded ZIP → dictionary crack (for lawful access).
- Hex carving: verified magic numbers; removed junk header bytes where applicable.
- **PCAP**
- Stream follow; conversation stats; FTP/HTTP/S comms review; keyword pivots.
- **Memory**
- `pslist`, `netscan`, `memdump` targeted PID, `lsadump` (secrets).
- **Android**
- Contacts, Calls, SMS: SQLite; review -wal files; browser `History`.

## 4) Timeline Normalization
- All timestamps converted to UTC.
- Wrote normalized events into `timeline.csv` with columns:
    -  source, timestamp_utc, host/device, artifact, action, details
- Cross‑checked for causality and consistency.

## 5) Reporting
- Screenshots exported to `/screenshots`.
- Key artifacts, paths, commands, and findings compiled into `report.pdf`.
