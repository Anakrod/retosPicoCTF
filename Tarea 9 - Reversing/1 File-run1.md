# Nombre del reto
### 1File-run1	
## Objetivo
```
A program has been provided to you, what happens if you try to run it on the command line? Download the program [here](https://artifacts.picoctf.net/c/310/run).

HINT1: To run the program at all, you must make it executable (i.e. `$ chmod +x run`)
HINT2: Try running it by adding a '.' in front of the path to the file (i.e. `$ ./run`)
```
## Solucion
``` shell 
┌──(anitars㉿kali)-[~/…/hacking/picoCTF/reversing_tarea/filerun1]
└─$ file run   
run: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, BuildID[sha1]=0514683255a9ef58abe3c729e7418d07210a759e, for GNU/Linux 3.2.0, not stripped
                                                                          
┌──(anitars㉿kali)-[~/…/hacking/picoCTF/reversing_tarea/filerun1]
└─$ chmod +x run
                                                                          
┌──(anitars㉿kali)-[~/…/hacking/picoCTF/reversing_tarea/filerun1]
└─$ ./run                     
The flag is: picoCTF{U51N6_Y0Ur_F1r57_F113_47cf2b7b}                                                                          
┌──(anitars㉿kali)-[~/…/hacking/picoCTF/reversing_tarea/filerun1]
└─$ 

FLAG: 'picoCTF{U51N6_Y0Ur_F1r57_F113_47cf2b7b}'


Descargamos el programa que se nos indica y seguimos las pistas que nos da, lo hacemos ejecutable y lo corremos de la siguiente manera './run' y asi obtenemos la bandera.
```
## Referencias
```

```
