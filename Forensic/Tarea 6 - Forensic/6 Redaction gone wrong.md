# Nombre del reto
### Redaction gone wrong	
## Objetivo
```
Now you DON’T see me. This [report](https://artifacts.picoctf.net/c/264/Financial_Report_for_ABC_Labs.pdf) has some critical data in it, some of which have been redacted correctly, while some were not. Can you find an important key that was not redacted properly?

HINT: How can you be sure of the redaction?
```
## Solucion
``` shell 
                                                                           
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/Forensic]
└─$ mkdir redaction
                                                                           
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/Forensic]
└─$ cd redaction 
                                                                           
┌──(anitars㉿kali)-[~/…/hacking/picoCTF/Forensic/redaction]
└─$ wget https://artifacts.picoctf.net/c/264/Financial_Report_for_ABC_Labs.pdf
--2022-10-23 20:02:02--  https://artifacts.picoctf.net/c/264/Financial_Report_for_ABC_Labs.pdf
Resolviendo artifacts.picoctf.net (artifacts.picoctf.net)... 54.230.202.68, 54.230.202.24, 54.230.202.94, ...
Conectando con artifacts.picoctf.net (artifacts.picoctf.net)[54.230.202.68]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 34915 (34K) [application/octet-stream]
Grabando a: «Financial_Report_for_ABC_Labs.pdf»

Financial_Report_f 100%[===============>]  34.10K  --.-KB/s    en 0.08s   

2022-10-23 20:02:03 (420 KB/s) - «Financial_Report_for_ABC_Labs.pdf» guardado [34915/34915]

┌──(anitars㉿kali)-[~/…/hacking/picoCTF/Forensic/redaction]
└─$ file Financial_Report_for_ABC_Labs.pdf 
Financial_Report_for_ABC_Labs.pdf: PDF document, version 1.7, 1 pages
                                                                           
┌──(anitars㉿kali)-[~/…/hacking/picoCTF/Forensic/redaction]
└─$ open Financial_Report_for_ABC_Labs.pdf 


picoCTF{C4n_Y0u_S33_m3_fully}

![[Pasted image 20221023201003.png]]

abrimos el documento con el comando 'open' y nos mostrara un documento, veremos algunas partes en negro, seleccionamos las partes y la ultima parte en color negra, ccontiene la bandera, al seleccionarla la podremos ver.
```
## Referencias
```

```
