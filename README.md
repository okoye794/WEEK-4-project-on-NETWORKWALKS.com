# WEEK-4-project-on-NETWORKWALKS.com
# Mediroza General Hospital — Penetration Testing Project

**Program:** Networkwalks Cybersecurity Internship (Batch B083, Week 4)
**Engagement Type:** Black-box Penetration Test
**Target:** `medirozahospital.com` (authorized training environment)
**Duration:** 5 Days | **Status:** ✅ Completed

> ⚠️ Conducted in a controlled, authorized training environment for educational purposes only. Never apply these techniques without explicit permission.

## Overview
Simulated black-box pentest of a hospital web application: identify vulnerabilities, exploit them to demonstrate real impact, and deliver a professional report with remediation guidance.

## Methodology
Recon (`robots.txt`, directory browsing) → authentication testing → SQL injection exploitation → password cracking (dictionary attacks) → file metadata forensics (`exiftool`) → AI-assisted data analysis → structured reporting.

## Key Findings

| Vulnerability | Risk |
|---|---|
| Username enumeration via inconsistent errors | Medium |
| SQL injection → authentication bypass | **Critical** |
| Sensitive files accessible post-bypass | High |
| Weak, crackable file passwords | High |
| Sensitive data left in file metadata | Medium |
| Directory listing on forgotten backup folder | **Critical** |
| Confidential records exposed in public backup | **Critical** |

## Attack Chain
Hidden directories found via `robots.txt` → login form vulnerable to SQL injection → bypassed authentication into a restricted portal → downloaded weakly-protected files → metadata revealed a note pointing to a forgotten backup folder → that folder had directory listing enabled, exposing an internal database backup with confidential records → the responsible staff member was identified by cross-referencing metadata.

**Lesson:** individually moderate issues chained together into a critical data exposure — a reminder of why defense-in-depth matters.

## Recommendations
Standardize login error messages · use parameterized queries · restrict file access · enforce strong passwords · strip metadata before distribution · disable directory listing · remove public-facing backups.

## Skills Demonstrated
Web App Testing · SQL Injection · Auth Bypass Analysis · Password Cracking · File Forensics · OSINT/Recon · Risk Assessment · Technical Reporting

---
*Completed as part of hands-on cybersecurity training toward a SOC Analyst career, via the Networkwalks internship program.*
