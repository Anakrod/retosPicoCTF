# Nombre del reto
### Trivial Flag Transfer Protocol	
## Objetivo
```
Figure out how they moved the [flag](https://mercury.picoctf.net/static/e4836d9bcc740d457f4331d68129a0bc/tftp.pcapng).

HINT: What are some other ways to hide data?
```
## Solucion
``` shell 
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/Trivial_Flag]
└─$ ls
tftp.pcapng
                                                                          
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/Trivial_Flag]
└─$ file tftp.pcapng 
tftp.pcapng: pcapng capture file - version 1.0
                                                                          
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/Trivial_Flag]
└─$ wireshark tftp.pcapng   
 ** (wireshark:12736) 18:23:06.349258 [GUI WARNING] -- FIX Add drag reordering to UAT dialog


^Z
zsh: suspended  wireshark tftp.pcapng
                                                                          
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/Trivial_Flag]
└─$ ls
instructions.txt  picture2.bmp  plan         tftp.pcapng
picture1.bmp      picture3.bmp  program.deb
                                                                          
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/Trivial_Flag]
└─$ ls -la
total 89009
drwxrwx--- 1 root vboxsf     4096 oct 17 18:27 .
drwxrwx--- 1 root vboxsf     4096 oct 16 20:46 ..
-rwxrwx--- 1 root vboxsf      113 oct 17 18:27 instructions.txt
-rwxrwx--- 1 root vboxsf   824518 oct 17 18:27 picture1.bmp
-rwxrwx--- 1 root vboxsf 36578358 oct 17 18:27 picture2.bmp
-rwxrwx--- 1 root vboxsf  1466574 oct 17 18:27 picture3.bmp
-rwxrwx--- 1 root vboxsf       59 oct 17 18:27 plan
-rwxrwx--- 1 root vboxsf   138310 oct 17 18:27 program.deb
-rwxrwx--- 1 root vboxsf 52116496 mar 15  2021 tftp.pcapng
                                                                          
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/Trivial_Flag]
└─$ cat instructions.txt 
GSGCQBRFAGRAPELCGBHEGENSSVPFBJRZHFGQVFTHVFRBHESYNTGENAFSRE.SVTHERBHGNJNLGBUVQRGURSYNTNAQVJVYYPURPXONPXSBEGURCYNA
                                                                          
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/Trivial_Flag]
└─$ cat instructions.txt | base32 -d
4�(%��b0NC��^P�99M
�g�b�Xl�F���base32: entrada inválida
                                                                          
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/Trivial_Flag]
└─$ cat instructions.txt | base64 -d
!�@Ed@<B�▒�▒CRIS��YQ�TT�TTAD�51�4RDbase64: entrada inválida
                                                                          
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/Trivial_Flag]
└─$ cat instructions.txt | tr [A-Z] [N-ZA-N]
TFTPDOESNTENCRYPTOURTRAFFICSOWEMUSTDISGUISEOURFLAGTRANSFER.FIGUREOUTAWAYTOHIDETHEFLAGANDIWILLCHECKBACKFORTHEPLAN
                                                                          
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/Trivial_Flag]
└─$ 
[1]  + killed     wireshark tftp.pcapng
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/Trivial_Flag]
└─$ ls -la

total 89009
drwxrwx--- 1 root vboxsf     4096 oct 17 18:27 .
drwxrwx--- 1 root vboxsf     4096 oct 16 20:46 ..
-rwxrwx--- 1 root vboxsf      113 oct 17 18:27 instructions.txt
-rwxrwx--- 1 root vboxsf   824518 oct 17 18:27 picture1.bmp
-rwxrwx--- 1 root vboxsf 36578358 oct 17 18:27 picture2.bmp
-rwxrwx--- 1 root vboxsf  1466574 oct 17 18:27 picture3.bmp
-rwxrwx--- 1 root vboxsf       59 oct 17 18:27 plan
-rwxrwx--- 1 root vboxsf   138310 oct 17 18:27 program.deb
-rwxrwx--- 1 root vboxsf 52116496 mar 15  2021 tftp.pcapng
                                                                          
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/Trivial_Flag]
└─$ 
                                                                          
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/Trivial_Flag]
└─$ cat plan | tr [A-Z] [N-ZA-N]
IUSEDTHEPROGRAMANDHIDITWITH-DUEDILIGENCE.CHECKOUTTHEPHOTOS
                                                                          
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/Trivial_Flag]
└─$ sudo dpkg program.deb    
[sudo] contraseña para anitars: 
Lo siento, pruebe otra vez.
[sudo] contraseña para anitars: 
Lo siento, pruebe otra vez.
[sudo] contraseña para anitars: 
dpkg: error: se necesita una opción de acción

Escriba dpkg --help para ayuda sobre instalar y desinstalar paquetes [*];
Use `apt' o `aptitude' para una gestión de los paquetes más amigable;
Escriba dpkg -Dhelp para una lista de los valores de depuración de dpkg;
Escriba dpkg --force-help para una lista de las opciones para forzar cosas;
Escriba dpkg-deb --help para obtener ayuda sobre manipulación de archivos .deb;

Las opciones marcadas con [*] producen una salida extensa,
¡fíltrela con `less' o con `more'!
                                                                          
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/Trivial_Flag]
└─$ sudo dpkg -i program.deb
dpkg: atención: desactualizando steghide de 0.5.1-15 a 0.5.1-9.1+b1
(Leyendo la base de datos ... 324183 ficheros o directorios instalados actualmente.)
Preparando para desempaquetar program.deb ...
Desempaquetando steghide (0.5.1-9.1+b1) sobre (0.5.1-15) ...
Configurando steghide (0.5.1-9.1+b1) ...
Procesando disparadores para man-db (2.10.2-3) ...
Procesando disparadores para kali-menu (2022.4.1) ...
                                                                          
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/Trivial_Flag]
└─$ steghide --extract -sf picture1.bmp
Anotar salvoconducto: 
steghide: �no pude extraer ning�n dato con ese salvoconducto!
                                                                          
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/Trivial_Flag]
└─$ steghide --extract -sf picture1.bmp -p DUEDILIGENCE
steghide: �no pude extraer ning�n dato con ese salvoconducto!
                                                                          
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/Trivial_Flag]
└─$ steghide --extract -sf picture2.bmp -p DUEDILIGENCE
steghide: �no pude extraer ning�n dato con ese salvoconducto!
                                                                          
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/Trivial_Flag]
└─$ steghide --extract -sf picture3.bmp -p DUEDILIGENCE
anot� los datos extra�dos e/"flag.txt".
                                                                          
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/Trivial_Flag]
└─$ cat flag.txt                
picoCTF{h1dd3n_1n_pLa1n_51GHT_18375919}
                                                                          
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/Trivial_Flag]
└─$ 



Abrimos lo descargado mediante wireshark, descargamos los paquetes, y en la linea de comandos instalamos los siguiente sudo dpkg -i program.deb, despues haciendo uso del comando "steghide" buscamos extraer lo que hay dentro de las imagenes "picture1.bmp, picture2.bmp y picture3.bmp", hasta encontrar la bandera, la cual se encuentra en "picture3.bmp" en un documento .txt.
```
## Referencias
```

```
