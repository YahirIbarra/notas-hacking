## Objetivo
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/capture.pcap) and [key](https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/picopico.key). Recover the flag.

## Pistas
- Try using a tool like Wireshark.
- How can you decrypt the TLS stream?

## Solución
```
┌──(kali㉿kali)-[~/Documents/Retos/webnet0]
└─$ ls
capture.pcap  picopico.key
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/webnet0]
└─$ file capture.pcap 
capture.pcap: pcap capture file, microsecond ts (little-endian) - version 2.4 (Ethernet, capture length 65535)
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/webnet0]
└─$ file picopico.key 
picopico.key: ASCII text
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/webnet0]
└─$ wireshark capture.pcap


DENTRO DE WIRESHARK SELECCIONAMOS LA OPCION DE EDITAR -> PREFERENCIAS -> PROTOCOLOS -> TLS

DESPUES SELECCIONAMOS LA LLAVE picopico.key Y FINALMENTE FILTRAMOS LOS PAQUETES HTTP, TENIENDO COMO RESULTADO LO SIGUIENTE:


GET / HTTP/1.1

Host: ec2-18-223-184-200.us-east-2.compute.amazonaws.com

User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.14; rv:68.0) Gecko/20100101 Firefox/68.0

Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8

Accept-Language: en-US,en;q=0.5

Accept-Encoding: gzip, deflate, br

Connection: keep-alive

Upgrade-Insecure-Requests: 1

Pragma: no-cache

Cache-Control: no-cache

  

HTTP/1.1 200 OK

Date: Fri, 23 Aug 2019 15:56:36 GMT

Server: Apache/2.4.29 (Ubuntu)

Last-Modified: Mon, 12 Aug 2019 16:50:05 GMT

ETag: "5ff-58fee50dc3fb0-gzip"

Accept-Ranges: bytes

Vary: Accept-Encoding

Content-Encoding: gzip

Pico-Flag: picoCTF{nongshim.shrimp.crackers}

Content-Length: 821

Keep-Alive: timeout=5, max=100

Connection: Keep-Alive

Content-Type: text/html

  

<!doctype html>

<html lang="en">

<head>

<!-- Required meta tags -->

<meta charset="utf-8">

<meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">

  

<!-- Bootstrap CSS -->

<link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css" integrity="sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T" crossorigin="anonymous">

<!-- Custom styles for this template -->

<link href="starter-template.css" rel="stylesheet">

  

<title>Hello, world!</title>

</head>

<body>

<div class="container">

<div class="starter-template">

<h1>Welcome to A Sample Page</h1>

<p class="lead">

There is legit nothing to see here.<br>

</p>

</div>

</div><!-- /.container -->

  

<!-- Optional JavaScript -->

<!-- jQuery first, then Popper.js, then Bootstrap JS -->

<script src="https://code.jquery.com/jquery-3.3.1.slim.min.js" integrity="sha384-q8i/X+965DzO0rT7abK41JStQIAqVgRVzpbzo5smXKp4YfRvH+8abtTE1Pi6jizo" crossorigin="anonymous"></script>

<script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.7/umd/popper.min.js" integrity="sha384-UO2eT0CpHqdSJQ6hJty5KVphtPhzWj9WO1clHTMGa3JDZwrnQq4sF86dIHNDz0W1" crossorigin="anonymous"></script>

<script src="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/js/bootstrap.min.js" integrity="sha384-JjSmVgyd0p3pXB1rRibZUAYoIIy6OrQ6VrjIEaFf/nJGzIxFDsf4x0xIM+B07jRM" crossorigin="anonymous"></script>

</body>

</html>
```

## Notas adicionales


## Referencias

