# Phishing Indicators of Compromise

This file contains indicators identified during the phishing email investigation project.  
All URLs, domains, and IP addresses are defanged using `[.]` and `hxxp/hxxps` to prevent accidental clicking.

---

## Case 01: Unclaimed Property / Fund Phishing Email

### Summary

This case involved a suspicious unclaimed property/fund email claiming the recipient may be entitled to a large payout. The email used official-sounding language but was sent from a personal Gmail account and contained financial lure/social engineering indicators.

| Type | Indicator | Notes |
|---|---|---|
| Sender Email | `fmsadjustors@gmail[.]com` | Personal Gmail account claiming to represent financial/government services |
| Sending IP | `209.85.220[.]65` | Gmail sending infrastructure shown in header |
| URL | `hxxp://money.cnn[.]com/2013/01/24/pf/unclaimed-money/index.html` | Link included in suspicious email |
| Domain | `money.cnn[.]com` | Domain checked using URLScan/VirusTotal |
| Domain | `unclaimed[.]org` | Link displayed in the email |
| Subject | `Unclaimed Property/Fund FSM Califorins USA` | Suspicious subject with spelling errors |
| Claimed Amount | `$1.7 million` | Financial lure used in message body |

### Notes

- SPF, DKIM, and DMARC passed because the message was sent through Gmail.
- Passing authentication did not make the email safe because the sender identity did not match the claimed organization.
- The email used a large financial payout lure, vague authority claims, and poor grammar.
- Verdict: **Suspicious / Likely Phishing**

---

## Case 02: Advance-Fee Scam Email Header Analysis

### Summary

This case used a Nebraska GenCyber email header analysis sample involving an advance-fee scam. The sender claimed to have access to a large amount of money and offered the recipient a percentage for helping receive the funds.

| Type | Indicator | Notes |
|---|---|---|
| From Email | `vieria@aol[.]com` | Claimed sender address |
| Reply-To Email | `carrr444@yahoo[.]com` | Reply-To address does not match From address |
| Return-Path | `32309uslisidfj@mail.shako.com.tw[.]com` | Return-Path does not match From or Reply-To |
| Origin Host | `85-250-54-29.bb.netvision.net[.]il` | Origin host shown in email header |
| Origin IP | `85.250.54[.]29` | Origin IP shown in header analysis |
| Mail Server | `mail.shako.com[.]tw` | Mail server shown in routing |
| Mail Server IP | `202.39.131[.]130` | IP associated with mail server/location analysis |
| Subject | `[Spam-Mail] Dear Sir/Madam.` | Spam-marked generic subject |
| Spam Score | `73` | High spam score shown in header |
| Claimed Amount | `$60 million` | Financial lure used in message body |
| Promised Reward | `30% of total sum` | Advance-fee scam indicator |

### Notes

- The `From`, `Reply-To`, and `Return-Path` fields did not match.
- The email was sent to undisclosed recipients.
- The sender claimed to be from Guinea Bissau, but technical routing evidence showed infrastructure associated with other locations.
- The message used classic advance-fee scam language.
- Verdict: **Phishing / Spam**

---

## Overall Project Notes

The indicators in this file were collected from two phishing investigation case studies:

1. **Unclaimed Property / Fund Phishing Email**
2. **Advance-Fee Scam Email Header Analysis**

The main suspicious patterns identified were:

- Personal email accounts claiming to represent official organizations
- Mismatched `From`, `Reply-To`, and `Return-Path` fields
- High-value financial lures
- Poor grammar and generic greetings
- Undisclosed recipients
- Suspicious routing inconsistencies
- Social engineering language designed to pressure or persuade the recipient

These indicators were documented for training and portfolio purposes only.
