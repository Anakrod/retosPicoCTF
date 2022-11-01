# Nombre del reto
### credstuff	
## Objetivo
```
We found a leak of a blackmarket website's login credentials. Can you find the password of the user `cultiris` and successfully decrypt it? Download the leak [here](https://artifacts.picoctf.net/c/534/leak.tar). The first user in `usernames.txt` corresponds to the first password in `passwords.txt`. The second user corresponds to the second password, and so on.

HINT: Maybe other passwords will have hints about the leak?
```
## Solucion
``` shell 
┌──(anitars㉿kali)-[~/…/picoCTF/crypto/tarea8/creadstuff]
└─$ wget https://artifacts.picoctf.net/c/534/leak.tar
--2022-10-31 20:40:30--  https://artifacts.picoctf.net/c/534/leak.tar
Resolviendo artifacts.picoctf.net (artifacts.picoctf.net)... 13.249.74.22, 13.249.74.56, 13.249.74.17, ...
Conectando con artifacts.picoctf.net (artifacts.picoctf.net)[13.249.74.22]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 30720 (30K) [application/octet-stream]
Grabando a: «leak.tar»

leak.tar           100%[===============>]  30.00K  --.-KB/s    en 0.02s   

2022-10-31 20:40:31 (1.62 MB/s) - «leak.tar» guardado [30720/30720]

                                                                           
┌──(anitars㉿kali)-[~/…/picoCTF/crypto/tarea8/creadstuff]
└─$ tar xvf leak.tar 
leak/
leak/passwords.txt
leak/usernames.txt
                                                                           
┌──(anitars㉿kali)-[~/…/picoCTF/crypto/tarea8/creadstuff]
└─$ ls
leak  leak.tar
                                                                           
┌──(anitars㉿kali)-[~/…/picoCTF/crypto/tarea8/creadstuff]
└─$ cd leak      
                                                                           
┌──(anitars㉿kali)-[~/…/crypto/tarea8/creadstuff/leak]
└─$ ls
passwords.txt  usernames.txt
                                                                           
┌──(anitars㉿kali)-[~/…/crypto/tarea8/creadstuff/leak]
└─$ vim usernames.txt 

zsh: suspended  vim usernames.txt
                                                                           
┌──(anitars㉿kali)-[~/…/crypto/tarea8/creadstuff/leak]
└─$ cat passwords.txt | head -n 378 | tail -n 1
cvpbPGS{P7e1S_54I35_71Z3}
                                                                           
┌──(anitars㉿kali)-[~/…/crypto/tarea8/creadstuff/leak]
└─$ 

Utilizamos el comando 'VIM' para ver lo que hay, buscamos la palabra 'cultiris' despues buscamos en que linea esta con 'esc' + : set number y de esa manera nos saldremos del 'VIM' y pondremos el siguiente comando para poder encontrar la bandera
'cat passwords.txt | head -n 378 | tail -n 1
'

La bandera estara en 'rot13', asi que aplicamos rot13 y listo.

'picoCTF{C7r1F_54V35_71M3}'
```
## Referencias
```

```
