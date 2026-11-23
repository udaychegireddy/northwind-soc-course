# Analyst Reference Sheet

Quick-reference tables used in the slides. Keep this open during the practical activities.

## Ports worth knowing

| Port | Protocol / service | Normal use | Warning sign |
|---|---|---|---|
| 20/21 | FTP | File transfer | Cleartext logins; large uploads to unknown hosts |
| 22 | SSH | Remote administration | Many failed logins from one IP |
| 23 | Telnet | Legacy remote access | Any use today |
| 25 / 587 | SMTP | Sending email | A workstation sending mail directly |
| 53 | DNS | Name lookups | Very high volume, very long names, many TXT queries |
| 80 / 443 | HTTP / HTTPS | Web traffic | Regular calls to an unknown site (beaconing) |
| 110 / 995 | POP3 | Reading email | Access from unusual locations |
| 143 / 993 | IMAP | Reading email | Access from unusual locations |
| 389 / 636 | LDAP / LDAPS | Directory queries | Bulk queries (enumeration) |
| 445 | SMB | Windows file sharing | Exposed to the internet; many internal connections |
| 3389 | RDP | Remote Desktop | Logins from unusual countries |

## Windows event IDs

| Event ID | Log | Meaning |
|---|---|---|
| 4624 | Security | Successful logon |
| 4625 | Security | Failed logon |
| 4648 | Security | Logon with explicit credentials |
| 4672 | Security | Special (admin) privileges assigned at logon |
| 4688 | Security | New process created |
| 4698 | Security | Scheduled task created |
| 4769 | Security | Kerberos service ticket requested |
| 4771 | Security | Kerberos pre-authentication failed |
| 7045 | System | New service installed |
| 1102 | Security | Security log cleared |

## Logon types (Event 4624 / 4625)

| Type | Meaning |
|---|---|
| 2 | Interactive (at the keyboard) |
| 3 | Network (e.g. file share) |
| 4 | Batch (scheduled task) |
| 5 | Service |
| 7 | Unlock |
| 10 | Remote Desktop (RemoteInteractive) |

## Event 4625 status codes

| Code | Meaning |
|---|---|
| 0xC000006A | Wrong password for an existing account |
| 0xC0000064 | User name does not exist |
| 0xC0000234 | Account locked out |
| 0xC0000072 | Account disabled |
| 0xC000006F | Logon outside allowed hours |
| 0xC0000071 | Password expired |

## Microsoft Entra ID sign-in error codes (common)

| Code | Meaning |
|---|---|
| 50126 | Invalid user name or password |
| 50034 | User account does not exist |
| 50053 | Account locked (too many attempts) |
| 50074 | Strong authentication (MFA) required |
| 500121 | MFA failed or was denied |
| 50140 | "Keep me signed in" interrupt |

In the Northwind datasets these appear in plain words in the `failure_reason` field.

## Email ports and authentication

| Item | What it is |
|---|---|
| SMTP 25 / 587 | Sending and relaying email |
| IMAP 993, POP3 995 | Reading email (encrypted) |
| SPF | Is the sending server allowed for this domain? |
| DKIM | Is the message signed and unchanged? |
| DMARC | Do the results match the visible From domain, and what to do if not (none / quarantine / reject) |

## Linux log locations

| File | Contains |
|---|---|
| /var/log/auth.log (Debian/Ubuntu) or /var/log/secure (RHEL) | Logins, sudo, SSH |
| /var/log/syslog or /var/log/messages | General system events |
| /etc/crontab, /etc/cron.d/ | Scheduled jobs (persistence) |
| ~/.bash_history | Commands typed by a user |

## MITRE ATT&CK techniques used in this course

| ID | Technique |
|---|---|
| T1566.001 | Phishing: spearphishing attachment |
| T1204.002 | User execution: malicious file |
| T1059.001 | Command and scripting interpreter: PowerShell |
| T1027 | Obfuscated files or information |
| T1105 | Ingress tool transfer |
| T1071.004 | Application layer protocol: DNS |
| T1048 | Exfiltration over alternative protocol |
| T1110.001 / .003 / .004 | Brute force: guessing / spraying / stuffing |
| T1078 | Valid accounts |
| T1621 | Multi-factor authentication request generation |
| T1564.008 | Hide artifacts: email hiding rules |
| T1558.003 | Kerberoasting |
| T1543.003 | Create or modify system process: Windows service |
| T1053.005 | Scheduled task |
| T1547.001 | Registry run keys / startup folder |
