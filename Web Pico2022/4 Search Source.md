# Nombre del reto
### Search Source
## Objetivo
```
The developer of this website mistakenly left an important artifact in the website source, can you find it? The website is [here](http://saturn.picoctf.net:61941/)

HINT: How could you mirror the website on your local machine so you could use more powerful tools for searching?
```
## Solucion
``` shell
picoCTF{1nsp3ti0n_0f_w3bpag3s_8de925a7}

┌──(anitars㉿kali)-[~/Descargas]
└─$ mkdir search_source 
                                                                          
┌──(anitars㉿kali)-[~/Descargas]
└─$ cd search_source/ 
                                                                          
┌──(anitars㉿kali)-[~/Descargas/search_source]
└─$ wget -m  http://saturn.picoctf.net:61941/
--2022-10-03 22:18:39--  http://saturn.picoctf.net:61941/
Resolviendo saturn.picoctf.net (saturn.picoctf.net)... 18.217.86.78
Conectando con saturn.picoctf.net (saturn.picoctf.net)[18.217.86.78]:61941... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 15920 (16K) [text/html]
Grabando a: «saturn.picoctf.net:61941/index.html»

saturn.picoctf.net 100%[==============>]  15.55K  --.-KB/s    en 0.06s   
....

ACABADO --2022-10-03 22:18:41--
Tiempo total de reloj: 2.1s
Descargados: 20 ficheros, 655K en 0.4s (1.68 MB/s)
                                                                          
┌──(anitars㉿kali)-[~/Descargas/search_source]
└─$ grep -R "picoCTF"                        
saturn.picoctf.net:61941/css/style.css:/** banner_main picoCTF{1nsp3ti0n_0f_w3bpag3s_8de925a7} **/
                                                                          
┌──(anitars㉿kali)-[~/Descargas/search_source]


Creamos una carpeta para descargar los archivos de el sitio web, seguido de esto, solamente aplicamos un grep para buscar la bandera, y asi se buscara en todas las carpetas que se hayan descargado en esa carpeta.

```
## Referencias
```
Busque como encontrar la bandera pero no encontre nada, entonces recurri a buscarlo en youtube :(
https://www.youtube.com/watch?v=7PqL1g_25QQ
```
