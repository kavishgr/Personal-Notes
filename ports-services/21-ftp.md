# 21 - FTP

## Basic Information

The **File Transfer Protocol \(FTP**\) is a standard network protocol used for the transfer of computer files between a client and server on a computer network.

**Default Port:** 21

```text
PORT   STATE SERVICE
21/tcp open  ftp
```

## **Banner Grabbing**

```
nc -vn <IP> 21
```

## Passive v/s Active FTP

### Active

FTP sessions are initiated by an FTP client's connection to port 21 of any FTP server. This establishes the "forward" command and control channel. An active FTP client next opens a listening port on its machine, informs the remote FTP server of this port number, and requests the remote FTP server to connect from its port 20 back to the client on the port it has specified. This establishes the "reverse data channel" for transporting data.

Since many firewalls and NAT routers automatically block incoming connections to their protected client machines, the need to establish this second "reverse data channel" can cause trouble. Although passive FTP was created to overcome these problems, most modern firewalls and NAT routers have become "FTP aware". They monitor the outgoing control channel, interpret the client's request to the remote server, and open an incoming port back through the router to the client machine. Active FTP clients can thereby operate behind FTP aware firewalls and NAT routers without trouble.

