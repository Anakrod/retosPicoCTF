# Nombre del reto
### Information	
## Objetivo
```
Files can always be changed in a secret way. Can you find the flag? [cat.jpg](https://mercury.picoctf.net/static/d1375e383810d8d957c04eef9e345732/cat.jpg)

HINT1: Look at the details of the file
HINT2: Make sure to submit the flag as picoCTF{XXXXX}
```
## Solucion
``` shell 
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/Forensic]
└─$ mkdir information  
                                                                          
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/Forensic]
└─$ cd information 
                                                                          
┌──(anitars㉿kali)-[~/…/hacking/picoCTF/Forensic/information]
└─$ wget https://mercury.picoctf.net/static/d1375e383810d8d957c04eef9e345732/cat.jpg      
--2022-10-20 21:18:15--  https://mercury.picoctf.net/static/d1375e383810d8d957c04eef9e345732/cat.jpg
Resolviendo mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Conectando con mercury.picoctf.net (mercury.picoctf.net)[18.189.209.142]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 878136 (858K) [application/octet-stream]
Grabando a: «cat.jpg»

cat.jpg            100%[==============>] 857.55K  1.19MB/s    en 0.7s    

2022-10-20 21:18:16 (1.19 MB/s) - «cat.jpg» guardado [878136/878136]

                                                                          
┌──(anitars㉿kali)-[~/…/hacking/picoCTF/Forensic/information]
└─$ open cat.jpg  
                                                                          
┌──(anitars㉿kali)-[~/…/hacking/picoCTF/Forensic/information]
└─$ strings cat.jpg                    
JFIF
0Photoshop 3.0
8BIM
PicoCTF
http://ns.adobe.com/xap/1.0/
<?xpacket begin='
' id='W5M0MpCehiHzreSzNTczkc9d'?>
<x:xmpmeta xmlns:x='adobe:ns:meta/' x:xmptk='Image::ExifTool 10.80'>
<rdf:RDF xmlns:rdf='http://www.w3.org/1999/02/22-rdf-syntax-ns#'>
 <rdf:Description rdf:about=''
  xmlns:cc='http://creativecommons.org/ns#'>
  <cc:license rdf:resource='cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9'/>
 </rdf:Description>
 <rdf:Description rdf:about=''
  xmlns:dc='http://purl.org/dc/elements/1.1/'>
  <dc:rights>
   <rdf:Alt>
    <rdf:li xml:lang='x-default'>PicoCTF</rdf:li>
   </rdf:Alt>
  </dc:rights>
 </rdf:Description>
</rdf:RDF>
</x:xmpmeta>
                  
┌──(anitars㉿kali)-[~/…/hacking/picoCTF/Forensic/information]
└─$ strings cat.jpg | grep picoCTF
                                                                          
┌──(anitars㉿kali)-[~/…/hacking/picoCTF/Forensic/information]
└─$ exiftool cat.jpg     
ExifTool Version Number         : 12.44
File Name                       : cat.jpg
Directory                       : .
File Size                       : 878 kB
File Modification Date/Time     : 2021:03:15 12:24:46-06:00
File Access Date/Time           : 2022:10:20 21:18:28-05:00
File Inode Change Date/Time     : 2022:10:20 21:18:17-05:00
File Permissions                : -rwxrwx---
File Type                       : JPEG
File Type Extension             : jpg
MIME Type                       : image/jpeg
JFIF Version                    : 1.02
Resolution Unit                 : None
X Resolution                    : 1
Y Resolution                    : 1
Current IPTC Digest             : 7a78f3d9cfb1ce42ab5a3aa30573d617
Copyright Notice                : PicoCTF
Application Record Version      : 4
XMP Toolkit                     : Image::ExifTool 10.80
License                         : cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9
Rights                          : PicoCTF
Image Width                     : 2560
Image Height                    : 1598
Encoding Process                : Baseline DCT, Huffman coding
Bits Per Sample                 : 8
Color Components                : 3
Y Cb Cr Sub Sampling            : YCbCr4:2:0 (2 2)
Image Size                      : 2560x1598
Megapixels                      : 4.1
                                                                          
┌──(anitars㉿kali)-[~/…/hacking/picoCTF/Forensic/information]
└─$ zsteg -a buildings.png | grep pico
                                                                           
┌──(anitars㉿kali)-[~/…/hacking/picoCTF/Forensic/information]
└─$ zsteg -a cat.jpg | grep pico 
                                                                           
┌──(anitars㉿kali)-[~/…/hacking/picoCTF/Forensic/information]
└─$ 

Intentamos varias formas de encontrar la bandera, utilizamos 'strings' pero no nos da algo concreto, despues zteg, pero nada, despues usamos 'exiftool', el nombre de la lisencia parece extraño, sospechamos de ser base 64, usamos un convertidor y efectivamente, ahí esta la bandera.


picoCTF{the_m3tadata_1s_modified}

```
## Referencias
```
https://www.base64decode.org/
```
