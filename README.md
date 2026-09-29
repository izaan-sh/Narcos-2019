# ICT378 - Cyber Forensics & Incident Response: Narcos 2019 Investigation Report

**Author:** Izaan Shumaiz  
**Course:** ICT378 - Cyber Forensics & Incident Response  
**Primary Tools:** Autopsy, Magnet AXIOM, FTK Imager, ChromeCacheView, TrueCrypt, Image Steganography Tool, DB Browser for SQLite  

---

## Executive Summary

In 2019, New Zealand Customs detained two passengers, **John Fredricksen** and **Jane Esteban**, arriving in Wellington from Brisbane after methamphetamine was discovered hidden inside luggage. A subsequent raid at 666 Rewera Avenue, Petone, recovered additional evidence and computing hardware.

This forensic investigation analyzes disk images and memory dumps across three primary devices:
- **Narcos-1:** Steve Kowhai's Desktop (`Steve`)
- **Narcos-2:** John Fredricksen's Laptop (`JohnF`)
- **Narcos-3:** Jane Esteban's Laptop (`JaneE`)

---

## Case Verdict & Summary of Findings

| Suspect | Role / Findings | Final Verdict |
| :--- | :--- | :---: |
| **Steve Kowhai** | Local organizer and receiver in New Zealand. Researched methamphetamine cutting techniques, drug routes, utilized privacy tools (ProtonMail, CCleaner), and suggested steganography methods. | **GUILTY** |
| **John Fredricksen** | Operations coordinator. Managed client databases, flight bookings, and encrypted logistics communications via TrueCrypt and Discord. | **GUILTY** |
| **Jane Esteban** | Undercover Australian Federal Police (AFP) officer. Artifacts confirm undercover training materials, survival documentation, and deployment of a surveillance payload to monitor John under duress. | **EXCULPATED (Innocent)** |

---

## Key Technical Evidence & Findings

### 1. Artifact & Profile Attribution
- Identified distinct user profiles across Windows builds:
  - **Narcos-1:** `Steve` on `STEVE-DESKTOP`
  - **Narcos-2:** `johnf` on `JOHNFLAPTOPT`
  - **Narcos-3:** `janee` on `JELAPTOP`

### 2. Encryption & Obfuscation Circumvention
- **TrueCrypt Container:** Recovered encrypted container `secret` located under `C:\Users\JohnF\Downloads\Attachments-Important, crucial to our method\secret`.
- **Credential Recovery:** Discovered passphrases (`ilovediving`, `Elchapo2`) by parsing surrounding system logs, browser cache, and Discord communication remnants.
- **Steganography:** Uncovered concealed operational payloads embedded inside image files (`BNE.png` / `package.jpg`) using LSB steganography extraction.

### 3. Malware & Vulnerability Analysis
- **Payload:** Quasar RAT (Remote Access Trojan) disguised as `Contact_Card.zip`.
- **Vector:** Social engineering execution by John Fredricksen using default user privileges, enabling full remote monitoring without requiring an OS-level exploit.

---

## Repository Documents

- [`IZAAN_34984006_Narcos2019_Investigation_Report.pdf`](https://github.com/izaan-sh/Narcos-2019/blob/main/IZAAN_34984006_Narcos2019_Investigation_Report.pdf) — Complete 43-page formal investigation report.
- [`my_evidences.pdf`](https://github.com/izaan-sh/Narcos-2019/tree/main/Evidence) — Extracted forensic screenshots and evidence log artifact compilation.

---

## Software & Tools Utilized

* **Disk & Memory Analysis:** Autopsy, Magnet AXIOM, FTK Imager
* **Cache & Artifact Extraction:** ChromeCacheView, DB Browser for SQLite
* **Decryption & Steganography:** TrueCrypt, Image Steganography Tool
