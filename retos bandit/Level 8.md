## Objetivo
The password for the next level is stored in the file **data.txt** and is the only line of text that occurs only once

## Datos de acceso al nivel
**bandit.labs.overthewire.org**
bandit8
TESKZC0XvTetK0S9xNwm25STk5iWrBvP
## Solución
```
bandit8@bandit:~$ sort data.txt | uniq -c
     10 18DyjwhN856SsMx8bNrFSvr6rJxNQKhE
     10 1iyGemEgn3qUOOFcAJyGPHOiewqZyp1y
     10 2CQ5DQRdtoe9Ft8YpMHqCwQcN1Bk9lCI
     10 365RauAVsFlxktPMpoLtIf1uxijU1TfV
     10 4K2MoVHd1gXfoOdDjvlaRxFNZwmi4A4C
     10 52p0CnGhAvm4m3fPKqz9mTxVDeVYCvnG
     10 5Y76FifuxKStZi4CVovF2uPhgLrZnLzG
     10 7A4l2BI3lPJgNdWAmyXAGlfB8uvCQLX0
     10 8cxarYi5VoKRj3lzo2baLOJaMgUtzoRH
     10 97Qwmy18JE8aGIud1stpTsOrOtUMHeGI
     10 9d8exmGtSsGcU1gz6HmqTfSxmnmI4FBo
     10 A16BW831T94qcsYcGDSkgzYhxnX2xUdK
     10 aAd8RbcAAGVRifo0gE2x1nPIGH2fjgZi
     10 ahwL1iJ5EDLt9wpBjrP2DY8pv6FLdrLy
     10 AiYd84lOOVTA4gqJPX7f6DH8eG3zwq1W
     10 aniL5AEkrKcj4mFR1ujwPZdtF4z1SAin
     10 b0XUx8jfeWYAUGlnOGGAyVRxdNziM4SF
     10 bJDV41So5UyGPR98w9x5pX6nqWsOU2ra
     10 br26ueVSoLeZd8HqErTJpNVCtwFufHGO
     10 BVego1OuHFYy1glUiCH3m5dQxEPV8D6d
     10 bWO8QplAdUvLTPoI07UdQc6zKvON0WS3
     10 cEqNrEqHVIIi9fQKdcvAxaip1brmsSxT
     10 Dml3j9ydZQj13Q6xVRPHVuMhD9pt0NbT
     10 drJxnp5fJxeVRYlCldsIEtrEEwBdyRIL
     10 eJZcdtHKg9jLpvpK9v31Fj1opqlA1A9k
      1 EN632PlfYiZbn3PhVK3XOGSlNInNE00t
     10 eNdwlpf6iBeQ3o11iHefoHd9GYKDTIfQ
     10 euIPhAiMI8n0DxPCbaAhJ9RTBO3fX4UE
     10 EzkkJebPKsBh9ERGT3vffA2NhTMCbFS5
     10 EzyaXOFuwjlARDRsbctadMvVgZA1y1Sj
     10 fGJ2YQ92lVRRgQ9dC0TiLEMacCsw8Lm9
     10 FJS8eDt5xeeyabbeEqyRV9W8uQ62BYnX
     10 FQIgwPiuPKftkFhIy9Nzm94sWdNGTlHd
     10 fuBEcq8TyETrSmuD2yQRmvp42K2jlWdH
     10 fWBv5AzQI14holge9okDaOvrgL7NGNTr
     10 gAAoAApNgD1pS0c9OTGWdsGTIwRDgY0M
     10 gOtGle2Dg1bG8UaS5hN6CjIF14eGM4Qu
     10 GuRn8oi7ecl8kSzTh1GrlHXhcFaNBF7f
     10 H4ZQ34QTyLVVE6Q8nSQVQjtt7gAVztVX
     10 hA2abugfwKD5OEdFW4hSBacALoJiJSKg
     10 HbIahMn0Q6vzNgo1RFXG7GPp8nQ9OO56
     10 HmDZyN0zxPJAkwcaZKhru6S9vFbGuJOg
     10 hWy3uJOV7nE8P26AjcCusGfgHo5ILfM6
     10 i7Ith55pB4DL8SoytpbodUwBodotTGjk
     10 JDr0GA5HspKsYLSpdOBCH6kHT71czynh
     10 jL32h6jpv6GGSCRoDBAyECslrqkJQkm7
     10 Kbv13vGt7e4r4KFPCw688NivbBr5K1hs
     10 kjIuqjobFBhKw9Mmfj2wAnWbXB2VxSfv
     10 kkhCyItNHN3wnTVqmE8C3PcZgbVCWuYt
     10 KkwvIeB3CtYvsxjslESZwkR589n51cEY
     10 KYISscbRkhzx8A10I54jgdbq1sEO98lG
     10 l7nwMDTwlZ2ahsqs9EiiiU1zS9oiuTXK
     10 LR92hMCqRihyASXr5srJ041d0WUVbdee
     10 m1vKmRXwPcZQsvRfjAPA1Oq7haLmy4uu
     10 mrgF9gEkQXZKe9E58QfdKcZtG22tMIly
     10 mTYRseor14aRwbazgTmVVgM4mDOkZJJ4
     10 mvfnErC75MoKu7FCjV75ny7r5v3hPtvN
     10 NCO6mwiQQx2Xct00hxWfynfWyAnFLkgZ
     10 nj1s0u8MNekTeuJ7dLQW31zwtsRdHLQe
     10 NRPT61QwcINsfTDrLO2dpFUhayZehqT0
     10 nyPmwN4SQuTg8M8Cx4anpQQMLvwBsycz
     10 NzjErDvr4xRMBJox5tSJsGuBGF9Ini2S
     10 P8jd7Kr8GXVKTLhe1Y7cVYAARwh4lN4A
     10 piYrfvTU6JmxKJlXgfsGnMBc2expvE8Q
     10 PQ0a8vewEyqcaKm7P21uKO88lpXupIMi
     10 pVukrvfmtzHjUQkr4j8N4ri6lWOMbDYj
     10 pWagnmV56wxV241gY75RPloSDlRTWOA7
     10 q519Xqdlz3wnk3tjmiqzxZRB2rdsYv5o
     10 Q5jKs4g4YYQtlgCfRZ5Joh9jwRAtN4Q0
     10 qcm9OMrZwofpcM8CsuTffc9LKRp50Bwk
     10 qtUQnuIjoLTNwviHPE6yULyPEVUuag5K
     10 Qu5gLayacFzgkk6Qy2aAY9tMvAAMm8vh
     10 Rlaj8VWIHkYsAg42TsFplgAd4ekjgR2X
     10 RyLqqJ3d9ocx0ICbF5x9pMiXPAqXtxoH
     10 s4KiXmQhsCpX4zbIDIeVWKaRJWHwYaHm
     10 swXvCokPAhVazCnl9rPeLXWYHIC5yj8h
     10 t4924Or8OK04Bd6NSXPwlGRaYWcG2pfo
     10 t9IKaY2XcYiDkUXvWE2JOZKIdZvpDXt3
     10 tbwqIearQexlJbmkwluaaa7ZoPXLSuXe
     10 TCXcLHZOAPbd1osXWeuNqltMylxtlUVr
     10 TM3NCu6BEfCirP0jPZxtUm8NX2ypTAF5
     10 TOWEeiT4P5TcGnZ2pyG63NKEvTm0MdPg
     10 tUlwNyLyJjRiFaj4n0oN5cvoUlJKpW8m
     10 TzjPxJ7VQMAEB3R4cvQOOq6jrOKelLQe
     10 uw9mhc4SblNVn8TcIR202ar0ejoUv1bX
     10 vlsSKqk3yVx2PZxIkBuZPR3KKIf8hGi1
     10 Vpj0ntqaDt8nWZL7Hf7QKJX8okOqoI79
     10 vwy1ljezuLueU0DgNTKf4ODgnSKmspJA
     10 WcJIGAlq3VP6b0d7uGzMEjv8awnJst1n
     10 WMgbyqEed5iHRvsI5bVMypuXlQh1dkIJ
     10 x18U8IZqzElHvbzuvBIkLHoX60JnsIH6
     10 X7oolq8RgTxDAJVn6XqHZqQsIXWT5ebi
     10 XRTmJCR9zWNbTt7xZyeqIjH1u1TM1qDx
     10 xtcg9IZotPgfR7qGI8V0jd7L6XErPgih
     10 YIcCD3TC5p6UKk44dVtyHktC7DjFm2jf
     10 YMFh71LtzL97GBBRng0YQUmKm4fsVYDO
     10 yPrvV3lIXlttYCnHE6NILDZWmlMiUIcK
     10 YQEGfxSoUTNa0rT9aDX7SvFM9nlt8h6z
     10 yqKbkKmzg8RV8v3GbtfuMktHvWoVDLo6
     10 zOTIYMCpuvJ0DZGzoEwqIYc19SkIVQdl
     10 zwhYlyTRS3mNMsud9hapW5MDorCIGM0r
bandit8@bandit:~$ sort data.txt | uniq -u
EN632PlfYiZbn3PhVK3XOGSlNInNE00t
```

## Notas adicionales
- El comando sort ordena las lineas
- El comando unique muestra las lineas de manera unica
- El parametro -c en el unique muestra la cantidad de ocurrencias
- El parametro -u en unique muestra unicamente la linea que es unica

## Referencias