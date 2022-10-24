# Nombre del reto
### Caesar
## Objetivo
```
 Decrypt this [message](https://jupiter.challenges.picoctf.org/static/49f31c8f17817dc2d367428c9e5ab0bc/ciphertext).
 
HINT: caesar cipher [tutorial](https://learncryptography.com/classical-encryption/caesar-cipher)
```
## Solucion
``` shell 
import string

cadena = 'ynkooejcpdanqxeykjrbdofgkq' 
letras = string.ascii_letters
rot = 4
flag = ' '

for c in cadena:
        flag += letras [(letras.find (c)+rot) % 26 ]
print("picoCTF{",flag,"}")


┌──(anitars㉿kali)-[~/…/hacking/picoCTF/crypto/caesar]
└─$ cat ciphertext   
picoCTF{ynkooejcpdanqxeykjrbdofgkq}                                                                           
┌──(anitars㉿kali)-[~/…/hacking/picoCTF/crypto/caesar]
└─$ python3 exp.py 
 xmjnndiboczmpwdxjiqacnefjp
                                                                           
┌──(anitars㉿kali)-[~/…/hacking/picoCTF/crypto/caesar]
└─$ python3 exp.py
picoCTF{  xmjnndiboczmpwdxjiqacnefjp }
                                                                           
┌──(anitars㉿kali)-[~/…/hacking/picoCTF/crypto/caesar]
└─$ python3 exp.py
picoCTF{  crossingtherubiconvfhsjkou }
                                                                           
┌──(anitars㉿kali)-[~/…/hacking/picoCTF/crypto/caesar]
└─$ 

Aplicamos rot 4

```
## Referencias
```
https://privacycanada.net/classical-encryption/caesar-cipher/
```
