## Objetivo
What does asm2(0x4,0x2d) return? Submit the flag as a hexadecimal value (starting with '0x'). NOTE: Your submission for this question will NOT be in the normal flag format. [Source](https://jupiter.challenges.picoctf.org/static/ceac75672637589213b952abe32c84b3/test.S)

## Pistas
- assembly [conditions](https://www.tutorialspoint.com/assembly_programming/assembly_conditions.htm)

## Solución
```
[] <- esp
[] -0xc
[0x5f89 ] - 0x8
[0xa3] - 0x4
[ebp ] <- ebp
[ret ] +  0x4
[0x4 ] +  0x8
[0x2d] +  0xc

[0x4] eax

asm2:
	<+0>:	push   ebp
	<+1>:	mov    ebp,esp
	<+3>:	sub    esp,0x10
	<+6>:	mov    eax,DWORD PTR [ebp+0xc]
	<+9>:	mov    DWORD PTR [ebp-0x4],eax
	<+12>:	mov    eax,DWORD PTR [ebp+0x8]
	<+15>:	mov    DWORD PTR [ebp-0x8],eax
	<+18>:	jmp    0x50c <asm2+31>
	<+20>:	add    DWORD PTR [ebp-0x4],0x1
	<+24>:	add    DWORD PTR [ebp-0x8],0xd1
	<+31>:	cmp    DWORD PTR [ebp-0x8],0x5fa1
	<+38>:	jle    0x501 <asm2+20>
	<+40>:	mov    eax,DWORD PTR [ebp-0x4]
	<+43>:	leave  
	<+44>:	ret   


TERMINAL PYTHON
-----------------------------------------------------------------------------------
Python 3.9.6 (tags/v3.9.6:db3ff76, Jun 28 2021, 15:26:21) [MSC v.1929 64 bit (AMD64)] on win32
Type "help", "copyright", "credits" or "license" for more information.
>>> 0x10
16
>>> 0x4 <= 0c5fa1
  File "<stdin>", line 1
    0x4 <= 0c5fa1
            ^
SyntaxError: invalid syntax
>>> 0x4 <= 0x5fa1
True
>>> 0x1
1
>>> 0x2d+0x1
46
>>> hex(0x2d+0x1)
'0x2e'
>>> 0xd1
209
>>> 0x4
4
>>> 0x5fa1
24481
>>> (24481-213) / 209
116.11483253588517
>>> 0x2e
46
>>> hex(46+117)
'0xa3'
-----------------------------------------------------------------------------------



Flag: 0xa3
```

## Notas adicionales


## Referencias

