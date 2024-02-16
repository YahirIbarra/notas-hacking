## Objetivo
The password for the next level is stored in the file **data.txt** in one of the few human-readable strings, preceded by several ‘=’ characters.

## Datos de acceso al nivel
**bandit.labs.overthewire.org**
bandit9
EN632PlfYiZbn3PhVK3XOGSlNInNE00t
## Solución
```
bandit9@bandit:~$ strings data.txt
4SA&l"
FR^+
3+2)`
^gjb
zVC&
=2""L(
Qu:
2$A(
HI\}7 H
3X#9
#0jb
uf`e
x]T========== theG)"
PUb,
ZZ      )
~atv
.a!CH
R\Z|
&8ykUC
05hHs
'|%x
y4+f
Na>O6
)sJ-
Ee~z
$M(J
MIh'
5f6;ph
I/]0
*mFv
Q)\ c
!Z4HC
D[L)Y
k'Y92V
NyRe
Dm#{
[s1wg4
[o<A{
j"f<
3}pU
m/iJ@i
3g!\[
<%      Q
J_r8M
C4dr
U5&g
Sn\|
|\oYK}
@phW!
+a,>
.uJf?,
I-Yr
j+!]
fU|"
b"u\
Vcod)))
m+!4
$U_ZC
O8rP}c
? Wv
9(bE
c6lxQ}
========== passwordk^
q+T6
cj~j
]{{v
RMPAd
-W1N]
^j I
wN)V
C"<g'
ia-V
i9lM
jbi$
Ag6A
f5rZPo
X1mW
Q$XG
4FLW
h*kT
^X#i
z8Wp
Y=xW
@V.|
,8z
t%=q
0lp%h
\)c|
,d4fb?
p#fz:
[%ug
^`t d
========== is
hlbw
KnP@
g2h?V1
{0s["I
OKjq
f_m7
Rw(%
4=}D3
Cz!z
W?|4\
!?      _1
E'x{
Ht}9
T4_+D`
{1\=
S@UG
k9[%
bbdC
9SM%
VxW]
!F_V
oS6{
qMk!
_Sn[
A}GY
`)LQ
+i;F
Jb?o
/{b2
94%?A
q.6U
!<$G/
)Scn`
{RWQ
+,p*
QeN$hL]
(\er9
FC&=z
5@jj~
zHW;<
K0L~
nZ8h
BaZ[
#IH>a
#:n-
l{-B
l*r[
!7 ]
2:jJo{3)xm
=Y!m
TIKg
KULS
gn#M
c.Q>K'
        $/2`)=Y
TZ5}
4'+2
*"$5
4_Q=\
@x1g
MO=(
>P\v
bmf3q
V~c)C
6RLX2
HG~hD
0_.{
\%x]>1s{
^,to
?=|J
:nM1Y
v4{)b
)T]c
s,gn
}'Gt
-o+&2I*
u0'm
Sd]8
u%<{
d.3v
Oq+u
vaKsJ
vb37s
\@07
V@y|-
{'ad
>U@:
Or:Z5
JR3)H
)2Wj
-:mSz
mhk7
X)MF*
'2ky0
@9+D/'?,
P1vEGF'9
1['F
fOd'
jZ3W
F$      A
4<.P
REf|
5{~i
?L6>
@I]j5
zW5E
Dr%[+
*2lk
NEz+
wv..
mwQ!2
WX=DA
{OXr
{TbJ;=l
??r)S
[=lI
u-)E
]wPP
{"@Ip
rx70yJ{
qX2R^{X
WH      fU
2KYl
#pJ_
PJoZP
G^xu
========== G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s
CEznc
2[Q:
k[z\e+
>8=6
@^%{
""%4
        j-~j
1u9!e
zA\El
6/@8
J|Y]
$?%96
+<Es
fA49f!
=r=_
2XNcD[
[,o"b
DBtwa
t]{P
a9~$w
>.Tp
}x6~
V]R}
^t|d
=uea
2t$(
7Cmpie
X?,;U
>)uY
3OxsG
5tKW
Qg      R
;&Q-
y|      |
isqH
Qe>fC
~}hO
^QMG/
zl=4
gg0/
#qF~
x<A&
y;u_    nN
bandit9@bandit:~$ strings data.txt  | grep '=='
x]T========== theG)"
========== passwordk^
========== is
========== G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s
bandit9@bandit:~$ exit
```

## Notas adicionales
- El comado *strings* muestra las cadenas dentro de un archivo binario o de datos
- El comando grep nos permite buscar dentro de el archivo con datos legibles

## Referencias