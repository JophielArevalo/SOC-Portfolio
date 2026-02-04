# Digital Forensics – Case Investigation (Disk, Memory, Network & Mobile)

This investigation reconstructs activity across **four evidence sources**—a Windows disk image, a dorm network packet capture (PCAP), a Windows memory dump, and an Android device image—to determine user identity, exfiltration paths, communications, and a correlated timeline.

---

## 🎯 Objectives
- Preserve evidence integrity (hashing, chain of custody).
- Mount and analyze disk partitions; parse registry hives; recover deleted files.
- Reconstruct conversations and transfers from PCAP (Wireshark).
- Enumerate live processes, sockets, and secrets from a memory dump (Volatility).
- Extract contacts, calls, SMS, and browser artifacts from Android SQLite DBs.
- Produce a single **timeline** correlating events across all sources.

---

## 📁 Folder Contents
- **report.pdf** — Full, annotated investigation report with screenshots and references.
- **evidence-workflow.md** — Acquisition, verification, mounting, and toolchain steps.
- **screenshots/** — Selected figures (hex carving, Volatility outputs, PCAP streams).
- **timeline.csv** — Normalized timeline (UTC) across all evidence.
- **summary.md** — (This file) Executive overview for recruiters.

---

## 🧩 Key Techniques
- **Disk forensics (Windows):** `img_stat`, `mmls`, mount by offset, Recycle Bin parsing, ZIP cracking, registry parsing (RegRipper), file carving via hex signatures.
- **Network forensics (PCAP):** Stream reconstruction (TCP), conversation stats, credential and artifact discovery.
- **Memory forensics:** Profile detection, `pslist`, `netscan`, `memdump`, `lsadump`.
- **Mobile forensics (Android):** SQLite extraction (contacts, calls, SMS), artifacts review, browser History and -wal files.
- **Timeline correlation:** Event normalization and cross‑source validation.

---

## 🛡️ Integrity & Legal Considerations
- Evidence hashed on acquisition (e.g., `md5sum`) and re-verified post‑processing.
- Read‑only mounts; changes recorded in **evidence-workflow.md**.
- Chain‑of‑custody captured for each handling step.

---

## 📌 Outcomes
- Attributed user and device ownership via registry hives & usernames.
- Recovered deleted documents (including mis‑labeled/hidden files).
- Identified communications and likely exfil vectors from PCAP + memory.
- Built a consolidated timeline mapping **who**, **what**, **when**, and **how**.

---

## 🛠️ Tooling
Linux coreutils, Sleuth Kit, RegRipper, Wireshark, Volatility, SQLite tools, hex editors.
