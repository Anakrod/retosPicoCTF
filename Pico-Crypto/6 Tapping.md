# Nombre del reto
### Tapping
## Objetivo
```
Theres tapping coming in from the wires. What's it saying `nc jupiter.challenges.picoctf.org 9422`.

HINT1: What kind of encoding uses dashes and dots?
HINT2: The flag is in the format PICOCTF{}
```
## Solucion
``` shell 
┌──(anitars㉿kali)-[~/…/hacking/picoCTF/crypto/easy]
└─$ nc jupiter.challenges.picoctf.org 9422
.--. .. -.-. --- -.-. - ..-. { -- ----- .-. ... ...-- -.-. ----- -.. ...-- .---- ... ..-. ..- -. ..--- -.... ---.. ...-- ---.. ..--- ....- -.... .---- ----- } 
                                                                           
┌──(anitars㉿kali)-[~/…/hacking/picoCTF/crypto/easy]
└─$ 

picoCTF{M0RS3C0D31SFUN2683824610}

Utilizamos CyberChef para convertir de Morse a ASCII.
```
## Referencias
```
MORSE A ASCII

https://gchq.github.io/CyberChef/
```
