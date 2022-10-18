# Nombre del reto
### tunn3l v1s10n
## Objetivo
```
We found this [file](https://mercury.picoctf.net/static/01be2b38ba97802285a451b94505ea75/tunn3l_v1s10n). Recover the flag.

Hint: Weird that it won't display right...
```
## Solucion
``` shell 
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/tunnel]
└─$ ls
tunn3l_v1s10n
                                                                           
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/tunnel]
└─$ file tunn3l_v1s10n
tunn3l_v1s10n: data
                                                                           
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/tunnel]
└─$ hexeditor tunn3l_v1s10n 
                                                                           
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/tunnel]
└─$ hexeditor tunn3l_v1s10n
                                                                           
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/tunnel]
└─$ hexeditor tunn3l_v1s10n
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/tunnel]
└─$ mv tunn3l_v1s10n tunnel.bmp
                                                                           
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/tunnel]
└─$ open tunnel.bmp 
                                                                           
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/tunnel]
└─$ Gtk-Message: 21:01:33.396: Failed to load module "gail"

** (gimp-2.10:33117): WARNING **: 21:01:33.436: (../atk-adaptor/bridge.c:1018):atk_bridge_adaptor_init: runtime check failed: (root)

                                                                           
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/tunnel]
└─$ hexeditor tunnel.bmp               
                                                                           
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/tunnel]
└─$ open tunnel.bmp
                                                                           
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/tunnel]
└─$ Gtk-Message: 21:37:39.014: Failed to load module "gail"

** (gimp-2.10:40854): WARNING **: 21:37:44.323: (../atk-adaptor/bridge.c:1018):atk_bridge_adaptor_init: runtime check failed: (root)

                                                                           
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/tunnel]
└─$ ls                            
tunnel.bmp
                                                                           
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/tunnel]
└─$ hexeditor tunnel.bmp
                                                                           
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/tunnel]
└─$ open tunnel.bmp     
                                                                           
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/tunnel]
└─$ Gtk-Message: 21:54:02.539: Failed to load module "gail"

** (gimp-2.10:44919): WARNING **: 21:54:03.901: (../atk-adaptor/bridge.c:1018):atk_bridge_adaptor_init: runtime check failed: (root)

                                                                           
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/tunnel]
└─$ hexeditor tunnel.bmp
                                                                           
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/tunnel]
└─$ open tunnel.bmp     
                                                                           
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/tunnel]
└─$ Gtk-Message: 21:58:44.171: Failed to load module "gail"

** (gimp-2.10:46184): WARNING **: 21:58:44.629: (../atk-adaptor/bridge.c:1018):atk_bridge_adaptor_init: runtime check failed: (root)

                                                                           
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/tunnel]
└─$ hexeditor tunnel.bmp
                                                                           
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/tunnel]
└─$ open tunnel.bmp     
                                                                           
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/tunnel]
└─$ Gtk-Message: 22:01:09.638: Failed to load module "gail"

** (gimp-2.10:46839): WARNING **: 22:01:09.962: (../atk-adaptor/bridge.c:1018):atk_bridge_adaptor_init: runtime check failed: (root)

                                                                           
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/tunnel]
└─$ hexeditor tunnel.bmp
                                                                           
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/tunnel]
└─$ open tunnel.bmp     
                                                                           
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/tunnel]
└─$ Gtk-Message: 22:03:02.228: Failed to load module "gail"

** (gimp-2.10:47371): WARNING **: 22:03:02.286: (../atk-adaptor/bridge.c:1018):atk_bridge_adaptor_init: runtime check failed: (root)

                                                                           
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/tunnel]
└─$ 

picoCTF{qui1t3_a_v13w_2020}
```
## Referencias
```
reparamos el tamaño del encabezado,
reparamos el decirle donde comienzan los datos
28 00 00 00 28 00 en las ultimas dos columnas en la primera fila.
segunda fila 40 03, segunda columna (offset 12)

revisamos cada que se modifique la imagen hasta poder visualizar la bandera.
```
