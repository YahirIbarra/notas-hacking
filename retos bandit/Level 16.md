## Objetivo
The credentials for the next level can be retrieved by submitting the password of the current level to **a port on localhost in the range 31000 to 32000**. First find out which of these ports have a server listening on them. Then find out which of those speak SSL and which don’t. There is only 1 server that will give the next credentials, the others will simply send back to you whatever you send to it.

## Datos de acceso al nivel
**bandit.labs.overthewire.org**
bandit16
JQttfApK4SeyHwDlI9SXGR50qclOAil1
## Solución
```
bandit16@bandit:~$ nmap localhost
Starting Nmap 7.80 ( https://nmap.org ) at 2024-02-22 18:16 UTC
Nmap scan report for localhost (127.0.0.1)
Host is up (0.00015s latency).
Not shown: 994 closed ports
PORT      STATE SERVICE
22/tcp    open  ssh
1111/tcp  open  lmsocialserver
1840/tcp  open  netopia-vo2
4321/tcp  open  rwhois
8000/tcp  open  http-alt
30000/tcp open  ndmps

Nmap done: 1 IP address (1 host up) scanned in 0.09 seconds
bandit16@bandit:~$ nmap localhost -p 31000-32000
Starting Nmap 7.80 ( https://nmap.org ) at 2024-02-22 18:19 UTC
Nmap scan report for localhost (127.0.0.1)
Host is up (0.00015s latency).
Not shown: 996 closed ports
PORT      STATE SERVICE
31046/tcp open  unknown
31518/tcp open  unknown
31691/tcp open  unknown
31790/tcp open  unknown
31960/tcp open  unknown

Nmap done: 1 IP address (1 host up) scanned in 0.09 seconds
bandit16@bandit:~$ openssl s_cliente -connect localhost:31046
Invalid command 's_cliente'; type "help" for a list.
bandit16@bandit:~$ openssl s_client -connect localhost:31046
CONNECTED(00000003)
80DBF0F7FF7F0000:error:0A0000F4:SSL routines:ossl_statem_client_read_transition:unexpected message:../ssl/statem/statem_clnt.c:398:
---
no peer certificate available
---
No client certificate CA names sent
---
SSL handshake has read 293 bytes and written 300 bytes
Verification: OK
---
New, (NONE), Cipher is (NONE)
Secure Renegotiation IS NOT supported
Compression: NONE
Expansion: NONE
No ALPN negotiated
Early data was not sent
Verify return code: 0 (ok)
---
bandit16@bandit:~$ openssl s_client -connect localhost:31518
CONNECTED(00000003)
Can't use SSL_get_servername
depth=0 CN = localhost
verify error:num=18:self-signed certificate
verify return:1
depth=0 CN = localhost
verify error:num=10:certificate has expired
notAfter=Feb 22 18:04:07 2024 GMT
verify return:1
depth=0 CN = localhost
notAfter=Feb 22 18:04:07 2024 GMT
verify return:1
---
Certificate chain
 0 s:CN = localhost
   i:CN = localhost
   a:PKEY: rsaEncryption, 2048 (bit); sigalg: RSA-SHA1
   v:NotBefore: Feb 22 18:03:07 2024 GMT; NotAfter: Feb 22 18:04:07 2024 GMT
---
Server certificate
-----BEGIN CERTIFICATE-----
MIIDCzCCAfOgAwIBAgIEX2JjdTANBgkqhkiG9w0BAQUFADAUMRIwEAYDVQQDDAls
b2NhbGhvc3QwHhcNMjQwMjIyMTgwMzA3WhcNMjQwMjIyMTgwNDA3WjAUMRIwEAYD
VQQDDAlsb2NhbGhvc3QwggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQDt
h6CuzWl9fWIzJZ94yvFL1T8PaxSTXcQwib1JlZkRih1G1ju3ZL17w3YocIqw1xzC
NtQ+7ux2rV5v8Pwe5Yg/WOKVGUnq6qH4La1H3I6AA7Bjw/0zw4jqeGY04M+3KQjC
nsphanCHk21PvWlfQ4HmNq8vgnRjf8WI6M/a6LehTXl7JjjMyM4NIg1j/dIgYQzo
Qse/a2orQCizztD/bVFOw2Phep/DmJxAEjc4SCuGQ/CrWqNmF5nk0wjKeRHPTmUv
2T3gulxBP9bGVa95IHTPM4LuuEXbXEvvAxRLjs5Onr3kosYjH1FtRrPiGi3ERN1B
Y4R1ppdwOexX29DPc713AgMBAAGjZTBjMBQGA1UdEQQNMAuCCWxvY2FsaG9zdDBL
BglghkgBhvhCAQ0EPhY8QXV0b21hdGljYWxseSBnZW5lcmF0ZWQgYnkgTmNhdC4g
U2VlIGh0dHBzOi8vbm1hcC5vcmcvbmNhdC8uMA0GCSqGSIb3DQEBBQUAA4IBAQC4
+wIeeI2hhn6WRVsnJgtoFMQud6OWLQTB2DNRuhNsMgia50WXZJeB2/rTGDdRL3Lm
yq7lbXTrsDRvid6ZbR5KkzZDHci6gMLQMzSlsEGOzRVYWc2AHQUa22K/RLAM7XEE
tDRtvPclx4VCfFp2l8ccGwv6YoeJYimVj3cYSQ94eUk7JLlqlXjgHr/jHftK8LZR
Etho2bmJjZjnHUX+bhEksmAyui5RyesX0f0tYnHqvTu4RvVhpGiwmA42m+OQgW3S
cvzTrm0ayclxl2TvvnF2HQv+yhwX0x2x+/A8nUPOT//pWjPp4QVs870wZAsTuiBV
wskXiCXcGAR1qbFGuxpF
-----END CERTIFICATE-----
subject=CN = localhost
issuer=CN = localhost
---
No client certificate CA names sent
Peer signing digest: SHA256
Peer signature type: RSA-PSS
Server Temp Key: X25519, 253 bits
---
SSL handshake has read 1339 bytes and written 373 bytes
Verification error: certificate has expired
---
New, TLSv1.3, Cipher is TLS_AES_256_GCM_SHA384
Server public key is 2048 bit
Secure Renegotiation IS NOT supported
Compression: NONE
Expansion: NONE
No ALPN negotiated
Early data was not sent
Verify return code: 10 (certificate has expired)
---
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: B07351C6343E25AD599FB4AF5BF9899AE8AD037FAE1B85A39B4D56883B45708C
    Session-ID-ctx:
    Resumption PSK: 45B9E7F5BA8BA83719B5E7F67AAC8426C33BD59A89011D7C7B84C9036450EE92DF9FC6E5ADB85CBD41D0E4DE01D99102
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - 68 56 d1 a1 a1 c6 63 c0-7e 9e 4f 9f 3a 92 b8 03   hV....c.~.O.:...
    0010 - 34 20 df f5 03 71 c4 83-03 8a b6 56 53 36 03 80   4 ...q.....VS6..
    0020 - 30 05 f0 9a 40 0e af e0-f1 41 f4 bb 17 69 cb e0   0...@....A...i..
    0030 - 7c 75 08 6d b1 40 ac 72-a1 cd 57 fb 78 df f5 8f   |u.m.@.r..W.x...
    0040 - e8 da eb f5 7f ad 50 7a-01 28 4c 18 f1 4a f6 65   ......Pz.(L..J.e
    0050 - 21 c7 12 bd fd 6a e4 c7-26 26 07 d4 1b 7e 9b b2   !....j..&&...~..
    0060 - 35 bf 5f 0d 4b 7b 50 26-32 2d aa 33 56 46 43 92   5._.K{P&2-.3VFC.
    0070 - 17 8c 53 c8 c0 e8 2e 19-15 ff 79 b5 1d c9 0c cf   ..S.......y.....
    0080 - 27 81 f4 f5 00 e1 30 d0-4f 16 47 95 bb 14 dd ba   '.....0.O.G.....
    0090 - 44 b2 cd 30 36 84 ed e7-34 5f 89 f0 d3 cc 99 a1   D..06...4_......
    00a0 - 20 3a 2e 79 4f f3 3b 61-2a c0 b2 e3 22 05 f7 c0    :.yO.;a*..."...
    00b0 - 62 d1 d0 0b 06 eb 08 92-e4 5a 21 fb bb ff a4 cf   b........Z!.....
    00c0 - 1f a6 b8 05 f4 c5 74 ec-12 d6 39 2f 6f da 43 cd   ......t...9/o.C.

    Start Time: 1708626063
    Timeout   : 7200 (sec)
    Verify return code: 10 (certificate has expired)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: 0774ABDC14562E7DD840BDFB37146D6C51ECAB27371C34504FD9163BC7312FE1
    Session-ID-ctx:
    Resumption PSK: 0348FE77CEB1B0DF5538F81564722E4A2D0DF1BD94CE87E178FE4128CEC99078A6932FA30054ACB6B0A3944C0BFE1433
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - 68 56 d1 a1 a1 c6 63 c0-7e 9e 4f 9f 3a 92 b8 03   hV....c.~.O.:...
    0010 - d7 93 ca d4 b6 3d ee f4-71 4c dd a8 f7 3f 51 86   .....=..qL...?Q.
    0020 - d7 7d 53 8b 33 c2 14 f5-21 1b c8 73 60 f6 d7 b8   .}S.3...!..s`...
    0030 - ad e6 a4 ee 6e 00 e0 81-c5 aa 4d a7 01 68 0d b0   ....n.....M..h..
    0040 - 99 50 83 7e 9e 0b 7f 7c-d6 6e 64 3d ba 74 fd 42   .P.~...|.nd=.t.B
    0050 - 87 1b 27 3e 20 5e 4b 6a-ac eb 87 9e b5 a4 7f 87   ..'> ^Kj........
    0060 - 63 33 0f d5 27 93 84 e4-5b ca d0 e5 1b 97 7b 01   c3..'...[.....{.
    0070 - 22 e2 5d e0 80 60 e1 b7-c3 7f 35 eb 78 fd a4 ad   ".]..`....5.x...
    0080 - 32 a9 53 e3 d4 36 b7 e9-06 18 88 fd ae d2 40 b8   2.S..6........@.
    0090 - 5f 54 01 87 22 22 0b 32-fc 61 08 c7 9a aa a1 47   _T.."".2.a.....G
    00a0 - 43 b4 7c f5 02 30 7f e6-8f 7c 88 a6 6c bf 73 e5   C.|..0...|..l.s.
    00b0 - fd af 0b 5d 9b d6 c6 65-54 13 22 80 80 d4 3e 8a   ...]...eT."...>.
    00c0 - 57 2e 78 27 73 03 33 67-f4 98 34 d4 e7 dd 3b c1   W.x's.3g..4...;.

    Start Time: 1708626063
    Timeout   : 7200 (sec)
    Verify return code: 10 (certificate has expired)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
