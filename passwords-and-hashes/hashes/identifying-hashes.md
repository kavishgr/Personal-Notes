# Identifying Hashes

MD5 

```text
root@kavishgr:~/AutoRecon/results/heistHTB/loot/hashID# hashcat --example-hashes | grep -B2 '\$1\$'

MODE: 500
TYPE: md5crypt, MD5 (Unix), Cisco-IOS $1$ (MD5)
HASH: $1$38652870$DUjsu4TTlTsOe/xxZ05uf/
--
MODE: 12200
TYPE: eCryptfs
HASH: $ecryptfs$0$1$4207883745556753$567daa975114206c
--
MODE: 16700
TYPE: FileVault 2
HASH: $fvde$1$16$84286044060108438487434858307513$20000$f1620ab93192112f0a23eea89b5d4df065661f974b704191
```

```text
root@kavishgr:~/AutoRecon/results/heistHTB/loot/hashID# hashcat --example-hashes | grep '\$1\$'
TYPE: md5crypt, MD5 (Unix), Cisco-IOS $1$ (MD5)
HASH: $1$38652870$DUjsu4TTlTsOe/xxZ05uf/
HASH: $ecryptfs$0$1$4207883745556753$567daa975114206c
HASH: $fvde$1$16$84286044060108438487434858307513$20000$f1620ab93192112f0a23eea89b5d4df065661f974b704191

```

```text
root@kavishgr:~/AutoRecon/results/heistHTB/loot/hashID# hashid '$1$pdQG$o8nrSzsGXeaduXrjlvKc91'
Analyzing '$1$pdQG$o8nrSzsGXeaduXrjlvKc91'
[+] MD5 Crypt 
[+] Cisco-IOS(MD5) 
[+] FreeBSD MD5 

```

