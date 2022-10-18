# Nombre del reto
### Sleuthkit Intr	
## Objetivo
```
Download the disk image and use `mmls` on it to find the size of the Linux partition. Connect to the remote checker service to check your answer and get the flag. Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.

-   [Download disk image](https://artifacts.picoctf.net/c/114/disk.img.gz)
-   Access checker program: `nc saturn.picoctf.net 52279`
```
## Solucion
``` shell 
                                                                          
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/sleuthkit]
└─$ mmls disk.img 
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000204799   0000202752   Linux (0x83)
                                                                          
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/sleuthkit]
└─$  nc saturn.picoctf.net 52279
What is the size of the Linux partition in the given disk image?
Length in sectors: 202752
202752
Great work!
picoCTF{mm15_f7w!}
                                                                          
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/sleuthkit]
└─$ 

descomprimimos la imagen que descargamos previamente, utilizamos el comando 'mmls' que nos dara la informacion de la particion, despues ingresaremos el 'nc' que nos da en las instrucciones y nos pedira ingresar la longitud de la particion de linux (que nos da cuando ingresamos el comando 'mmls') y enseguida nos dara la bandera.

```
## Referencias
```
descomprimimos la imagen y damos el siguiente comando:
mmls disk.img

despues pegamos la nc  que nos da el reto y obtenemos la bandera

```




