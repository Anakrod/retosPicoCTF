# Nombre del reto
### Scavenger Hunt
## Objetivo
```
	There is some interesting information hidden around this site [http://mercury.picoctf.net:5080/](http://mercury.picoctf.net:5080/). Can you find it?
HINT: You should have enough hints to find the files, don't run a brute forcer.
```

## Solucion
``` shell 
FLAG: picoCTF{th4ts_4_l0t_0f_pl4c3s_2_lO0k_35844447}

Visitaremos las siguientes ligas para ir encontrando las partes de la bandera.

PART 1: view-source:http://mercury.picoctf.net:5080/
PART 2: view-source:http://mercury.picoctf.net:5080/mycss.css
PART 3: http://mercury.picoctf.net:5080/robots.txt
PART 4: http://mercury.picoctf.net:5080/.htaccess
PART 5: http://mercury.picoctf.net:5080/.DS_Store

Primero revisaremos el codigo del sitio, ahi encontraremos la primera parte, nos dara una pista que nos llevara a la hoja de estilos (mycss.css).
De ahi nos iran dando mas pistas para encontrar todas las partes.


```
## Referencias