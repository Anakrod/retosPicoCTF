# Nombre del reto
### Pixelated	
## Objetivo
```
I have these 2 images, can you make a flag out of them? [scrambled1.png](https://mercury.picoctf.net/static/49743139fb7c10765dbf462d40987d2a/scrambled1.png) [scrambled2.png](https://mercury.picoctf.net/static/49743139fb7c10765dbf462d40987d2a/scrambled2.png)

HINT1: [https://en.wikipedia.org/wiki/Visual_cryptography](https://en.wikipedia.org/wiki/Visual_cryptography)

HINT2: Think of different ways you can "stack" images


```
## Solucion
``` shell 
se descarga lo solicitado
java -jar /stegsolve.jar

┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/crypto]
└─$ java -jar /opt/stegsolve.jar 
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true
                                    
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/crypto]
└─$ 
Descargamos stegsolve y lo corremos, nos abrira una ventana y aqui le indicaremos las imagenes que queremos unir y ahi estara la bandera.

picoCTF{2a4d45c7}
```
## Referencias
```

```
