# Nombre del reto
	
## Objetivo
```
This [garden](https://jupiter.challenges.picoctf.org/static/d0e1ffb10fc0017c6a82c57900f3ffe3/garden.jpg) contains more than it seems.

HINT: What is a hex editor?
```
## Solucion
``` shell 
┌──(anitars㉿kali)-[~/picoCTF/forensic]
└─$ hexeditor garden.jpg 
                                                                           
┌──(anitars㉿kali)-[~/picoCTF/forensic]
└─$ strings garden.jpg | grep pico
Here is a flag "picoCTF{more_than_m33ts_the_3y3eBdBd2cc}"
                                                                           
┌──(anitars㉿kali)-[~/picoCTF/forensic]
└─$ 


picoCTF{more_than_m33ts_the_3y3eBdBd2cc}                
```
## Referencias
```
hexeditor
strings

```
