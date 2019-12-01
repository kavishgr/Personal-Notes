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

 The hash value is `stealthagent`.

