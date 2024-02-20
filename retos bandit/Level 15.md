## Objetivo
The password for the next level can be retrieved by submitting the password of the current level to **port 30001 on localhost** using SSL encryption.

**Helpful note: Getting “HEARTBEATING” and “Read R BLOCK”? Use -ign_eof and read the “CONNECTED COMMANDS” section in the manpage. Next to ‘R’ and ‘Q’, the ‘B’ command also works in this version of that command…**

## Datos de acceso al nivel
**bandit.labs.overthewire.org**
bandit15
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt

## Solución
```
bandit15@bandit:~$ echo "jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt" | open_ssl s_cliente -connect localhost:30001 -ign_eof
Command 'open_ssl' not found, did you mean:
  command 'openssl' from deb openssl (3.0.2-0ubuntu1.10)
Try: apt install <deb name>
bandit15@bandit:~$ echo "jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt" | openssl s_cliente -connect localhost:30001 -ign_eof
Invalid command 's_cliente'; type "help" for a list.
bandit15@bandit:~$ echo "jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt" | openssl s_client -connect localhost:30001 -ign_eof
CONNECTED(00000003)
Can't use SSL_get_servername
depth=0 CN = localhost
verify error:num=18:self-signed certificate
verify return:1
depth=0 CN = localhost
verify error:num=10:certificate has expired
notAfter=Feb 20 17:51:06 2024 GMT
verify return:1
depth=0 CN = localhost
notAfter=Feb 20 17:51:06 2024 GMT
verify return:1
---
Certificate chain
 0 s:CN = localhost
   i:CN = localhost
   a:PKEY: rsaEncryption, 2048 (bit); sigalg: RSA-SHA1
   v:NotBefore: Feb 20 17:50:06 2024 GMT; NotAfter: Feb 20 17:51:06 2024 GMT
---
Server certificate
-----BEGIN CERTIFICATE-----
MIIDCzCCAfOgAwIBAgIEIivS1jANBgkqhkiG9w0BAQUFADAUMRIwEAYDVQQDDAls
b2NhbGhvc3QwHhcNMjQwMjIwMTc1MDA2WhcNMjQwMjIwMTc1MTA2WjAUMRIwEAYD
VQQDDAlsb2NhbGhvc3QwggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQC4
XC9dgne8ha9I/vXn4uTtObLhI/PPyLyl4jyDQPp61VtsEMcOb95KhXxdtQiDtzSD
3KXQVFLaPlVGKDWSR9nV+GoazSNPmNLH/IMVrUYxXjYikPxo1jjYKyuqfjV5bNm3
Hz6z4eDl7wNbPRaPAMPo0WU23m9M04bKQHLINfN7Abz3a+7ChLeICrWXiXp9mWfj
PY8cK7Vayz0eHU4Lg64q4jUaXQqZ/ta1RqZEwv7ZuTKctcazpK/u2+h4zvQCPyLh
uDjUXZTLlIuhfjyKUJLQsmYHAQprV6sY3ybFN32dW6MSE0/ApT6Th0LzKeaYxk5b
3NIeaYyPeKsjqFSwy+2zAgMBAAGjZTBjMBQGA1UdEQQNMAuCCWxvY2FsaG9zdDBL
BglghkgBhvhCAQ0EPhY8QXV0b21hdGljYWxseSBnZW5lcmF0ZWQgYnkgTmNhdC4g
U2VlIGh0dHBzOi8vbm1hcC5vcmcvbmNhdC8uMA0GCSqGSIb3DQEBBQUAA4IBAQBQ
RXG1k+cB357X43fsiyaCQQh4RbWHOcg1jBes5eiC/H8MyC3ec1znXvOUfqJcWNQJ
9UJDMwbkpo+IcwJiOe9n/D3Zeypv1g+ta8KKLsQ+zcbp5RdltKy7GuO/s5WjVofE
/IHz/5g+IMoqqYLlquQ539CZykPMC9TB9uWfJj/i8faCox4gjtkSCri+27tUZuHi
eYR3zxY1ptsJti/pMaItC6Oc2/pSlotQ4fXdciLZYGXqlmSFBt8Y8/v1YkhME5gN
3HmBV/Zg1SghA57zYsbf3npvQwudr04f2iF493pe0VRN6DfiXTxWkJe1VKuyGHEr
Q4L4OdVlgMSeyYyKgFc7
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
    Session-ID: 4227B234CDB03D324D3881FEEEDE2067F745588D5B4009B0D68227F11965508D
    Session-ID-ctx:
    Resumption PSK: 917852B7DD40E4BA2AC42A58AA8F62E263E12E86AAF7CF0DC7ED8496EDE8EC61E95E6FF6F72EE65A84EF2CE5B07F3170
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - 81 c9 7a 81 90 61 a2 44-6e 83 ab 39 4b a2 9f d6   ..z..a.Dn..9K...
    0010 - 3b ae c1 a0 53 59 d7 ec-c6 a1 18 41 54 c3 ea a3   ;...SY.....AT...
    0020 - 27 44 c8 e8 17 ea 2d d1-35 b3 8d e8 f9 a3 d7 8e   'D....-.5.......
    0030 - d9 79 3f 66 77 27 a2 10-46 ac e9 19 64 b0 35 02   .y?fw'..F...d.5.
    0040 - 20 f3 8e f6 37 3f aa ad-42 df 55 0b 11 12 46 59    ...7?..B.U...FY
    0050 - 2c 99 e2 29 21 49 48 1b-c2 31 04 54 08 9f e0 5b   ,..)!IH..1.T...[
    0060 - 72 40 58 87 2a c2 99 ca-44 25 d3 d0 a1 9e 34 b9   r@X.*...D%....4.
    0070 - fd 67 9b 3a 4a fb 6e 10-1d b7 40 74 68 9c 5e d1   .g.:J.n...@th.^.
    0080 - 95 11 26 64 96 13 5d a0-1d 2f 49 17 1c 4d 21 22   ..&d..]../I..M!"
    0090 - 40 40 78 25 74 2c fa 27-b7 60 eb 06 82 17 5d ab   @@x%t,.'.`....].
    00a0 - c4 3c ff 18 69 15 43 0a-81 96 7b 80 13 6b c0 5c   .<..i.C...{..k.\
    00b0 - d8 5f 5f 9c 77 6f 4b 7a-9c 80 80 f7 0e b5 c9 2a   .__.woKz.......*
    00c0 - 33 b1 c2 3b c8 0a 92 6a-f5 ae 9a 49 9c 50 2f b9   3..;...j...I.P/.

    Start Time: 1708455967
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
    Session-ID: E4F20B82890B02F8839B0880382EC96B97BEC8ED99F6A2117D5FC1EC7E1EC154
    Session-ID-ctx:
    Resumption PSK: 695E73A4224207FA3EAD0160B85C523784E7EF300D468677273C9286F371A541E1BEFFD9E958B81AB3199EE870038FCD
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - 81 c9 7a 81 90 61 a2 44-6e 83 ab 39 4b a2 9f d6   ..z..a.Dn..9K...
    0010 - 6e 17 cc 39 f9 ac 66 c8-f2 cf 60 20 ce da 1a ff   n..9..f...` ....
    0020 - 05 a6 7e 84 c6 d0 d8 ae-4d 90 60 00 4c f3 9d 38   ..~.....M.`.L..8
    0030 - 01 ae 69 eb 3d bf 46 90-b5 2a 56 01 dd ab 32 f6   ..i.=.F..*V...2.
    0040 - 48 bb c8 0c 93 24 f6 0d-af 67 ce 48 94 58 08 b4   H....$...g.H.X..
    0050 - 49 ad d8 d2 ba 88 70 99-16 4e db 22 c9 47 66 5a   I.....p..N.".GfZ
    0060 - 04 fa ed 3b 1e ec 71 1d-da 6c 56 e2 16 8a f8 61   ...;..q..lV....a
    0070 - 09 8d 24 0b 9c 9c a2 fa-69 9c 58 5f f5 d0 b7 55   ..$.....i.X_...U
    0080 - b7 cf df 16 ce f8 81 e9-3b 4d 39 4e 62 56 f1 b8   ........;M9NbV..
    0090 - 2a 87 07 76 02 2b c8 62-12 be 9f 3f 17 09 36 49   *..v.+.b...?..6I
    00a0 - 26 7b 28 dd 85 57 d7 d8-8a a6 69 59 14 6a f8 fe   &{(..W....iY.j..
    00b0 - 7d d1 e0 d9 52 2f 94 c9-c7 66 85 30 ef ab 70 95   }...R/...f.0..p.
    00c0 - 4c 14 fd 08 03 04 11 f4-25 f3 71 aa c7 43 1b 82   L.......%.q..C..

    Start Time: 1708455967
    Timeout   : 7200 (sec)
    Verify return code: 10 (certificate has expired)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
Correct!
JQttfApK4SeyHwDlI9SXGR50qclOAil1

closed
```

## Notas adicionales
- El comando openssl establece una conexion segura por la capa del socket.
- El comando s_client sirve para actual como un cliente generico en la conexion ssl
- El parametro -connect sirve para especificar el servidor a donde nos vamos a conectar
- El parametro -ign_eof permite mantener la conexion del cliente activa hasta que este nos de una respuesta

## Referencias
- https://en.wikipedia.org/wiki/Transport_Layer_Security#SSL_1.0,_2.0,_and_3.0
- https://www.feistyduck.com/library/openssl-cookbook/online/
