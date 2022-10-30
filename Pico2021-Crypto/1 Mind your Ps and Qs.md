# Nombre del reto
### Mind your Ps and Qs	
## Objetivo
```
In RSA, a small `e` value can be problematic, but what about `N`? Can you decrypt this? [values](https://mercury.picoctf.net/static/b9ddda080c56fb421bf30409bec3460d/values)

HINT: Bits are expensive, I used only a little bit over 100 to save money
```
## Solucion
``` shell 
┌──(anitars㉿kali)-[~]
└─$ python3       
Python 3.10.7 (main, Sep  8 2022, 14:34:29) [GCC 12.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> from Crypto.Util.number import long_to_bytes
>>> from Crypto.Util.number import inverse
>>> c = 964354128913912393938480857590969826308054462950561875638492039363373779803642185
>>> e =65537
>>> p = 2434792384523484381583634042478415057961
>>> q = 650809615742055581459820253356987396346063
>>> p
2434792384523484381583634042478415057961
>>> q
650809615742055581459820253356987396346063
>>> n = p * q
>>> n
1584586296183412107468474423529992275940096154074798537916936609523894209759157543
>>> tn = (p-1)+(q-1)
>>> d = inverse(e,tn)
>>> m = pow(c,d,n)
>>> m 
677854786107566493250643976039073435257117621464114480139527394085930068768298184
>>> long_to_bytes(m)
b"\x16\xde\x11t\xd0\x96\xeb\xb6\x11\xa6\xe3J\xa9\xcc\xb3z\xa3\x96v\x9f'\x0c+\xd7A\xa49.\x05\xc0\x0e\xbd\x94\xc8"
>>> tn = (p-1)*(q-1)
>>> d = inverse(e,tn)
>>> m = pow(c,d,n)
>>> m 
13016382529449106065927291425342535437996222135352905256639684640304028661985917
>>> long_to_bytes(m)
b'picoCTF{sma11_N_n0_g0od_73918962}'
>>> 

Realizamos la factorizacion de el valor de 'n' para obtener 'p' y 'q' y poder realizar las operaciones necesarias para poder obtener la bandera.
```
## Referencias
```
factordb.com
```
oracle padding attack