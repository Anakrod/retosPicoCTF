# Nombre del reto
### What lies within
## Objetivo
```
There's something in the [building](https://jupiter.challenges.picoctf.org/static/011955b303f293d60c8116e6a4c5c84f/buildings.png). Can you retrieve the flag?

```
## Solucion
```
picoCTF{h1d1ng_1n_th3_b1t5}

┌──(anitars㉿kali)-[~/picoCTF/forensic]
└─$ zsteg -a buildings.png | grep pico
b1,rgb,lsb,xy       .. text: "picoCTF{h1d1ng_1n_th3_b1t5}"
                                                                           
┌──(anitars㉿kali)-[~/picoCTF/forensic]
└─$ 

Hay varias formas de poder encontrar la bandera, una de ellas es por medio de un decodificador en linea, en la que le damos la imagen y nos devolvera la decodificacion donde se encontrara la bandera.

la otra manera sera descargando 'zsteg' que nos mostrada mucha informacion en la cual estara la bandera, si agregamos un grep nos dara la bandera solamente.
```
## Referencias
```
metadatos
https://stylesuxx.github.io/steganography/
```
