# Threat Intelligence Investigation

This project documents a **threat intelligence investigation** of a suspected **CoinMiner** malware sample targeting the **Northbridge Fintech** environment. The investigation covers malware identification, file and network indicators, behavioral analysis, MITRE ATT&CK mapping, and recommended defensive actions.

## Table of Contents

* Project Overview
* Network Topology
* Tools and Technologies
* Configuration Steps
* Results and Findings
* Author

## Project Overview

The purpose of this project was to investigate and profile a suspected phishing malware sample associated with the **CoinMiner** malware family.

The investigation focused on:

* Identifying the malware sample and associated filenames.
* Extracting and documenting the **SHA-256 hash**.
* Analyzing antivirus and sandbox detection results.
* Identifying related dropped files.
* Investigating **Command and Control (C2)** infrastructure.
* Mapping observed malware behavior to **MITRE ATT&CK** techniques.
* Identifying indicators of compromise (**IOCs**).
* Providing defensive recommendations for the Security Operations Center (SOC).

## Network Topology

The source report does not provide a complete physical or logical network topology, specific internal device names, or workstation IP addresses. It does, however, document the malware's external infrastructure relationships.

* **Target Organization:** Northbridge Fintech
* **Malware Family:** CoinMiner
* **File Type:** Win32 Executable (`.exe`)
* **Malicious IP Addresses:**

  * `208.167.233.7`
  * `45.32.65.138`
* **Autonomous System:** Both malicious IP addresses were reported as associated with **ASN 20473** and located in the United States.
* **Contacted Domain:** `pool.hashvault.pro`
* **Domain Detection:** `12/89`
* **Domain Creation Date:** `2017-10-12`
* **Observed Communications:** The malware established outbound communications with external infrastructure, consistent with C2 activity.

## Tools and Technologies

* **VirusTotal** — Used to assess antivirus detection coverage.
* **Hybrid Analysis** — Used for behavioral and sandbox analysis.
* **MITRE ATT&CK** — Used to map observed malware behaviors to attack techniques.
* **CAPE Sandbox** — Behavioral analysis framework identified during the investigation.
* **CAPA** — Used for capability and behavioral analysis.
* **C2AE** — Behavioral similarity analysis.
* **Zenbox** — Sandboxing and behavioral analysis.
* **EDR/Antivirus Controls** — Recommended for detecting and blocking suspicious behavior.
* **Network Firewalls** — Recommended for restricting malicious outbound communication.
* **DNS Filtering** — Recommended for blocking malicious domains.
* **Web Proxies** — Recommended for monitoring and restricting external communication.

## Configuration Steps

1. **Identify the malware sample** and document the suspected malware family and original filenames.
2. **Record the file type** as a Win32 executable (`.exe`).
3. **Calculate and document the SHA-256 fingerprint** of the analyzed sample:
   `061de99e4a504d331e11d4ee27d246790290d9e44e6a261c0f5bb756255db640`
4. **Review VirusTotal results** to determine how many security vendors classified the sample as malicious.
5. **Review Hybrid Analysis results** to identify additional detections and behavioral information.
6. **Identify related dropped files**, including `WinRing0x64.sys` and `bjvz6r.exe`.
7. **Investigate network communications** and identify external IP addresses contacted by the malware.
8. **Investigate contacted domains**, identifying `pool.hashvault.pro` as a relevant infrastructure indicator.
9. **Map observed behavior to MITRE ATT&CK**, including **T1622 – Debugger Evasion** and **T1071 – Application Layer Protocol**.
10. **Review behavioral similarity indicators**, including the C2AE, CAPA, CAPE Sandbox, and Zenbox hashes.
11. **Document indicators of compromise** for use in security monitoring and detection controls.
12. **Recommend defensive controls**, including blocking malicious IP addresses and domains, incorporating file hashes into security controls, and updating endpoint and network detection rules.

## Results and Findings

The investigation identified a suspected **CoinMiner** malware sample targeting the Northbridge Fintech environment.

### Detection Results

* **VirusTotal:** `58/70` available antivirus engines detected or classified the file as malicious.
* **Hybrid Analysis:** `17/26` available antivirus engines detected or classified the file as malicious.
* **SHA-256:** `061de99e4a504d331e11d4ee27d246790290d9e44e6a261c0f5bb756255db640`
* **Related dropped files:**

  * `WinRing0x64.sys`
  * `bjvz6r.exe`

### Network Findings

The investigation identified two malicious IP addresses:

* `208.167.233.7`
* `45.32.65.138`

The malware also contacted the domain `pool.hashvault.pro`, which had a reported detection rate of `12/89`.

### MITRE ATT&CK Findings

The analysis identified the following behaviors:

* **T1622 – Debugger Evasion:** The malware attempts to avoid examination or analysis, potentially hindering detection and investigation.
* **T1071 – Application Layer Protocol:** The malware uses legitimate application-layer protocols such as HTTP/HTTPS, DNS, SMB, or FTP to communicate with C2 infrastructure.

### Behavioral Analysis

The investigation recorded the following behavioral similarity identifiers:

* **C2AE:** `2d0784920a7bf6f905a432af4b87a30d`
* **CAPA:** `70ed070d739a98c3316d0c9bb18eb660`
* **CAPE Sandbox:** `a9899a033230b483c355e3b7a3b93e53`
* **Zenbox:** `7c4e9fafcfbb01b6037c92422e929e95`

These analysis frameworks provided information about the sample's execution behavior, capabilities, and potential indicators of compromise.

### Recommended Defensive Actions

The report recommends that the SOC:

* **Block the identified malicious IP addresses** at the network perimeter.
* **Block identified malicious files** using appropriate security controls.
* Add the identified **domain and SHA-256 hash** to relevant security controls.
* Update **endpoint and network detection rules** to identify the observed malware behavior.
* Monitor continuously for **additional indicators of compromise and related activity**.

## Author

**WASIU BLESSING AJAO**

* **Role:** Threat Intelligence Analyst
* **Date of Investigation:** 19 September 2026
* **Organization Investigated:** Northbridge Fintech
* **Contact Information:** wasiuajao99@gmail.com
