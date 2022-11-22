# Nombre del reto
### patchme.py	
## Objetivo
```
Can you get the flag? Run this [Python program](https://artifacts.picoctf.net/c/388/patchme.flag.py) in the same directory as this [encrypted flag](https://artifacts.picoctf.net/c/388/flag.txt.enc).
```
## Solucion
``` shell 
┌──(anitars㉿kali)-[~/…/hacking/picoCTF/reversing_tarea/patchme]
└─$ wget https://artifacts.picoctf.net/c/388/patchme.flag.py
--2022-11-20 21:44:16--  https://artifacts.picoctf.net/c/388/patchme.flag.py
Resolviendo artifacts.picoctf.net (artifacts.picoctf.net)... 54.230.225.122, 54.230.225.11, 54.230.225.100, ...
Conectando con artifacts.picoctf.net (artifacts.picoctf.net)[54.230.225.122]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 980 [application/octet-stream]
Grabando a: «patchme.flag.py»

patchme.flag.py    100%[==============>]     980  --.-KB/s    en 0.001s  

2022-11-20 21:44:16 (1012 KB/s) - «patchme.flag.py» guardado [980/980]

                                                                          
┌──(anitars㉿kali)-[~/…/hacking/picoCTF/reversing_tarea/patchme]
└─$ wget https://artifacts.picoctf.net/c/388/flag.txt.enc   
--2022-11-20 21:44:30--  https://artifacts.picoctf.net/c/388/flag.txt.enc
Resolviendo artifacts.picoctf.net (artifacts.picoctf.net)... 54.230.225.51, 54.230.225.100, 54.230.225.122, ...
Conectando con artifacts.picoctf.net (artifacts.picoctf.net)[54.230.225.51]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 36 [application/octet-stream]
Grabando a: «flag.txt.enc»

flag.txt.enc       100%[==============>]      36  --.-KB/s    en 0s      

2022-11-20 21:44:31 (29.5 MB/s) - «flag.txt.enc» guardado [36/36]

                                                                          
┌──(anitars㉿kali)-[~/…/hacking/picoCTF/reversing_tarea/patchme]
└─$ python3 patchme.flag.py 
Please enter correct password for flag: hola
That password is incorrect
                                                                          
┌──(anitars㉿kali)-[~/…/hacking/picoCTF/reversing_tarea/patchme]
└─$ cat patchme.flag.py 
### THIS FUNCTION WILL NOT HELP YOU FIND THE FLAG --LT ########################
def str_xor(secret, key):
    #extend key to secret length
    new_key = key
    i = 0
    while len(new_key) < len(secret):
        new_key = new_key + key[i]
        i = (i + 1) % len(key)        
    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])
###############################################################################


flag_enc = open('flag.txt.enc', 'rb').read()



def level_1_pw_check():
    user_pw = input("Please enter correct password for flag: ")
    if( user_pw == "ak98" + \
                   "-=90" + \
                   "adfjhgj321" + \
                   "sleuth9000"):
        print("Welcome back... your flag, user:")
        decryption = str_xor(flag_enc.decode(), "utilitarian")
        print(decryption)
        return
    print("That password is incorrect")



level_1_pw_check()
                                                                          
┌──(anitars㉿kali)-[~/…/hacking/picoCTF/reversing_tarea/patchme]
└─$ python3 patchme.flag.py
Please enter correct password for flag: ak98-=90adfjhgj321sleuth9000
Welcome back... your flag, user:
picoCTF{p47ch1ng_l1f3_h4ck_21d62e33}
                                                                          
┌──(anitars㉿kali)-[~/…/hacking/picoCTF/reversing_tarea/patchme]
└─$ 

contraseña: ak98-=90adfjhgj321sleuth9000

FLAG: 'picoCTF{p47ch1ng_l1f3_h4ck_21d62e33}'

Descargamos lo indicado y corremos el programa que descargamos, nos pide una contraseña que no tenemos, revisamos el programa y vemos que valida un texto que esta en partes, tomamos esas partes y las unimos, corremos el programa de vuelta y ponemos la cadena que tomamos del codigo y obtenemos la bandera.
```
## Referencias
```

```
