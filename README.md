# Phishing Email Investigation Lab

## Project Description

This project is a hands-on phishing email investigation lab created to practice entry-level SOC analyst email triage skills. The goal of this project is to analyze suspicious email samples, review message headers, identify spoofing and scam indicators, investigate suspicious sender behavior, and document findings in a clear incident-style format.

Phishing investigation is a common task for cybersecurity analysts and SOC analysts. This project demonstrates my ability to review suspicious emails, identify indicators of compromise, analyze email authentication and routing details, and communicate findings through structured reports.

## Why I Created This Project

I created this project as part of my transition into cybersecurity and to build practical portfolio experience. After completing network traffic analysis work, I wanted to add an email security project that demonstrates another important SOC analyst skill: phishing email investigation.

This project helped me practice identifying suspicious sender behavior, reviewing SPF/DKIM/DMARC results, analyzing full email headers, checking links/domains, and writing professional investigation reports.

## Tools Used

- Gmail Show Original
- Google Messageheader Analyzer
- MXToolbox Header Analyzer
- VirusTotal
- URLScan.io
- WHOIS lookup
- Manual email header review
- Social engineering analysis
- Markdown reporting
- Screenshot documentation

## Skills Demonstrated

- Phishing email triage
- Email header analysis
- Sender spoofing detection
- SPF, DKIM, and DMARC review
- Reply-To and Return-Path comparison
- Suspicious link and domain analysis
- IOC identification
- Social engineering analysis
- Email routing review
- SOC-style incident reporting
- Recommended response documentation

## Investigation Methodology

For each case, I followed a structured investigation process:

1. Reviewed the email subject, sender, and message content.
2. Identified suspicious language, urgency, financial lures, or impersonation attempts.
3. Reviewed sender-related fields such as From, Reply-To, and Return-Path.
4. Analyzed email authentication results such as SPF, DKIM, and DMARC where available.
5. Reviewed full email headers and routing details.
6. Investigated suspicious links or domains using reputation tools where applicable.
7. Extracted indicators of compromise.
8. Determined a final verdict.
9. Documented recommended response actions.

## Case Studies Completed

| Case | Scenario | Focus Area |
|---|---|---|
| Case 01 | Unclaimed Property / Fund Email | Suspicious sender, financial lure, SPF/DKIM/DMARC review, link/domain analysis |
| Case 02 | Advance-Fee Scam Email Header Analysis | Header analysis, sender mismatch, routing inconsistencies, spam indicators, social engineering |

## Case 01: Unclaimed Property / Fund Phishing Email

In this case, I investigated a suspicious email claiming the recipient may be entitled to an unclaimed property/fund payout. The message claimed to represent official financial or government-related services but was sent from a personal Gmail account.

Key activities:
- Reviewed the email body for scam and social engineering indicators.
- Checked sender identity and mismatch between claimed organization and actual sender address.
- Reviewed SPF, DKIM, and DMARC results using Gmail Show Original.
- Used Google Messageheader Analyzer and MXToolbox to review header details.
- Checked suspicious URLs/domains using VirusTotal, URLScan.io, and WHOIS.
- Documented the case as suspicious / likely phishing.

Main findings:
- Sender used a personal Gmail account instead of an official government or financial domain.
- Email claimed a large payout amount, creating a financial lure.
- Message contained spelling errors, awkward wording, and vague authority claims.
- SPF, DKIM, and DMARC passed because the email was sent through Gmail, but the content and sender identity remained suspicious.
- Link/domain reputation tools did not confirm malware, but the overall email behavior matched phishing/scam patterns.

## Case 02: Advance-Fee Scam Email Header Analysis

In this case, I used a public Nebraska GenCyber email header analysis exercise to investigate an advance-fee scam email. The email claimed the sender had access to a large amount of money and offered the recipient a percentage for helping receive the funds.

Key activities:
- Reviewed the raw email header.
- Compared From, Reply-To, and Return-Path fields.
- Reviewed spam indicators and authentication information.
- Used Google Messageheader Analyzer to review routing information.
- Identified inconsistencies between the claimed sender location and technical routing evidence.
- Documented the message as phishing / spam.

Main findings:
- The From, Reply-To, and Return-Path fields did not match.
- The email was sent to undisclosed recipients.
- The message had a high spam score.
- The sender claimed to be from Guinea Bissau, while routing evidence showed infrastructure associated with other locations.
- The message used a classic advance-fee scam structure involving a large financial reward.

## Repository Structure

```text
phishing-email-investigation-lab/
│
├── README.md
│
├── reports/
│   ├── case-01-unclaimed-property-phishing-email.md
│   └── case-02-advance-fee-scam-header-analysis.md
│
├── screenshots/
│   ├── case-01/
│   │   ├── email-overview.png
│   │   ├── gmail-show-original.png
│   │   ├── google-header-analysis.png
│   │   ├── mxtoolbox-header-analysis.png
│   │   ├── suspicious-link.png
│   │   ├── urlscan-result.png
│   │   ├── virustotal-domain-result.png
│   │   └── whois-result.png
│   │
│   └── case-02/
│       ├── nebraska-source-page.png
│       ├── raw-header-fields.png
│       ├── origin-received-line.png
│       ├── origin-location-analysis.png
│       ├── email-body-scam-language.png
│       └── google-header-analysis.png
│
└── iocs/
    └── phishing-indicators.md
