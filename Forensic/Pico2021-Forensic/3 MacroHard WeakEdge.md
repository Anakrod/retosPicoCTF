# Nombre del reto
### MacroHard WeakEdge	
## Objetivo
```
I've hidden a flag in this file. Can you find it? [Forensics is fun.pptm](https://mercury.picoctf.net/static/d3dd8cd51524d9fafcccd1b7d55f85e7/Forensics is fun.pptm)
```
## Solucion
``` shell 
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF]
└─$ mkdir MacroHard
                                                                          
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF]
└─$ cd MacroHard 
                                                                          
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/MacroHard]
└─$ wget https://mercury.picoctf.net/static/d3dd8cd51524d9fafcccd1b7d55f85e7/Forensics%20is%20fun.pptm
--2022-10-11 08:46:15--  https://mercury.picoctf.net/static/d3dd8cd51524d9fafcccd1b7d55f85e7/Forensics%20is%20fun.pptm
Resolviendo mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Conectando con mercury.picoctf.net (mercury.picoctf.net)[18.189.209.142]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 100093 (98K) [application/octet-stream]
Grabando a: «Forensics is fun.pptm»

Forensics is fun.p 100%[==============>]  97.75K  41.1KB/s    en 2.4s    

2022-10-11 08:46:22 (41.1 KB/s) - «Forensics is fun.pptm» guardado [100093/100093]

                                                                          
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/MacroHard]
└─$ ls
'Forensics is fun.pptm'
                                                                          
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/MacroHard]
└─$ unzip Forensics\ is\ fun.pptm 
Archive:  Forensics is fun.pptm
  inflating: [Content_Types].xml     
  inflating: _rels/.rels             
  inflating: ppt/presentation.xml    
  .....
  
  ppt/slideLayouts/_rels/slideLayout11.xml.rels  
  inflating: ppt/theme/theme1.xml    
 extracting: docProps/thumbnail.jpeg  
  inflating: ppt/vbaProject.bin      
  inflating: ppt/presProps.xml       
  inflating: ppt/viewProps.xml       
  inflating: ppt/tableStyles.xml     
  inflating: docProps/core.xml       
  inflating: docProps/app.xml        
  inflating: ppt/slideMasters/hidden  
                                                                          
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/MacroHard]
└─$ ls
'[Content_Types].xml'   docProps  'Forensics is fun.pptm'   ppt   _rels
                                                                          
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/MacroHard]
└─$ cd ppt      
                                                                          
┌──(anitars㉿kali)-[~/…/hacking/picoCTF/MacroHard/ppt]
└─$ ls               
presentation.xml  slideLayouts  tableStyles.xml  viewProps.xml
presProps.xml     slideMasters  theme
_rels             slides        vbaProject.bin
                                                                          
┌──(anitars㉿kali)-[~/…/hacking/picoCTF/MacroHard/ppt]
└─$ cd slideMasters                                              
                                            ┌──(anitars㉿kali)-[~/…/picoCTF/MacroHard/ppt/slideMasters]
└─$ ls
hidden  _rels  slideMaster1.xml
                                                                          
┌──(anitars㉿kali)-[~/…/picoCTF/MacroHard/ppt/slideMasters]
└─$ cat hidden                                                 
Z m x h Z z o g c G l j b 0 N U R n t E M W R f d V 9 r b j B 3 X 3 B w d H N f c l 9 6 M X A 1 f Q                                                                          
┌──(anitars㉿kali)-[~/…/picoCTF/MacroHard/ppt/slideMasters]
└─$ cat hidden | tr -d ' '
ZmxhZzogcGljb0NURntEMWRfdV9rbjB3X3BwdHNfcl96MXA1fQ                                                                          
┌──(anitars㉿kali)-[~/…/picoCTF/MacroHard/ppt/slideMasters]
└─$ cat hidden | tr -d ' ' | base64 -d
flag: picoCTF{D1d_u_kn0w_ppts_r_z1p5}base64: entrada inválida
                                                                          
┌──(anitars㉿kali)-[~/…/picoCTF/MacroHard/ppt/slideMasters]
└─$ 


Descargamos, descomprimimos, entramos a la carpeta ppt, despues a slideMaster, leemos "hidden", y codificamos a base64 para encontrar la bandera.
```
## Referencias
```

```
