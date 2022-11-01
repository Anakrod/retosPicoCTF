# Nombre del reto
### Basic-mod1	
## Objetivo
```
We found this weird message being passed around on the servers, we think we have a working decryption scheme. Download the message [here](https://artifacts.picoctf.net/c/394/message.txt). Take each number mod 37 and map it to the following character set: 0-25 is the alphabet (uppercase), 26-35 are the decimal digits, and 36 is an underscore. Wrap your decrypted message in the picoCTF flag format (i.e. `picoCTF{decrypted_message}`)

HINT1: Do you know what `mod 37` means?
HINT2: `mod 37` means modulo 37. It gives the remainder of a number after being divided by 37.
```
## Solucion
``` shell 
datos = open('message.txt').read().strip().split(' ')
datos = [int(i)%37 for i in datos]
flag = ' '
print(datos)
for n in datos: 
	if n in range(26):
		flag +=chr(n+65)
	elif n in range(26,36):
		flag +=chr(n+22)
	else:
		flag += "" 
print(flag)

┌──(anitars㉿kali)-[~/…/hacking/picoCTF/crypto/mod]
└─$ nano mod.py   
                                                                           
┌──(anitars㉿kali)-[~/…/hacking/picoCTF/crypto/mod]
└─$ python3 mod.py
[17, 26, 20, 13, 3, 36, 13, 36, 17, 26, 20, 13, 3, 36, 1, 32, 1, 28, 31, 31, 29, 27]
 R0UNDNR0UNDB6B25531
                                                                           
┌──(anitars㉿kali)-[~/…/hacking/picoCTF/crypto/mod]
└─$ nano mod.py   
                                                                           
┌──(anitars㉿kali)-[~/…/hacking/picoCTF/crypto/mod]
└─$ python3 mod.py
[17, 26, 20, 13, 3, 36, 13, 36, 17, 26, 20, 13, 3, 36, 1, 32, 1, 28, 31, 31, 29, 27]
 R0UND_N_R0UND_B6B25531
                                                                           
┌──(anitars㉿kali)-[~/…/hacking/picoCTF/crypto/mod]
└─$ 

Realizamos un script para poder obtener la bandera.
```
## Referencias
```

```

