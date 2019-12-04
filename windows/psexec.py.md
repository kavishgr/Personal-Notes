---
description: PSEXEC like functionality written in Python.
---

# psexec.py

PsExec is a light-weight telnet-replacement that lets you execute processes on other systems, complete with full interactivity for console applications.

{% embed url="https://pen-testing.sans.org/blog/2013/03/27/psexec-python-rocks" %}

{% embed url="https://www.secureauth.com/labs/open-source-tools/impacket" %}

psexec.py will spawn a shell for the specified user only if the `ADMIN$` and `C$` shares are writable:

![](../.gitbook/assets/notwriteshares.png)

We can verify this with `crackmapexec.`

![](../.gitbook/assets/admincshareswrite.png)

 Notice the `(Pwn3d!)` 🥳   
This means the user has write access on both `ADMIN$` and `C$`.

Now run `psexec.py`

![Got a shell](../.gitbook/assets/psexecshell.png)

