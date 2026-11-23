# Session 2 — Practical: Is this email genuine?

**Time:** 20 minutes · **Format:** pairs · **Tools:** MXToolbox Email Header Analyzer or Google Admin Toolbox Messageheader

## Why this matters
- **Case:** in Session 1 you found that the attack on the Finance laptop started with an email. Today you examine it, next to two other emails Northwind received that week.
- **Theory:** SPF, DKIM, DMARC and header reading.
- **Later SIEM lab:** email-gateway logs and header fields are common SIEM data sources and alert triggers.

## Files
- `session-2/emails/email_A.eml`
- `session-2/emails/email_B.eml`
- `session-2/emails/email_C.eml` ← the email the Finance user received

Open each `.eml` file in a text editor (Notepad, TextEdit, VS Code) or view it on GitHub. **Do not open them in a mail program.**

## Tools
- MXToolbox: https://mxtoolbox.com/EmailHeaders.aspx
- Google Messageheader: https://toolbox.googleapps.com/apps/messageheader/

## Steps
1. Copy everything from the first line down to the blank line before the message body.
2. Paste it into one of the header analysers and run it.
3. For each email record: sender domain, SPF / DKIM / DMARC results, and any mismatch between From, Reply-To, Return-Path and the sending IP.
4. In the Log Explorer **Case notebook**, insert **Session 2 — Email verdicts** and give each email a verdict: Genuine, Phishing, or Needs more checks, with two pieces of evidence.
5. For email C, write down what you would check next.
6. Download your notebook.

## Deliverable
Updated `northwind-case-notebook.md` with three verdicts and evidence.

## If something does not work
- One analyser is down → use the other one.
- No internet → read the `Authentication-Results`, `Received`, `From`, `Reply-To`, `Return-Path` and `X-Originating-IP` lines directly in the file. Every piece of evidence you need is in the file.
