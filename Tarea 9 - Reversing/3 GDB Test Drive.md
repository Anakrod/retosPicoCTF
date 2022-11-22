# Nombre del reto
### GDB Test Drive	
## Objetivo
```
Can you get the flag? Download this [binary](https://artifacts.picoctf.net/c/117/gdbme). Here's the test drive instructions:

-   `$ chmod +x gdbme`
-   `$ gdb gdbme`
-   `(gdb) layout asm`
-   `(gdb) break *(main+99)`
-   `(gdb) run`
-   `(gdb) jump *(main+104)`
```
## Solucion
``` shell 

┌──(anitars㉿kali)-[~/…/hacking/picoCTF/reversing_tarea/gdb]
└─$ gdb gdbme           
GNU gdb (Debian 12.1-4) 12.1
Copyright (C) 2022 Free Software Foundation, Inc.
License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>
This is free software: you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.
Type "show copying" and "show warranty" for details.
This GDB was configured as "x86_64-linux-gnu".
Type "show configuration" for configuration details.
For bug reporting instructions, please see:
<https://www.gnu.org/software/gdb/bugs/>.
Find the GDB manual and other documentation resources online at:
    <http://www.gnu.org/software/gdb/documentation/>.

For help, type "help".
Type "apropos word" to search for commands related to "word"...
Reading symbols from gdbme...
(No debugging symbols found in gdbme)
(gdb) layout asm
                                                                          
┌──(anitars㉿kali)-[~/…/hacking/picoCTF/reversing_tarea/gdb]
└─$ 

Seguimos los pasos que se nos indica en la descripcion y en ultimo paso encontraremos la bandera.

FLAG: 'picoCTF{d3bugg3r_dr1v3_7776d758}'
```
## Referencias
```

```
