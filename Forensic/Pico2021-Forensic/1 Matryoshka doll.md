# Nombre del reto
### Matryoshka doll
## Objetivo
```
Matryoshka dolls are a set of wooden dolls of decreasing size placed one inside another. What's the final one? Image: [this](https://mercury.picoctf.net/static/2978e1270538613cd8181c7b0dabe9bd/dolls.jpg)

HINT1: Wait, you can hide files inside files? But how do you find them?
HINT2: Make sure to submit the flag as picoCTF{XXXXX}
```
## Solucion
``` shell 

┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF]
└─$ ls
 Forensic    'Pico 2021'       Untitled.md         'Web Pico2022'
'Pico 2019'  'PicoMini 2022'  'Web Pico 2019 pt1'
                                                                          
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF]
└─$ wget https://mercury.picoctf.net/static/2978e1270538613cd8181c7b0dabe9bd/dolls.jpg
--2022-10-11 08:16:16--  https://mercury.picoctf.net/static/2978e1270538613cd8181c7b0dabe9bd/dolls.jpg
Resolviendo mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Conectando con mercury.picoctf.net (mercury.picoctf.net)[18.189.209.142]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 651622 (636K) [application/octet-stream]
Grabando a: «dolls.jpg»

dolls.jpg          100%[==============>] 636.35K  24.3KB/s    en 47s     

2022-10-11 08:17:05 (13.5 KB/s) - «dolls.jpg» guardado [651622/651622]

                                                                          
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF]
└─$ binwalk dolls.jpg -e

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 594 x 1104, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
272492        0x4286C         Zip archive data, at least v2.0 to extract, compressed size: 378942, uncompressed size: 383937, name: base_images/2_c.jpg
651600        0x9F150         End of Zip archive, footer length: 22

                                                                          
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF]
└─$ ls
 dolls.jpg             'Pico 2019'       Untitled.md
 _dolls.jpg.extracted  'Pico 2021'      'Web Pico 2019 pt1'
 Forensic              'PicoMini 2022'  'Web Pico2022'
                                                                          
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF]
└─$ cd _dolls.jpg.extracted/base_images 
                                                                          
┌──(anitars㉿kali)-[~/…/hacking/picoCTF/_dolls.jpg.extracted/base_images]
└─$ ls                  
2_c.jpg
                                                                          
┌──(anitars㉿kali)-[~/…/hacking/picoCTF/_dolls.jpg.extracted/base_images]
└─$ binwalk 2_c.jpg     

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 526 x 1106, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
187707        0x2DD3B         Zip archive data, at least v2.0 to extract, compressed size: 196042, uncompressed size: 201444, name: base_images/3_c.jpg
383804        0x5DB3C         End of Zip archive, footer length: 22
383915        0x5DBAB         End of Zip archive, footer length: 22

                                                                          
┌──(anitars㉿kali)-[~/…/hacking/picoCTF/_dolls.jpg.extracted/base_images]
└─$ ls
2_c.jpg
                                                                          
┌──(anitars㉿kali)-[~/…/hacking/picoCTF/_dolls.jpg.extracted/base_images]
└─$ binwalk 2_c.jpg -e

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 526 x 1106, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
187707        0x2DD3B         Zip archive data, at least v2.0 to extract, compressed size: 196042, uncompressed size: 201444, name: base_images/3_c.jpg
383804        0x5DB3C         End of Zip archive, footer length: 22
383915        0x5DBAB         End of Zip archive, footer length: 22

                                                                          
┌──(anitars㉿kali)-[~/…/hacking/picoCTF/_dolls.jpg.extracted/base_images]
└─$ ls
2_c.jpg  _2_c.jpg.extracted
                                                                          
┌──(anitars㉿kali)-[~/…/hacking/picoCTF/_dolls.jpg.extracted/base_images]
└─$ cd _2_c.jpg.extracted/base_images  
                                                                          
┌──(anitars㉿kali)-[~/…/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images]
└─$ binwalk 3_c.jpg -e

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 428 x 1104, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
123606        0x1E2D6         Zip archive data, at least v2.0 to extract, compressed size: 77650, uncompressed size: 79806, name: base_images/4_c.jpg
201422        0x312CE         End of Zip archive, footer length: 22

                                                                          
┌──(anitars㉿kali)-[~/…/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images]
└─$ ls
3_c.jpg  _3_c.jpg.extracted
                                                                          
┌──(anitars㉿kali)-[~/…/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images]
└─$ cd _3_c.jpg.extracted/base_images 
                                                                          
┌──(anitars㉿kali)-[~/…/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images]
└─$ ls
4_c.jpg
                                                                          
┌──(anitars㉿kali)-[~/…/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images]
└─$ binwalk 4_c.jpg -e

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 320 x 768, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
79578         0x136DA         Zip archive data, at least v2.0 to extract, compressed size: 62, uncompressed size: 81, name: flag.txt
79784         0x137A8         End of Zip archive, footer length: 22

                                                                          
┌──(anitars㉿kali)-[~/…/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images]
└─$ cd _4_c.jpg.extracted 
                                                                          
┌──(anitars㉿kali)-[~/…/base_images/_3_c.jpg.extracted/base_images/_4_c.jpg.extracted]
└─$ ls
136DA.zip  flag.txt
                                                                          
┌──(anitars㉿kali)-[~/…/base_images/_3_c.jpg.extracted/base_images/_4_c.jpg.extracted]
└─$ cat flag.txt | grep pico
                                                                          
┌──(anitars㉿kali)-[~/…/base_images/_3_c.jpg.extracted/base_images/_4_c.jpg.extracted]
└─$ cat flag.txt            
picoCTF{4cf7ac000c3fb0fa96fb92722ffb2a32}                                                                          
┌──(anitars㉿kali)-[~/…/base_images/_3_c.jpg.extracted/base_images/_4_c.jpg.extracted]
└─$ 
picoCTF{4cf7ac000c3fb0fa96fb92722ffb2a32}



Vamos descomprimiendo lo que hay en cada imagen con el comando "binwalk [nombre] -e" hasta encontrar la bandera.
```

## Referencias
```

```
