# FUTURE_CS_02 - Phishing Email Detection & Awareness System

## Project Overview

This repository contains the deliverables for Task 2 of the Future Interns Cyber Security Track (2026).
The objective was to act as a Security Analyst to dissect real-world phishing email scenarios, identify their attack mechanics, classify their risk levels, and translate these findings into an actionable corporate awareness report designed to educate non-technical employees.

## Analysis Scope & Scenarios

The analysis focused strictly on email header anomalies, domain impersonation (typosquatting), social engineering tactics, and payload delivery mechanisms. Three distinct phishing campaigns were analyzed:

1. Scenario A: Credential Harvesting. Impersonation of PayPal to steal consumer financial login details.
2. Scenario B: Business Email Compromise (BEC) / CEO Fraud. Highly targeted executive impersonation designed to authorize fraudulent offshore wire transfers.
3. Scenario C: Internal Spear Phishing. Impersonation of the corporate IT department to capture employee credentials via a fake password reset portal.

## Methodology

Each email sample was subjected to the following analytical process:

- Sender Verification: Analyzing SMTP headers, Reply-To mismatches, and domain variations.
- Intent Analysis: Identifying the psychological triggers used (urgency, fear, authority).
- Payload Inspection: Safely reviewing the destination URLs without interaction.
- Risk Classification: Assigning a severity rating (Safe, Suspicious, Phishing) based on the accumulated indicators of compromise.

## Deliverables

- The comprehensive, corporate-ready Phishing Detection & Awareness Report (`.pdf` or `.docx`), including the "Do's and Don'ts" employee guidelines.
- `phishing_samples/`: Directory containing the raw email metadata, message bodies, and identified indicators for each analyzed campaign.
