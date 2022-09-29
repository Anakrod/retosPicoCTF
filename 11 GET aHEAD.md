# Nombre del reto

### GET aHEAD
## Objetivo
```
	Find the flag being held on this server to get ahead of the competition [http://mercury.picoctf.net:45028/](http://mercury.picoctf.net:45028/)


HINT1: Maybe you have more than 2 choices
HINT2: Check out tools like Burpsuite to modify your requests and look at the responses
```

## Solucion
``` shell 
En la linea de comandos
┌──(anitars㉿kali)-[~]
└─$ curl -I http://mercury.picoctf.net:45028/index.php
HTTP/1.1 200 OK
flag: picoCTF{r3j3ct_th3_du4l1ty_775f2530}
Content-type: text/html; charset=UTF-8


Para hacerlo desde el navegador, inspeccionamos la pagina, editamos ya sea el POST o el GET y le ponemos un HEAD de esa manera nos dara la bandera.
```
## Referencias

	http responses codes
	proxies