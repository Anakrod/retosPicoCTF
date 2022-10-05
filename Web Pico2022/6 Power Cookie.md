# Nombre del reto
### Power Cookie
## Objetivo
```
Can you get the flag? Go to this [website](http://saturn.picoctf.net:61304/) and see what you can discover.

HINT: Do you know how to modify cookies?
```
## Solucion
``` Shell

Ingresamos al sitio indicado, presionamos el boton que hay en el inicio del sitio y nos manda a un lugar que no nos dice nada. Como la pista nos indica algo de cambiar cookies, procedemos a buscar si se generaron algunas cookies y efectivamente hay una cookie, que nos muestra un "is admin", lo abrimos y nos muestra que "admin" tiene un valor de 0, lo cambiamos a 1, guardamos la nueva cookie y refrescamos el sitio el cual nos mostrara la bandera de manera exitosa.

'picoCTF{gr4d3_A_c00k13_0d351e23}'

```
## Referencias
```

```
