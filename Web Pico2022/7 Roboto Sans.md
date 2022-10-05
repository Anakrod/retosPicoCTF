# Nombre del reto
### Roboto Sans
## Objetivo
```
The flag is somewhere on this web application not necessarily on the website. Find it. Check [this](http://saturn.picoctf.net:64710/) out.
```
## Solucion
``` shell
Al no tener pistas, revisamos la descripcion que nos hace pensar que la bandera esta en alguna linea de codigo, revisamos y al ver el nombre decidimos usar 'robots.txt' que nos dara lo siguiente:

User-agent *
Disallow: /cgi-bin/
Think you have seen your flag or want to keep looking.

ZmxhZzEudHh0;anMvbXlmaW
anMvbXlmaWxlLnR4dA==
svssshjweuiwl;oiho.bsvdaslejg
Disallow: /wp-admin/

Revisamos lo que nos dio y tomamos las 3 penultimas lineas que parecen estar en base64, buscamos un decodificador de base64 y nos da lo sigueinte:

flag1.txtjs/myfi
js/myfile.txt
,z谖/u%z8

nos muestra un 'js/myfile.txt' que procedemos a usar, dejando lo siguiente:
view-source:http://saturn.picoctf.net:64710/js/myfile.txt
donde nos mostrara la bandera
'picoCTF{Who_D03sN7_L1k5_90B0T5_032f1c2b}
'
```
## Referencias
```
https://www.base64decode.org/
```
