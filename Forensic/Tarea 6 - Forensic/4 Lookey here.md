# Nombre del reto
	
## Objetivo
```
Attackers have hidden information in a very large mass of data in the past, maybe they are still doing it. Download the data [here](https://artifacts.picoctf.net/c/296/anthem.flag.txt).

HINT: Download the file and search for the flag based on the known prefix.
```
## Solucion
``` shell 
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/Forensic]
└─$ mkdir lookey
                                                                           
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/Forensic]
└─$ cd lookey 
                                                                           
┌──(anitars㉿kali)-[~/…/hacking/picoCTF/Forensic/lookey]
└─$ wget https://artifacts.picoctf.net/c/296/anthem.flag.txt              
--2022-10-23 19:36:09--  https://artifacts.picoctf.net/c/296/anthem.flag.txt
Resolviendo artifacts.picoctf.net (artifacts.picoctf.net)... 54.230.202.68, 54.230.202.2, 54.230.202.94, ...
Conectando con artifacts.picoctf.net (artifacts.picoctf.net)[54.230.202.68]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 108668 (106K) [application/octet-stream]
Grabando a: «anthem.flag.txt»

anthem.flag.txt    100%[===============>] 106.12K  --.-KB/s    en 0.1s    

2022-10-23 19:36:10 (755 KB/s) - «anthem.flag.txt» guardado [108668/108668]

                                                                           
┌──(anitars㉿kali)-[~/…/hacking/picoCTF/Forensic/lookey]
└─$ ls
anthem.flag.txt
                                                                           
┌──(anitars㉿kali)-[~/…/hacking/picoCTF/Forensic/lookey]
└─$ file anthem.flag.txt 
anthem.flag.txt: Unicode text, UTF-8 text
                                                                           
┌──(anitars㉿kali)-[~/…/hacking/picoCTF/Forensic/lookey]
└─$ cat anthem.flag.txt 
      ANTHEM

      by Ayn Rand


        CONTENTS

         PART ONE

         PART TWO
         .......
         ....
┌──(anitars㉿kali)-[~/…/hacking/picoCTF/Forensic/lookey]
└─$ grep -i "pico" anthem.flag.txt 
      we think that the men of picoCTF{gr3p_15_@w3s0m3_2116b979}
                                                                           
┌──(anitars㉿kali)-[~/…/hacking/picoCTF/Forensic/lookey]
└─$ 

Descargamos el archivo que nos dan, lo abrimos con un 'cat' y vemos que es un texto muy amplio, utilizamos un 'grep' para buscar si ahi esta la bandera, y efectivamente la bandera esta ahí.


```
## Referencias
```

```
