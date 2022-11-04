# Nombre del reto
### Vault 6	
## Objetivo
```
This vault uses an XOR encryption scheme. The source code for this vault is here: [VaultDoor6.java](https://jupiter.challenges.picoctf.org/static/937a166e2c8c5bf34928a2dab22e8ade/VaultDoor6.java)

HINT: If X ^ Y = Z, then Z ^ Y = X. Write a program that decrypts the flag based on this fact.
```
## Solucion
``` shell 
┌──(anitars㉿kali)-[~]
└─$ python3                     
Python 3.10.7 (main, Sep  8 2022, 14:34:29) [GCC 12.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> mybytes = [0x3b, 0x65, 0x21, 0xa , 0x38, 0x0 , 0x36, 0x1d,
...             0xa , 0x3d, 0x61, 0x27, 0x11, 0x66, 0x27, 0xa ,
...             0x21, 0x1d, 0x61, 0x3b, 0xa , 0x2d, 0x65, 0x27,
...             0xa , 0x6c, 0x61, 0x6d, 0x37, 0x6d, 0x6d, 0x6d]
>>> mybytes
[59, 101, 33, 10, 56, 0, 54, 29, 10, 61, 97, 39, 17, 102, 39, 10, 33, 29, 97, 59, 10, 45, 101, 39, 10, 108, 97, 109, 55, 109, 109, 109]
>>> cad = [ i^0x55 for i in mybytes ]
>>> cad
[110, 48, 116, 95, 109, 85, 99, 72, 95, 104, 52, 114, 68, 51, 114, 95, 116, 72, 52, 110, 95, 120, 48, 114, 95, 57, 52, 56, 98, 56, 56, 56]
>>> flag = [ chr(i) for i in cad]
>>> flag
['n', '0', 't', '_', 'm', 'U', 'c', 'H', '_', 'h', '4', 'r', 'D', '3', 'r', '_', 't', 'H', '4', 'n', '_', 'x', '0', 'r', '_', '9', '4', '8', 'b', '8', '8', '8']
>>> ''.join(flag)
'n0t_mUcH_h4rD3r_tH4n_x0r_948b888'
>
>Flag: picoCTF{n0t_mUcH_h4rD3r_tH4n_x0r_948b888}


Aplicamos un XOR 0x55 a cada byte que nos da el codigo y luego lo convertimos a caracter y aplicamos un 'join' para juntar todo y encontrar la bandera.
```
## Referencias
```

```
