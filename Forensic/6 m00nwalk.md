# Nombre del reto
### m00nwalk	

## Objetivo
```
Decode this [message](https://jupiter.challenges.picoctf.org/static/14393e18d98fedbaedbc28896d7ef31a/message.wav) from the moon.
```
## Solucion
``` shell
┌──(anitars㉿kali)-[~/sstv]
└─$ sudo python setup.py install
running install
/usr/lib/python3/dist-packages/setuptools/command/install.py:34:

Using /usr/lib/python3/dist-packages
Finished processing dependencies for sstv==0.1
                                                                           
┌──(anitars㉿kali)-[~/sstv]
└─$ cd ..  
                                                                           
┌──(anitars㉿kali)-[~]
└─$ ls
Descargas   Escritorio  hacking  Imágenes  picoCTF     Público  Vídeos
Documentos  file        hash     Música    Plantillas  sstv
                                                                           
┌──(anitars㉿kali)-[~]
└─$ cd picoCTF/forensic 
                                                                           
┌──(anitars㉿kali)-[~/picoCTF/forensic]
└─$ ls
buildings.png  flag.png    message.wav      pico_img.png
capture.pcap   garden.jpg  nano.12371.save  sstv
                                                                                                                                                   
┌──(anitars㉿kali)-[~/picoCTF/forensic]
└─$ sstv message.wav 
usage: sstv [-h] [-d AUDIO_FILE] [-o OUTPUT_FILE] [-s SKIP] [-V]
            [--list-modes] [--list-audio-formats] [--list-image-formats]
sstv: error: unrecognized arguments: message.wav
                                                                           
┌──(anitars㉿kali)-[~/picoCTF/forensic]
└─$ sstv -d message.wav -o result.png
[sstv] Searching for calibration header... Found!    
[sstv] Detected SSTV mode Scottie 1
[sstv] Decoding image...   [#########################################] 100%
[sstv] Drawing image data...
[sstv] ...Done!
                                                                           
┌──(anitars㉿kali)-[~/picoCTF/forensic]
└─$ ls
buildings.png  flag.png    message.wav      pico_img.png  sstv
capture.pcap   garden.jpg  nano.12371.save  result.png
                                                                           
┌──(anitars㉿kali)-[~/picoCTF/forensic]
└─$ open result.png 

picoCTF{beep_boop_im_in_space}



Instalamos sstv, y convertimos el audio descargado a .png, para de esta forma poder encontrar la bandera.
```
## Referencias
```
https://github.com/colaclanth/sstv
```
