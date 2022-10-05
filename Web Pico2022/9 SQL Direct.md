# Nombre del reto
### SQL Direct	
## Objetivo
```
Connect to this PostgreSQL server and find the flag!
```
## Solucion
``` shell

┌──(anitars㉿kali)-[~/hacking/hacking]
└─$ psql -h saturn.picoctf.net -p 65140 -U postgres pico
Contraseña para usuario postgres: 
psql (14.5 (Debian 14.5-1), servidor 14.2 (Debian 14.2-1.pgdg110+1))
Digite «help» para obtener ayuda.

pico=# \c pico
psql (14.5 (Debian 14.5-1), servidor 14.2 (Debian 14.2-1.pgdg110+1))
Ahora está conectado a la base de datos «pico» con el usuario «postgres».
pico=# \dt
        Listado de relaciones
 Esquema | Nombre | Tipo  |  Dueño   
---------+--------+-------+----------
 public  | flags  | tabla | postgres
(1 fila)

pico=# SELECT * FROM flags;
 id | firstname | lastname  |                address                 
----+-----------+-----------+----------------------------------------
  1 | Luke      | Skywalker | picoCTF{L3arN_S0m3_5qL_t0d4Y_21c94904}
  2 | Leia      | Organa    | Alderaan
  3 | Han       | Solo      | Corellia
(3 filas)

pico=# ^C
pico=# 

picoCTF{L3arN_S0m3_5qL_t0d4Y_21c94904}

Nos conectamos como se nos indica, entramos a lo que esta en el codigo, ponemos un '\dt' y nos mostrara las relaciones que hay, escribimos una linea (SELECT * FROM flags;)
que nos dara lo que hay en la tabla 'flags'
y ahi nos mostrara la bandera.
```
## Referencias
```

```