JQttfApK4SeyHwDlI9SXGR50qclOAil1
JQttfApK4SeyHwDlI9SXGR50qclOAil1
^C
bandit16@bandit:~$ openssl s_client -connect localhost:31691
CONNECTED(00000003)
80DBF0F7FF7F0000:error:0A0000F4:SSL routines:ossl_statem_client_read_transition:unexpected message:../ssl/statem/statem_clnt.c:398:
---
no peer certificate available
---
No client certificate CA names sent
---
SSL handshake has read 293 bytes and written 300 bytes
Verification: OK
---
New, (NONE), Cipher is (NONE)
Secure Renegotiation IS NOT supported
Compression: NONE
Expansion: NONE
No ALPN negotiated
Early data was not sent
Verify return code: 0 (ok)
---
bandit16@bandit:~$ openssl s_client -connect localhost:31790
CONNECTED(00000003)
Can't use SSL_get_servername
depth=0 CN = localhost
verify error:num=18:self-signed certificate
verify return:1
depth=0 CN = localhost
verify error:num=10:certificate has expired
notAfter=Feb 22 18:04:08 2024 GMT
verify return:1
depth=0 CN = localhost
notAfter=Feb 22 18:04:08 2024 GMT
verify return:1
---
Certificate chain
 0 s:CN = localhost
   i:CN = localhost
   a:PKEY: rsaEncryption, 2048 (bit); sigalg: RSA-SHA1
   v:NotBefore: Feb 22 18:03:08 2024 GMT; NotAfter: Feb 22 18:04:08 2024 GMT
