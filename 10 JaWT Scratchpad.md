# Nombre del reto
### JaWT Scratchpad
## Objetivo
```
Internal server errors can be intentionally returned by this challenge. If you experience one, try clearing your cookies.

#### Description

Check the admin scratchpad! `https://jupiter.challenges.picoctf.org/problem/58210/` or http://jupiter.challenges.picoctf.org:58210
```

## Solucion
``` shell 
──(anitars㉿kali)-[~]
└─$ john hash -w=/usr/share/wordlists/rockyou.txt
Using default input encoding: UTF-8
Loaded 1 password hash (HMAC-SHA256 [password is key, SHA256 256/256 AVX2 8x])
Press 'q' or Ctrl-C to abort, almost any other key for status
ilovepico        (?)     
1g 0:00:00:05 DONE (2022-09-23 22:07) 0.1754g/s 1297Kp/s 1297Kc/s 1297KC/s ilovepinky53..ilovepatri
Use the "--show" option to display all of the cracked passwords reliably
Session completed. 

Utilizamos john para poder crackear la cookie que nos da, de tal manera que la podamos cambiar y asi poder convertirnos en admin y obtener la bandera.
```

## Referencias
```
https://jwt.io/
https://github.com/openwall/john
```