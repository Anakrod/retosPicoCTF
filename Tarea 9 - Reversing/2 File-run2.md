# Nombre del reto
### File-run2	
## Objetivo
```
Another program, but this time, it seems to want some input. What happens if you try to run it on the command line with input "Hello!"? Download the program [here](https://artifacts.picoctf.net/c/353/run).

HINT: Try running it and add the phrase "Hello!" with a space in front (i.e. "./run Hello!")
```
## Solucion
``` shell 
┌──(anitars㉿kali)-[~/…/hacking/picoCTF/reversing_tarea/filerun1]
└─$ file run.1 
run.1: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, BuildID[sha1]=e923d195967f2f793c6de52cee78b8fb7f3c0a2a, for GNU/Linux 3.2.0, not stripped
                                                                          
┌──(anitars㉿kali)-[~/…/hacking/picoCTF/reversing_tarea/filerun1]
└─$ chmod +x run.1                                                                          
┌──(anitars㉿kali)-[~/…/hacking/picoCTF/reversing_tarea/filerun1]
└─$ ./run.1 Hello!
The flag is: picoCTF{F1r57_4rgum3n7_f65ed63e}                                                                          
┌──(anitars㉿kali)-[~/…/hacking/picoCTF/reversing_tarea/filerun1]
└─$ 

FLAG: 'picoCTF{F1r57_4rgum3n7_f65ed63e}'

Descargamos el programa que se nos indica y seguimos las pistas que nos da, lo hacemos ejecutable y lo corremos de la siguiente manera './run.1 Hello!' agregando el argumento 'Hello!' y asi obtenemos la bandera.
```
## Referencias
```

```
