# 23 - Telnet

## **Basic Information**

Telnet is a network protocol that gives users a UNsecure way to access a computer over a network.

**Default port:** 23

```text
23/tcp open  telnet
```

## **Banner Grabbing**

```
nc -vn <IP> 23
```

## Enumeration

All the interesting enumeration can be performed by nmap:

```text
nmap --script "*telnet* and safe" -p 23 <IP>
```

