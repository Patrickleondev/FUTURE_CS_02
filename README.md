# FUTURE_CS_02 — Phishing Email Detection & Awareness System

## About This Task

This repository is the submission for **Task 2** of the **Future Interns Cyber Security Track (2026)**.

**Task:** Analyze real phishing email samples, identify phishing indicators, classify email risk, and produce a professional security awareness report for business users.

---

## Analysis Approach

This task was completed by:

1. Collecting representative phishing email samples (credential theft, BEC fraud, spear phishing)
2. Analyzing email headers to identify spoofed senders, mismatched Reply-To fields, and suspicious originating IPs
3. Inspecting links and domains for typosquatting and obfuscation techniques
4. Classifying each email's risk level (Safe / Suspicious / Phishing)
5. Documenting findings and creating employee-facing prevention guidelines

---

## Tools Used

| Tool                        | Purpose                                    |
| --------------------------- | ------------------------------------------ |
| Google Apps Header Analyzer | Parsing and analyzing email headers        |
| MXToolbox                   | DKIM/SPF/DMARC record verification         |
| Browser DevTools            | Inspecting links and URL structures safely |
| Google Docs / Markdown      | Documentation and report writing           |

---

## Repository Structure

```
FUTURE_CS_02/
├── Phishing_Detection_Report.md    # Full professional awareness report
├── README.md                       # This file
└── phishing_samples/
    └── phishing_email_samples.md   # Raw phishing email samples with header analysis
```

---

## Key Deliverables

- [**Phishing Detection & Awareness Report**](Phishing_Detection_Report.md) — Full report covering 3 analyzed phishing scenarios, risk classification, attack lifecycle, and employee prevention guidelines.
- [**Raw Email Samples & Header Analysis**](phishing_samples/phishing_email_samples.md) — Detailed breakdown of each phishing email's headers and red flags.

---

*Submitted by: Patrick Leon | Future Interns Cyber Security Program 2026*
