# Nombre del reto
### Operation Oni	
## Objetivo
```
Download this disk image, find the key and log into the remote machine. Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.
```
## Solucion
``` shell 

┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/operation]
└─$ gzip -d disk.img.gz 
                                                                          
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/operation]
└─$ mmls disk.img      
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000206847   0000204800   Linux (0x83)
003:  000:001   0000206848   0000471039   0000264192   Linux (0x83)
                                                                          
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/operation]
└─$ fls -o 206848 disk.img 
d/d 458:        home
d/d 11: lost+found
d/d 12: boot
d/d 13: etc
d/d 79: proc
d/d 80: dev
d/d 81: tmp
d/d 82: lib
d/d 85: var
d/d 94: usr
d/d 104:        bin
d/d 118:        sbin
d/d 464:        media
d/d 468:        mnt
d/d 469:        opt
d/d 470:        root
d/d 471:        run
d/d 473:        srv
d/d 474:        sys
V/V 33049:      $OrphanFiles
                                                                          
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/operation]
└─$ fls -o 206848 disk.img 470
r/r 2344:       .ash_history
d/d 3916:       .ssh
                                                                           
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/operation]
└─$ fls -o 206848 disk.img 3916
r/r 2345:       id_ed25519
r/r 2346:       id_ed25519.pub
                                                                           
──(anitars㉿kali)-[~/hacking/hacking/picoCTF/operation]
└─$ icat -o 206848 disk.img 2345           
-----BEGIN OPENSSH PRIVATE KEY-----
b3BlbnNzaC1rZXktdjEAAAAABG5vbmUAAAAEbm9uZQAAAAAAAAABAAAAMwAAAAtzc2gtZW
QyNTUxOQAAACBgrXe4bKNhOzkCLWOmk4zDMimW9RVZngX51Y8h3BmKLAAAAJgxpYKDMaWC
gwAAAAtzc2gtZWQyNTUxOQAAACBgrXe4bKNhOzkCLWOmk4zDMimW9RVZngX51Y8h3BmKLA
AAAECItu0F8DIjWxTp+KeMDvX1lQwYtUvP2SfSVOfMOChxYGCtd7hso2E7OQItY6aTjMMy
KZb1FVmeBfnVjyHcGYosAAAADnJvb3RAbG9jYWxob3N0AQIDBAUGBw==
-----END OPENSSH PRIVATE KEY-----
                                                                           
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/operation]
└─$ nano data     
                                                                           
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/operation]
└─$ cat key_file 
-----BEGIN OPENSSH PRIVATE KEY-----
b3BlbnNzaC1rZXktdjEAAAAABG5vbmUAAAAEbm9uZQAAAAAAAAABAAAAMwAAAAtzc2gtZW
QyNTUxOQAAACBgrXe4bKNhOzkCLWOmk4zDMimW9RVZngX51Y8h3BmKLAAAAJgxpYKDMaWC
gwAAAAtzc2gtZWQyNTUxOQAAACBgrXe4bKNhOzkCLWOmk4zDMimW9RVZngX51Y8h3BmKLA
AAAECItu0F8DIjWxTp+KeMDvX1lQwYtUvP2SfSVOfMOChxYGCtd7hso2E7OQItY6aTjMMy
KZb1FVmeBfnVjyHcGYosAAAADnJvb3RAbG9jYWxob3N0AQIDBAUGBw==
-----END OPENSSH PRIVATE KEY-----
                                                                           
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/operation]
└─$ chmod +00 key_file               
                                                                           
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/operation]
└─$ ls -la
total 235557
drwxrwx--- 1 root vboxsf      4096 oct 17  2022 .
drwxrwx--- 1 root vboxsf      4096 oct 16 20:46 ..
-rwxrwx--- 1 root vboxsf     27364 oct 12 22:26 disk2.img.gz
-rwxrwx--- 1 root vboxsf 241172480 mar 15  2022 disk.img
-rwxrwx--- 1 root vboxsf       411 oct 17  2022 key_file
                                                                           
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/operation]
└─$ chmod x00 key_file
chmod: modo inválido: «x00»
Pruebe 'chmod --help' para más información.
                                                                           
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/operation]
└─$ chmod +80 key_file
chmod: modo inválido: «+80»
Pruebe 'chmod --help' para más información.
                                                                           
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/operation]
└─$ ssh -i key_file -p 62404 ctf-player@saturn.picoctf.net
The authenticity of host '[saturn.picoctf.net]:62404 ([18.217.86.78]:62404)' can't be established.
ED25519 key fingerprint is SHA256:5gIm/EJ9bYnoH4qed83W5HXLfN1DO55849f6Lze0lx8.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[saturn.picoctf.net]:62404' (ED25519) to the list of known hosts.
Welcome to Ubuntu 20.04.3 LTS (GNU/Linux 5.13.0-1025-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

This system has been minimized by removing packages and content that are
not required on a system that users do not log into.

To restore this content, you can run the 'unminimize' command.

The programs included with the Ubuntu system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
applicable law.

ctf-player@challenge:~$ ls
flag.txt
ctf-player@challenge:~$ cat flag.txt
picoCTF{k3y_5l3u7h_339601ed}ctf-player@challenge:~$ Connection to saturn.picoctf.net closed by remote host.
Connection to saturn.picoctf.net closed.
                                                                           
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/operation]
└─$ '


descargamos la imagen que nos da, seguido de eso la descomprimimos y haremos uso de los comando 'mmls, fls, icat' despues nos conectaremos con llave que nos dan, listaremos los archivos que hay y leeremos 'flag.txt' de tal manera que asi obtengamos la bandera.
```
## Referencias
```
operation oni

mmls disk.img

fls -o 206848 disk.img

```

