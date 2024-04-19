## Objetivo
How about we take you on an adventure on exploring certificate signing requestsTake a look at this CSR file [here](https://artifacts.picoctf.net/c/420/readmycert.csr).

## Pistas
- Download the certificate signing request and try to read it.

## Solución
```
┌──(kali㉿kali)-[~/Documents/Retos/readmycert]
└─$ ls
readmycert.csr
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/readmycert]
└─$ cat readmycert.csr
-----BEGIN CERTIFICATE REQUEST-----
MIICpzCCAY8CAQAwPDEmMCQGA1UEAwwdcGljb0NURntyZWFkX215Y2VydF9hNzE2
M2JlOH0xEjAQBgNVBCkMCWN0ZlBsYXllcjCCASIwDQYJKoZIhvcNAQEBBQADggEP
ADCCAQoCggEBAL6KBBqiFmUHDwT3NtVw+Ozveo9uAZ+c47X5n+MEsWPowsNIz9fG
kpLf9rgu9kR4ZR1H5IEddOGEsTA9qRUc1mwBuZeld5o9ltDU+6YzCKANDnwS61sB
w4FV54LTy33T1+1bc11o++3LM34pFCGWI3lwoj8GWDRJdxvvp5Iwh5kz4ki6Mwp/
HAKyyG9i9KMOXAm/Zw0FkL1UZppHa00cbdCieen7lZgeVpFlIs3uo8tL6fGmpYww
Ard6ZFzL1zCwgZukSHsul20gi9Ba4Uz3R4f6zA/PL0S7haAif96yyi/REREKUZGt
76Gt8zv2xVAqhZYYpFqOmv1ycRmZSyF8GWkCAwEAAaAmMCQGCSqGSIb3DQEJDjEX
MBUwEwYDVR0lBAwwCgYIKwYBBQUHAwIwDQYJKoZIhvcNAQELBQADggEBAI4mtS0h
2HQseRJfnySGJdsnquMyLSV1EdvAfb2qTosXuQH0vunk5NbnR9yjXKej0I2Uu6DW
f9UehV+QsgW1tmZKpjGXj602nESDBVwiyNw84AXaW74+vH1lVKu9YFf08GI40Fee
jYYjQLz6DatXL0Qsuyjjo/MF1W1z/N7ErLvox7tj+dIOfEs14LYx61JrwwcAw8Ak
1lo4gwusg/+aEpAhDcw62Bjh2iGfwydHV7vh04vWBzPoSz5xyrNG+w8kALKKRUTh
Z9wKzilfeMGpobC7at6ys5cMdrC3ePVxn0XWTQEWfjQwtr+UtOoOWlP8eJEstWQU
qbdZveR4nsgbnkU=
-----END CERTIFICATE REQUEST-----
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/readmycert]
└─$ vi readmycert.csr
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/readmycert]
└─$ cat readmycert.csr 

MIICpzCCAY8CAQAwPDEmMCQGA1UEAwwdcGljb0NURntyZWFkX215Y2VydF9hNzE2
M2JlOH0xEjAQBgNVBCkMCWN0ZlBsYXllcjCCASIwDQYJKoZIhvcNAQEBBQADggEP
ADCCAQoCggEBAL6KBBqiFmUHDwT3NtVw+Ozveo9uAZ+c47X5n+MEsWPowsNIz9fG
kpLf9rgu9kR4ZR1H5IEddOGEsTA9qRUc1mwBuZeld5o9ltDU+6YzCKANDnwS61sB
w4FV54LTy33T1+1bc11o++3LM34pFCGWI3lwoj8GWDRJdxvvp5Iwh5kz4ki6Mwp/
HAKyyG9i9KMOXAm/Zw0FkL1UZppHa00cbdCieen7lZgeVpFlIs3uo8tL6fGmpYww
Ard6ZFzL1zCwgZukSHsul20gi9Ba4Uz3R4f6zA/PL0S7haAif96yyi/REREKUZGt
76Gt8zv2xVAqhZYYpFqOmv1ycRmZSyF8GWkCAwEAAaAmMCQGCSqGSIb3DQEJDjEX
MBUwEwYDVR0lBAwwCgYIKwYBBQUHAwIwDQYJKoZIhvcNAQELBQADggEBAI4mtS0h
2HQseRJfnySGJdsnquMyLSV1EdvAfb2qTosXuQH0vunk5NbnR9yjXKej0I2Uu6DW
f9UehV+QsgW1tmZKpjGXj602nESDBVwiyNw84AXaW74+vH1lVKu9YFf08GI40Fee
jYYjQLz6DatXL0Qsuyjjo/MF1W1z/N7ErLvox7tj+dIOfEs14LYx61JrwwcAw8Ak
1lo4gwusg/+aEpAhDcw62Bjh2iGfwydHV7vh04vWBzPoSz5xyrNG+w8kALKKRUTh
Z9wKzilfeMGpobC7at6ys5cMdrC3ePVxn0XWTQEWfjQwtr+UtOoOWlP8eJEstWQU
qbdZveR4nsgbnkU=

                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/readmycert]
└─$ base64 -d readmycert.csr 
0��0��0<1&0$U
             picoCTF{read_mycert_a7163be8}10U)
�0�     *�H��                                   ctfPlayer0�"0
|�[ÁU����}���[s]h���3~)!�#yp�?X4Iw0��3�H�3��tᄱ0=��l���w�=������
��Tf�GkMmТy����V�e"����K�񦥌0�zd\��0����H{.�m ��Z�L�G����/D���"޲�/�
Q���;��100U%�Z���rq�K!|i�&0$   *�H��
             0
+0      *�H��
�W/D,�(����ms��Ĭ��ǻc��|K5��1�Rk���$�Z8�ܣ\��Ѝ������_����fJ�1���6�D�\"��<��[�>�}eT��`W��b8�W���#@��
�:�▒��!��'GW��Ӌ�3�K>qʳF�$��ED�g�       �����!
�)_x�����j޲��
             v��x�q�E�M~40�����ZS�x�,�d��Y��x��E 


Flag: picoCTF{read_mycert_a7163be8}
```

## Notas adicionales


## Referencias

