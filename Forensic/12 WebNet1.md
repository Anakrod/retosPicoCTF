# Nombre del reto
### WebNet1
## Objetivo
```
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/capture.pcap) and [key](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/picopico.key). Recover the flag.

HINT1: Try using a tool like Wireshark.
HINT2: How can you decrypt the TLS stream?
```
## Solucion
``` shell 
┌──(anitars㉿kali)-[~/hacking/hacking]
└─$ strings vulture.jpg | grep pico
picoCTF{honey.roasted.peanuts}

Realizamos lo mismo que en WebNet0, agregamos la key en wireshark, buscamos el flujo HTTP, encontramos una imagen, la descargamos y la revisamos, a simple vista no hay nada, pero si revisamos los strings de esta, encontraremos la bandera ahí.
 
```
## Referencias
```

```
