# Phishing Email Detection & Awareness System

## Sample 1 — PayPal Account Suspended (Classic Phishing)

**Date Received:** 2026-02-28  
**Source:** Public phishing sample dataset (autinerd/phishing-mail-examples)  
**Classification:** 🔴 PHISHING

---

### Raw Email Headers

```
Return-Path: <security-noreply@paypa1-accounts.com>
Received: from smtp.paypa1-accounts.com (192.168.47.221)
          by mx.mailserver.com with ESMTP
Date: Fri, 28 Feb 2026 09:14:33 +0000
From: "PayPal Security" <security@paypa1-accounts.com>
Reply-To: no-reply@paypa1-accounts-recover.net
To: victim@example.com
Subject: =?UTF-8?B?8J+agiBVcmdlbnQ6IFlvdXIgUGF5UGFsIGFjY291bnQgaGFzIGJlZW4gc3VzcGVuZGVk?=
Message-ID: <20260228091433.1A2B3C4D@paypa1-accounts.com>
MIME-Version: 1.0
Content-Type: text/html; charset=UTF-8
X-Mailer: MailSender Pro 3.2
```

---

### Email Body

```
Subject: 🚨 Urgent: Your PayPal Account Has Been Suspended

Dear PayPal User,

We have detected unusual activity on your PayPal account.
To avoid permanent account suspension, you must verify your account
details within 24 hours.

Click the button below to verify your identity now:

👉 Verify My Account: http://secure-paypa1-verify[.]com/login

If you do not verify your account, it will be permanently closed.

Thank you for your cooperation,
PayPal Security Team
support@paypal.com
```

---

### Header Analysis

| Header Field | Value | Red Flag? |
|---|---|:---:|
| From | <security@paypa1-accounts.com> | ✅ Spoofed domain |
| Reply-To | <no-reply@paypa1-accounts-recover.net> | ✅ Different from From |
| Return-Path | <security-noreply@paypa1-accounts.com> | ✅ Mismatched |
| Originating IP | 192.168.47.221 | ✅ Private/internal IP |
| X-Mailer | MailSender Pro 3.2 | ✅ Bulk mailer tool |

---

### Phishing Indicators Identified

| # | Indicator | Type | Description |
|---|---|---|---|
| 1 | `paypa1-accounts.com` | Spoofed Domain | Uses "1" instead of "l" — typosquatting |
| 2 | Reply-To ≠ From | Header Manipulation | Replies go to a different attacker-controlled address |
| 3 | "24 hours" deadline | Fear & Urgency | Creates panic to bypass the victim's critical thinking |
| 4 | "Dear PayPal User" | Generic Greeting | Real companies address you by name |
| 5 | `secure-paypa1-verify[.]com` | Malicious Link | Fake domain designed to capture credentials |
| 6 | No DKIM/SPF signature | Authentication Fail | Legitimate PayPal emails are digitally signed |
| 7 | Encoded Subject | Obfuscation | Base64 encoded to bypass spam filters |

**Risk Classification: 🔴 PHISHING — HIGH RISK**

---

## Sample 2 — Bank Wire Transfer Request (CEO Fraud / BEC)

**Date Received:** 2026-03-01  
**Source:** Business Email Compromise (BEC) simulation sample  
**Classification:** 🔴 PHISHING / Business Email Compromise (BEC)

---

### Raw Email Headers

```
Return-Path: <ceo_michael@corporategmai1.com>
Received: from mail-out.corporategmai1.com (45.142.212.100)
Date: Sun, 01 Mar 2026 07:22:10 +0000
From: "Michael Carter, CEO" <ceo_michael@corporategmai1.com>
To: hr.finance@targetcorp.com
Subject: Urgent Wire Transfer Needed Today
Message-ID: <20260301072210.BEC1234@corporategmai1.com>
X-Priority: 1
```

---

### Email Body

```
Subject: Urgent Wire Transfer Needed Today

Hi Sarah,

I'm currently in a board meeting and cannot be reached by phone.
I need you to process a wire transfer of $47,500 urgently to close
a confidential deal before end of business today.

Please wire to:
Account Name: GlobalTrade Partners Ltd
Account Number: 8834-2291-4419
Routing: 082-0041-1
Bank: First National Bank, Cayman Islands

This is time-sensitive and strictly confidential.
Do NOT discuss with other colleagues until it's done.

Thanks,
Michael Carter
CEO, TargetCorp Inc.
```

---

### Phishing Indicators Identified

| # | Indicator | Type | Description |
|---|---|---|---|
| 1 | `corporategmai1.com` | Spoofed Domain | "gmai1" with "1" instead of "l" |
| 2 | "Urgent... Today" | Urgency | Forces hasty decision-making |
| 3 | "Cannot be reached by phone" | Isolation | Prevents victim from calling to verify |
| 4 | "Strictly confidential — do not tell others" | Social Engineering | Prevents the victim from getting a second opinion |
| 5 | Offshore bank (Cayman Islands) | Financial Red Flag | Wire transfers to offshore accounts are irreversible |
| 6 | Impersonates CEO | Authority Abuse | High authority figure used to bypass approval processes |

**Risk Classification: 🔴 PHISHING — CRITICAL (BEC)**

---

## Sample 3 — IT Department Password Reset (Internal Spear Phishing)

**Date Received:** 2026-03-02  
**Source:** Spear phishing simulation sample  
**Classification:** 🟡 SUSPICIOUS

---

### Email Body

```
Subject: [IT] Action Required: Reset Your Password Before Friday

Hi Team,

Our security team has detected that a number of employee accounts are
using passwords that no longer meet our updated security policy.

Please update your password immediately using the link below:

👉 https://company-it-portal-reset.web.app/login

Accounts not updated by Friday will be locked.

IT Security Team
internal-it@company-it-helpdesk.co
```

---

### Phishing Indicators Identified

| # | Indicator | Type |
|---|---|---|
| 1 | Sender domain `company-it-helpdesk.co` | External domain, not company internal |
| 2 | Password reset link to `web.app` (Firebase) | Non-corporate hosting |
| 3 | "Accounts will be locked" | Urgency/Fear |
| 4 | "Hi Team" — no name | Generic greeting |

**Risk Classification: 🟡 SUSPICIOUS — Verify with IT Department before clicking**
