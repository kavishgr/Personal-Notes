# Decrypt Hashes

## Decrypt Cisco Type 7 password

{% embed url="https://github.com/theevilbit/ciscot7" %}

Example:

```text
python ciscot7.py -d -p 0242114B0E143F015F5D1E161713

Decrypted password: $uperP@ssword
```

## Decrypt MD5 Hash

The hash : `$1$pdQG$o8nrSzsGXeaduXrjlvKc91`

Copy the hash in a file called hash.txt, the run:

Command: `hashcat -m 500 hash.txt wordlist.txt`

```text
---- SNIP ----

MacBook-Pro:~ kavish$ hashcat -m 500 cisco-md5.txt /usr/share/wordlists/rockyou.txt

$1$pdQG$o8nrSzsGXeaduXrjlvKc91:stealth1agent

Session..........: hashcat
Status...........: Cracked
Hash.Type........: md5crypt, MD5 (Unix), Cisco-IOS $1$ (MD5)
Hash.Target......: $1$pdQG$o8nrSzsGXeaduXrjlvKc91
Time.Started.....: Sun Dec  1 19:09:29 2019 (53 secs)
Time.Estimated...: Sun Dec  1 19:10:22 2019 (0 secs)
Guess.Base.......: File (rockyou.txt)
Guess.Queue......: 1/1 (100.00%)
Speed.Dev.#2.....:    66484 H/s (6.96ms) @ Accel:64 Loops:31 Thr:16 Vec:1
Recovered........: 1/1 (100.00%) Digests, 1/1 (100.00%) Salts
Progress.........: 3544400/14344385 (24.71%)
Rejected.........: 38224/3544400 (1.08%)
Restore.Point....: 3527450/14344385 (24.59%)
Candidates.#2....: stheev -> stblea

Started: Sun Dec  1 19:09:24 2019
Stopped: Sun Dec  1 19:10:23 2019
MacBook-Pro:~ kavish$
```

 The hash value is `stealth1agent`.

With JtR \(one liner\):

`john --wordlist=/usr/share/wordlists/rockyou.txt ./ciscomd5.txt`

```text
root@kavishgr:~/AutoRecon/results/heistHTB/loot# cat ciscomd5.txt 
$1$pdQG$o8nrSzsGXeaduXrjlvKc91

root@kavishgr:~/AutoRecon/results/heistHTB/loot# john --wordlist=/usr/share/wordlists/rockyou.txt ./ciscomd5.txt 
Warning: detected hash type "md5crypt", but the string is also recognized as "md5crypt-long"
Use the "--format=md5crypt-long" option to force loading these as that type instead
Using default input encoding: UTF-8
Loaded 1 password hash (md5crypt, crypt(3) $1$ (and variants) [MD5 128/128 AVX 4x3])
Press 'q' or Ctrl-C to abort, almost any other key for status
stealth1agent    (?)
1g 0:00:01:30 DONE (2019-12-01 22:17) 0.01110g/s 38929p/s 38929c/s 38929C/s stealth323..stealth1967
Use the "--show" option to display all of the cracked passwords reliably
Session completed

root@kavishgr:~/AutoRecon/results/heistHTB/loot# 
```

