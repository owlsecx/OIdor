# 🆔 OIdor

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Linux%20%2F%20Windows-informational?style=flat-square&logo=linux&logoColor=white&color=0a0c10"/>
  <img src="https://img.shields.io/badge/Category-OWeb%20%2F%20Authorization%20Testing-cyan?style=flat-square"/>
  <img src="https://img.shields.io/badge/Dependencies-None%20(Standalone)-green?style=flat-square"/>
  <img src="https://img.shields.io/badge/License-Proprietary-green?style=flat-square"/>
  <img src="https://img.shields.io/badge/Part%20of-OwlSec%20Toolkit-7b5ea7?style=flat-square"/>
  <img src="https://img.shields.io/badge/Version-v1.0-cyan?style=flat-square"/>
</p>

> **OIdor** is a powerful IDOR testing and structured ID pattern generator. It supports multiple ID templates (prefix-year-seq, date-based, hex-style, compact), year/month range generation, HTTP probing for IDOR detection, pattern analysis, and export to TXT/JSON/CSV.

---

## 📌 Overview

OIdor helps security testers generate targeted ID sequences commonly used in web applications (user IDs, order numbers, ticket IDs, etc.) for testing Insecure Direct Object Reference (IDOR) vulnerabilities. It includes 6 built-in pattern templates, multi-year and multi-month generators, live HTTP probing with customizable success conditions, and reverse pattern analysis.

---

## 🖥️ Modules

| # | Module                | Description |
|---|-----------------------|-------------|
| **[1]** | **Generate**              | Single ID sequence with custom prefix, separator, year, month and padding |
| **[2]** | **Year Range**            | Generate IDs across a range of years (e.g. 2020–2025) |
| **[3]** | **Month Sweep**           | Generate IDs for all 12 months of a specific year |
| **[4]** | **HTTP Probe**            | Inject generated IDs into a URL template and check for IDOR (requires requests) |
| **[5]** | **Pattern Analyser**      | Reverse-engineer a sample ID to guess its structure |

---

## 📊 Pattern Templates

| Template | Example              | Description |
|----------|----------------------|-----------|
| **Standard**     | `EMP-24-001001`      | PREFIX-YY-SEQ |
| **Full Year**    | `EMP-2024-001001`    | PREFIX-YYYY-SEQ |
| **Seq-First**    | `001001-EMP-24`      | SEQ-PREFIX-YY |
| **Hex-Style**    | `EMP-0F4240`         | PREFIX + Hex sequence |
| **Date-Seq**     | `20240101-001001`    | YYYYMMDD-SEQ |
| **Compact**      | `EMP241001001`       | PREFIX + YY + MM + SEQ (no separator) |

---

## 🔍 Key Features

- **Common Prefixes**: EMP, USR, ORD, TICKET, INV, CASE, etc.
- **Flexible Sequencing**: Custom start, count, and zero-padding
- **HTTP IDOR Probe**: Real-time probing with custom success codes and keyword detection
- **Pattern Analysis**: Automatically detects separators, segments, and suggests matching templates
- **Multi-format Export**: TXT, JSON, and CSV with metadata

---

## 📁 Output

All generated IDs and probe results are saved to the `oidr_reports/` directory:

- `oidr_YYYYMMDD_HHMMSS.txt`
- `oidr_YYYYMMDD_HHMMSS.json`
- `oidr_YYYYMMDD_HHMMSS.csv`
- Probe findings saved as `oidr_probe_YYYYMMDD_HHMMSS.txt`

---

## ⚙️ Requirements

- **Linux or Windows**
- **No Python installation needed** — runs as a standalone executable
- **Optional**: `requests` library (for HTTP Probe mode only)

---

## 🚀 Usage

```bash
./OIdor


📦 Part of OwlSec Toolkit
This tool is part of the OwlSec suite — a collection of 300+ security and privacy tools.
🔗 owlsec.org

©️ License
Proprietary — © Khaled S. Haddad
Tools are distributed as pre-built executables. Source code is proprietary.

AUTHORISED SECURITY TESTING USE ONLY