---
Server certificate
-----BEGIN CERTIFICATE-----
MIIDCzCCAfOgAwIBAgIEWdQAXzANBgkqhkiG9w0BAQUFADAUMRIwEAYDVQQDDAls
b2NhbGhvc3QwHhcNMjQwMjIyMTgwMzA4WhcNMjQwMjIyMTgwNDA4WjAUMRIwEAYD
VQQDDAlsb2NhbGhvc3QwggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQC0
EWB28TWVpVUtrYSaYvmbjtrgpiTuEqg01/SReTOErvDgCyz8mhJ06BhcWK0RDiNz
E1BeQ1s7bo4V8knTeqgTd3cA9XIKO8BgqmGwYiPJyBVDMO+9S4dojnuJGViyhoM7
e0kKwdp7+uEER22koJg+ZqyI/dSSmvaDqMAU+D6FKxcxKjF8vTQzn0CLsYSXPHxT
mhshEAC8jWhYggcUxG0L1qMJnh/NL18e0jwBeCrE2PwsRuh1Qc6vl4Fd/mUByDJb
KSjsR3zDoegCWzh5lTAbnt5eaT47PBNA4foRLypdCG1tG+Cbgk6d0BGtluAJz9D8
5vEfrVpm38OelPOo0vBJAgMBAAGjZTBjMBQGA1UdEQQNMAuCCWxvY2FsaG9zdDBL
BglghkgBhvhCAQ0EPhY8QXV0b21hdGljYWxseSBnZW5lcmF0ZWQgYnkgTmNhdC4g
U2VlIGh0dHBzOi8vbm1hcC5vcmcvbmNhdC8uMA0GCSqGSIb3DQEBBQUAA4IBAQAl
z9TnfQ4cqpUeKMFRzhzuHEvuglEdfmmWmhpQ+NnpcI686OZDshzpHFRVUQjwMulr
XuhDoohLwnd+AOB4BqYWWYoF2z1mo3rsxZxxCoI7y8SP331O46Aqc4SyKMEfYBXq
mCaK5VQebSZotRPqI6jS2W7/+UmJXXKG4pEKI5pBA5tTnvNSbh6Yk87cFlAitTcN
36V1lq8S7tj2BZSfcC+nyoqwPPeLTb5beQTmKG0/JFDnYeHCbVQALq5AhXXH5G67
ytpppb4itSOMr9bfv+Awx6PPLbOJ/gxF1c1HkXX5/Pjbdy2W4sCykvXAJBir2BFe
ixo6bdA2sW0cz3uzk5x7
-----END CERTIFICATE-----
subject=CN = localhost
issuer=CN = localhost
---
No client certificate CA names sent
Peer signing digest: SHA256
Peer signature type: RSA-PSS
Server Temp Key: X25519, 253 bits
---
SSL handshake has read 1339 bytes and written 373 bytes
Verification error: certificate has expired
---
New, TLSv1.3, Cipher is TLS_AES_256_GCM_SHA384
Server public key is 2048 bit
Secure Renegotiation IS NOT supported
Compression: NONE
Expansion: NONE
No ALPN negotiated
Early data was not sent
Verify return code: 10 (certificate has expired)
---
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: AA5B448FDECF0B57389A4DF4FCA4D78853B523E2C75401E8475BB34B1BDF6A4D
    Session-ID-ctx:
    Resumption PSK: 65B1CBFC54FAC80DA930298EE74EEDE2F4AEB79D616446D548F8C8EA3FA441AF460507E52F66DA1989E209468C2F7589
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - d5 fe 56 7f 7c 44 0f 09-aa 20 5d ad 9d 9b 72 2f   ..V.|D... ]...r/
    0010 - 6c 23 a2 bc e2 a8 36 9f-ed 25 8f 7d a8 67 27 97   l#....6..%.}.g'.
    0020 - cf ec b3 23 aa ef 32 c3-fc 4d 25 36 01 a0 bd a9   ...#..2..M%6....
    0030 - 3c 09 b3 e1 e3 10 03 c6-4c 12 c8 cf 63 85 35 50   <.......L...c.5P
    0040 - 86 a8 72 a3 c0 48 08 a6-55 57 58 e1 ee e0 ec d7   ..r..H..UWX.....
    0050 - d8 b6 73 be 42 66 b9 33-92 f3 e4 19 2f 61 a2 f4   ..s.Bf.3..../a..
    0060 - 7a d2 dd c4 60 23 7b c2-e8 a3 1e 8f 83 6e c3 84   z...`#{......n..
    0070 - 41 6b d4 d4 f4 49 da 51-9c f8 2e 13 4b 4b ad 96   Ak...I.Q....KK..
    0080 - 29 70 cc ee dc 31 0a 1e-59 d8 af 15 4e f5 ee c1   )p...1..Y...N...
    0090 - 44 b8 82 4b 74 6d 23 30-3a ec 73 e5 50 25 45 48   D..Ktm#0:.s.P%EH
    00a0 - b4 7d b4 f9 17 c3 0a b2-c6 41 2c fe 40 fb 61 b7   .}.......A,.@.a.
    00b0 - 4a 77 61 bb 50 64 e5 62-18 2b 37 2d b6 60 cb c4   Jwa.Pd.b.+7-.`..
    00c0 - 15 0c 1b d1 d5 9d 35 67-f9 b0 75 79 71 5c 64 4b   ......5g..uyq\dK

    Start Time: 1708626117
    Timeout   : 7200 (sec)
    Verify return code: 10 (certificate has expired)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: 10A9FC992E0E462BDA140576B1BB6C42C632128F73C9EE06347C372E937E0609
    Session-ID-ctx:
    Resumption PSK: 27E0138B1FE50D18463E26DA6C0258EBF19AF10AC322CCB54B2F2B6D46B0CBC1238ACC1EBADBE98E162DB21CF6B1FEB5
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - d5 fe 56 7f 7c 44 0f 09-aa 20 5d ad 9d 9b 72 2f   ..V.|D... ]...r/
    0010 - f2 a5 a7 8a 8f 83 b5 2e-8e 6a 7b ab 3d 48 db f8   .........j{.=H..
    0020 - 52 9d b3 80 03 da b4 c9-ca 08 a6 48 06 ca bb 4b   R..........H...K
    0030 - 2c 00 eb 23 e5 80 02 6c-f0 43 c3 72 b3 3a 87 8d   ,..#...l.C.r.:..
    0040 - 83 33 bf 6f eb ff 88 17-e9 bb c4 3a b0 77 cc 08   .3.o.......:.w..
    0050 - 8e 16 b6 99 d2 04 e2 a5-de 1f 37 b5 20 dc 20 2e   ..........7. . .
    0060 - 60 ea 35 bc 6a 74 63 d9-3c d0 92 84 aa f2 7f ad   `.5.jtc.<.......
    0070 - 7b 79 0a f1 2d 11 36 79-96 13 a0 47 52 9d 69 2b   {y..-.6y...GR.i+
    0080 - 8a 47 62 dc 24 24 7d 2b-e3 bf b4 9d 51 d7 24 12   .Gb.$$}+....Q.$.
    0090 - e9 ff 09 06 66 dd ae 7c-2c 8f 43 99 a3 c8 d0 3e   ....f..|,.C....>
    00a0 - 9e 01 55 e0 9e 87 5d d5-b1 bd 16 e6 4c c2 e0 6d   ..U...].....L..m
    00b0 - 1c 32 15 ce f7 0e d6 ad-11 9b c5 f7 bb 2a 24 13   .2...........*$.
    00c0 - 70 c3 6c b3 11 08 f6 44-fa f1 a4 ac f5 bb 00 a6   p.l....D........

    Start Time: 1708626117
    Timeout   : 7200 (sec)
    Verify return code: 10 (certificate has expired)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
JQttfApK4SeyHwDlI9SXGR50qclOAil1
Correct!
-----BEGIN RSA PRIVATE KEY-----
MIIEogIBAAKCAQEAvmOkuifmMg6HL2YPIOjon6iWfbp7c3jx34YkYWqUH57SUdyJ
imZzeyGC0gtZPGujUSxiJSWI/oTqexh+cAMTSMlOJf7+BrJObArnxd9Y7YT2bRPQ
Ja6Lzb558YW3FZl87ORiO+rW4LCDCNd2lUvLE/GL2GWyuKN0K5iCd5TbtJzEkQTu
DSt2mcNn4rhAL+JFr56o4T6z8WWAW18BR6yGrMq7Q/kALHYW3OekePQAzL0VUYbW
JGTi65CxbCnzc/w4+mqQyvmzpWtMAzJTzAzQxNbkR2MBGySxDLrjg0LWN6sK7wNX
x0YVztz/zbIkPjfkU1jHS+9EbVNj+D1XFOJuaQIDAQABAoIBABagpxpM1aoLWfvD
KHcj10nqcoBc4oE11aFYQwik7xfW+24pRNuDE6SFthOar69jp5RlLwD1NhPx3iBl
J9nOM8OJ0VToum43UOS8YxF8WwhXriYGnc1sskbwpXOUDc9uX4+UESzH22P29ovd
d8WErY0gPxun8pbJLmxkAtWNhpMvfe0050vk9TL5wqbu9AlbssgTcCXkMQnPw9nC
YNN6DDP2lbcBrvgT9YCNL6C+ZKufD52yOQ9qOkwFTEQpjtF4uNtJom+asvlpmS8A
vLY9r60wYSvmZhNqBUrj7lyCtXMIu1kkd4w7F77k+DjHoAXyxcUp1DGL51sOmama
+TOWWgECgYEA8JtPxP0GRJ+IQkX262jM3dEIkza8ky5moIwUqYdsx0NxHgRRhORT
8c8hAuRBb2G82so8vUHk/fur85OEfc9TncnCY2crpoqsghifKLxrLgtT+qDpfZnx
SatLdt8GfQ85yA7hnWWJ2MxF3NaeSDm75Lsm+tBbAiyc9P2jGRNtMSkCgYEAypHd
HCctNi/FwjulhttFx/rHYKhLidZDFYeiE/v45bN4yFm8x7R/b0iE7KaszX+Exdvt
SghaTdcG0Knyw1bpJVyusavPzpaJMjdJ6tcFhVAbAjm7enCIvGCSx+X3l5SiWg0A
R57hJglezIiVjv3aGwHwvlZvtszK6zV6oXFAu0ECgYAbjo46T4hyP5tJi93V5HDi
Ttiek7xRVxUl+iU7rWkGAXFpMLFteQEsRr7PJ/lemmEY5eTDAFMLy9FL2m9oQWCg
R8VdwSk8r9FGLS+9aKcV5PI/WEKlwgXinB3OhYimtiG2Cg5JCqIZFHxD6MjEGOiu
L8ktHMPvodBwNsSBULpG0QKBgBAplTfC1HOnWiMGOU3KPwYWt0O6CdTkmJOmL8Ni
blh9elyZ9FsGxsgtRBXRsqXuz7wtsQAgLHxbdLq/ZJQ7YfzOKU4ZxEnabvXnvWkU
YOdjHdSOoKvDQNWu6ucyLRAWFuISeXw9a/9p7ftpxm0TSgyvmfLF2MIAEwyzRqaM
77pBAoGAMmjmIJdjp+Ez8duyn3ieo36yrttF5NSsJLAbxFpdlc1gvtGCWW+9Cq0b
dxviW8+TFVEBl1O4f7HVm6EpTscdDxU+bCXWkfjuRb7Dy9GOtt9JPsX8MBTakzh3
vBgsyi/sN3RqRBcGU40fOoZyfAMT8s1m/uYv52O6IgeuZ/ujbjY=
-----END RSA PRIVATE KEY-----

closed
bandit16@bandit:~$ exit
```

## Notas adicionales
- nmap analiza los primeros 100 puertos, pero en realidad hay 65535 puertos en total
- Si la conexion del comando openssl regresa un NONE significa que no habla el lenguaje ssl
- El segundo puerto unicamente responde con echo
- El tercero regresa la llave privada del siguiente nivel
## Referencias

