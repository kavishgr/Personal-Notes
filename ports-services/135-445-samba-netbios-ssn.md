# 135/445 - Samba/netbios-ssn

SMB stands for server message block. It’s a protocol for sharing resources like files, printers, in general any resource which should be retrievable or made available by the server. It primarily runs on port 445 or port 139 depending on the server . It is actually natively available in windows, so windows users don’t need to configure anything extra as such besides basic setting up. In linux however ,it is a little different. To make it work for linux, you need to install a samba server because linux natively does not use SMB protocol.

* run the following to find out the version of the smb server:

```text
nmap -sC -p 139,445 -sV 10.10.10.3
```

## Enumeration

### smbmap

SMBMap allows users to enumerate samba share drives across an entire domain. List share drives, drive permissions, share contents, upload/download functionality, file name auto-download pattern matching, and even execute remote commands. This tool was designed with pen testing in mind, and is intended to simplify searching for potentially sensitive data across large networks.

![](../.gitbook/assets/smbmap1.png)



### smbclient

