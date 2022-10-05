# Nombre del reto
	
## Objetivo
```
This is a really weird text file [TXT](https://jupiter.challenges.picoctf.org/static/e7e5d188621ee705ceeb0452525412ef/flag.txt)? Can you find the flag?
```
## Solucion
``` shell
	┌──(anitars㉿kali)-[~/picoCTF/forensic]
└─$ strings flag.txt | grep pico
                                                                           
┌──(anitars㉿kali)-[~/picoCTF/forensic]
└─$ hexeditor flag.txt     
                                                                           
┌──(anitars㉿kali)-[~/picoCTF/forensic]
└─$ file flag.png    
flag.png: cannot open `flag.png' (No such file or directory)
                                                                           
┌──(anitars㉿kali)-[~/picoCTF/forensic]
└─$ open flag.png
                                                                           
┌──(anitars㉿kali)-[~/picoCTF/forensic]
└─$ mv flag.txt flag.png
                                                                           
┌──(anitars㉿kali)-[~/picoCTF/forensic]
└─$ open flag.png       
                                                                           
┌──(anitars㉿kali)-[~/picoCTF/forensic]
└─$ 

picoCTF{now_you_know_about_extensions}

Descargamos lo que se nos indica, tratamos de abrirlo con heazaeditor, pero no funciona, despues procedemos a cambiar, de ser un .txt a un .png para de esa manera poder tener acceso a la bandera.
```
## Referencias
```
magic bytes
```
