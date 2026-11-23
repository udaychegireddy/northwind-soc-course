# Session 4 — Practical: Find the root cause

**Time:** 20 minutes · **Format:** pairs · **Tool:** Northwind Log Explorer

## Why this matters
- **Case:** the email came from a colleague's real mailbox, from an unusual IP address. So how did the attacker get into that mailbox? Today you find out, and decide how to respond.
- **Theory:** sign-in logs, password attacks and MFA bypass.
- **Later SIEM lab:** you will write searches and correlation rules for exactly these patterns.

## Files
- Log Explorer dataset: **Session 4 — Sign-in and mailbox audit logs**

## Steps
1. Open the Log Explorer and choose **Session 4 — Sign-in and mailbox audit logs**.
2. Start from what you already know: search the IP address from email C's `X-Originating-IP` header (Session 2).
3. Use **Count by field** on `source.ip` and `user.name` for failed sign-ins (`event.outcome:failure`). Decide which password attack this is.
4. Follow the compromised account: what happened with MFA, and from which IP addresses did the attacker sign in afterwards?
5. Search `event.dataset:m365.audit`. What did the attacker change or do in the mailbox?
6. Pin the key events, insert the template **Session 4 — Incident ticket** and **Insert pinned events**.
7. Complete the ticket, including three containment actions in the order you would do them. Download your notebook.

## Deliverable
Completed incident ticket in `northwind-case-notebook.md`.

## If something does not work
- Online page down → open `log-explorer/index.html` from the ZIP.
- You prefer a spreadsheet → open `datasets/session4_identity_logs.csv` in any spreadsheet program and filter the columns.
