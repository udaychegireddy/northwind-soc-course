# Northwind SOC Course — Practical Files

Files for the four practical activities of the SOC Analyst course. Everything here is **training data about a fictional company, Northwind Logistics**. All IP addresses and domains are reserved for documentation and lead nowhere.

> Repository link: **https://github.com/YOUR-ACCOUNT/northwind-soc-course**
> Log Explorer (online): **https://YOUR-ACCOUNT.github.io/northwind-soc-course/log-explorer/**

## Get the files

**Option 1 — Download ZIP (no account needed)**
1. Open the repository link above.
2. Click the green **Code** button, then **Download ZIP**.
3. Unzip the folder on your laptop.

**Option 2 — Git**
```
git clone https://github.com/YOUR-ACCOUNT/northwind-soc-course.git
```

## What is in this repository

```
northwind-soc-course/
├── README.md                               ← you are here
├── log-explorer/                           ← browser tool for Sessions 1 and 4
│   ├── index.html                          ← open this file in your browser
│   └── data/                               ← datasets loaded by the Log Explorer
├── datasets/                               ← the same logs as CSV and JSON
│   ├── session1_monday_morning.csv/.json
│   └── session4_identity_logs.csv/.json
├── session-1/
│   └── README.md                           ← Session 1 practical instructions
├── session-2/
│   ├── README.md                           ← Session 2 practical instructions
│   └── emails/                             ← email_A.eml, email_B.eml, email_C.eml
├── session-3/
│   ├── README.md                           ← Session 3 practical instructions
│   └── strings.txt                         ← the two strings to decode
├── session-4/
│   └── README.md                           ← Session 4 practical instructions
├── templates/                              ← case notebook templates (also built into the Log Explorer)
├── reference/
│   └── analyst-reference.md                ← ports, event IDs, error codes, ATT&CK IDs
└── LICENSE
```

## The case: The Northwind Payroll Breach

On **Monday 16 November 2026 at 09:41 UTC**, Northwind's SIEM raised two high-severity alerts on a Finance laptop. You are the SOC team. Over four sessions you will work out what happened, how it started, and how to respond.

| Session | Question you answer | Tool |
|---|---|---|
| 1 | What is happening on the affected laptop? | Northwind Log Explorer |
| 2 | How did the attack arrive? | MXToolbox / Google Messageheader |
| 3 | What did the attacker's code do? | CyberChef + MITRE ATT&CK Navigator |
| 4 | How did it really start, and how do we respond? | Northwind Log Explorer |

## The Case Notebook

The Log Explorer has a **Case notebook** tab. Insert the template for your session, fill it in, and click **Download as Markdown** to hand in your work. Notes are kept only in your browser, so download before closing the page.

## If something does not work

- **Online Log Explorer does not load:** open `log-explorer/index.html` from the downloaded folder. It works offline.
- **GitHub is unavailable:** ask your instructor for the course ZIP file (shared drive or USB stick).
- **A web tool is down:** each session README lists an alternative.
