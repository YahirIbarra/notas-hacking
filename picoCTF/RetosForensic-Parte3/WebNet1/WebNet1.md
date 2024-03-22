## Objetivo
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/capture.pcap) and [key](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/picopico.key). Recover the flag.

## Pistas
- Try using a tool like Wireshark.
- How can you decrypt the TLS stream?

## Solución
```
┌──(kali㉿kali)-[~/Documents/Retos/webnet1]
└─$ ls
capture.pcap  picopico.key
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/webnet1]
└─$ file capture.pcap 
capture.pcap: pcap capture file, microsecond ts (little-endian) - version 2.4 (Ethernet, capture length 65535)
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/webnet1]
└─$ file picopico.key 
picopico.key: ASCII text
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/webnet1]
└─$ wireshark capture.pcap 


DENTRO DE WIRESHARK SELECCIONAMOS LA OPCION DE EDITAR -> PREFERENCIAS -> PROTOCOLOS -> TLS

DESPUES SELECCIONAMOS LA LLAVE picopico.key Y FINALMENTE EXPORTAMOS EL ARCHIVO DE IMAGEN QUE SE ENCUENTRA EN LOS PAQUETES ENVIADOS POR EL PROTOCOLO HTTP


┌──(kali㉿kali)-[~/Documents/Retos/webnet1]
└─$ ls
capture.pcap  picopico.key  vulture.jpg
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/webnet1]
└─$ exiftool vulture.jpg
ExifTool Version Number         : 12.76
File Name                       : vulture.jpg
Directory                       : .
File Size                       : 70 kB
File Modification Date/Time     : 2024:03:21 21:46:10-04:00
File Access Date/Time           : 2024:03:21 21:46:45-04:00
File Inode Change Date/Time     : 2024:03:21 21:46:10-04:00
File Permissions                : -rw-r--r--
File Type                       : JPEG
File Type Extension             : jpg
MIME Type                       : image/jpeg
JFIF Version                    : 1.01
Exif Byte Order                 : Big-endian (Motorola, MM)
X Resolution                    : 1
Y Resolution                    : 1
Resolution Unit                 : None
Artist                          : picoCTF{honey.roasted.peanuts}
Y Cb Cr Positioning             : Centered
Profile CMM Type                : Little CMS
Profile Version                 : 2.1.0
Profile Class                   : Display Device Profile
Color Space Data                : RGB
Profile Connection Space        : XYZ
Profile Date Time               : 2012:01:25 03:41:57
Profile File Signature          : acsp
Primary Platform                : Apple Computer Inc.
CMM Flags                       : Not Embedded, Independent
Device Manufacturer             : 
Device Model                    : 
Device Attributes               : Reflective, Glossy, Positive, Color
Rendering Intent                : Perceptual
Connection Space Illuminant     : 0.9642 1 0.82491
Profile Creator                 : Little CMS
Profile ID                      : 0
Profile Description             : c2
Profile Copyright               : FB
Media White Point               : 0.9642 1 0.82491
Media Black Point               : 0.01205 0.0125 0.01031
Red Matrix Column               : 0.43607 0.22249 0.01392
Green Matrix Column             : 0.38515 0.71687 0.09708
Blue Matrix Column              : 0.14307 0.06061 0.7141
Red Tone Reproduction Curve     : (Binary data 64 bytes, use -b option to extract)
Green Tone Reproduction Curve   : (Binary data 64 bytes, use -b option to extract)
Blue Tone Reproduction Curve    : (Binary data 64 bytes, use -b option to extract)
Image Width                     : 640
Image Height                    : 716
Encoding Process                : Baseline DCT, Huffman coding
Bits Per Sample                 : 8
Color Components                : 3
Y Cb Cr Sub Sampling            : YCbCr4:2:0 (2 2)
Image Size                      : 640x716
Megapixels                      : 0.458

```

## Notas adicionales


## Referencias

