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

![FTP Connections](../.gitbook/assets/image001.gif)

### Active

The FTP session is initiated by an FTP client to port 21 on the FTP server. It is called the command and control or forward channel. Next the FTP client opens a listening port on its machine and informs the remote FTP server of this port number, and requests the remote FTP server to connect from its port 20 back to the client on the port it has specified. This establishes the "reverse data channel" for transporting data.

Since many firewalls and NAT routers automatically block incoming connections to their protected client machines, the need to establish this second "reverse data channel" can cause trouble. Although passive FTP was created to overcome these problems, most modern firewalls and NAT routers have become "FTP aware". They monitor the outgoing control channel, interpret the client's request to the remote server, and open an incoming port back through the router to the client machine. Active FTP clients can thereby operate behind FTP aware firewalls and NAT routers without trouble.

### Passive

Passive FTP protocol was created to overcome the firewall and router problems associated with active FTP's need to establish a reverse data channel back from the server to the client. Passive FTP operates just like active FTP except that both the initial control channel \(to the server's default port 21\) and the data channel \(to the server's default port 20\) are initiated by the client and received and accepted by the server. Passive FTP is generally used by web browsers and can sometimes be requested as an optional mode from full FTP clients. Because passive FTP does not use a "reverse data channel" approach, it is often more friendly to firewalls and NAT routers, though most modern NAT routers are now "FTP aware".

## Login

### Command Line

Syntax: `ftp IP/URL` or `ftp IP/URL [port]`

```text
root@kavishgr:~/home# ftp dlptest.com 
Connected to dlptest.com.

220 This is a private system - No anonymous login

Name: dlpuser@dlptest.com ##USERNAME
331 User dlpuser@dlptest.com OK. Password required
Password: ##PASSWORD

230-Your bandwidth usage is restricted

230 OK. Current restricted directory is /
Remote system type is UNIX.
Using binary mode to transfer files.
ftp> 

```

### Anonymous

Anonymous FTP is called _anonymous_ because you don't need to identify yourself before accessing files. In general, you enter the word `anonymous` or `ftp` when the host prompts you for a username; **you can enter anything for the password**, such as your e-mail address **or simply the word "`guest`"**. In many cases, when you access an anonymous FTP site, you won't even be prompted for your name and password.

### Browser

![FTP Browser Connection](../.gitbook/assets/ftpbrowser.png)

You can connect to a FTP server using a browser \(like Firefox\) using a URL like: 

```text
ftp://anonymous:anonymous@10.10.10.98
```

## Download all files from FTP

```text
wget -m ftp://anonymous:anonymous@10.10.10.98 #Donwload all
wget -m --no-pasive ftp://anonymous:anonymous@10.10.10.98 #Down
```

