# Nombre del reto
### Vault 5	
## Objetivo
```
In the last challenge, you mastered octal (base 8), decimal (base 10), and hexadecimal (base 16) numbers, but this vault door uses a different change of base as well as URL encoding! The source code for this vault is here: [VaultDoor5.java](https://jupiter.challenges.picoctf.org/static/d31ce4356bdfd15d33a9af7e35ab4d0a/VaultDoor5.java)

HINT1: You may find an encoder/decoder tool helpful, such as https://encoding.tools/
HINT2: Read the wikipedia articles on URL encoding and base 64 encoding to understand how they work and what the results look like.
```
## Solucion
``` shell 
Pasamos el texto que sacamos del codigo que descargamos a cyberChef y este aplicara un base64 y despues un 'URL decode' y asi encontraremos la bandera.

Flag: 'picoCTF{c0nv3rt1ng_fr0m_ba5e_64_e3152bf4}'
```
## Referencias
```
https://gchq.github.io/CyberChef/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)URL_Decode()&input=SlRZekpUTXdKVFpsSlRjMkpUTXpKVGN5SlRjMEpUTXhKVFpsSlRZM0pUVm1KVFkySlRjeUpUTXdKVFprSlRWbUpUWXlKVFl4SlRNMUpUWTFKVFZtSlRNMkpUTTBKVFZtSlRZMUpUTXpKVE14SlRNMUpUTXlKVFl5SlRZMkpUTTA
```
