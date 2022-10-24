# Nombre del reto
### Wireshark doo dooo
## Objetivo
```
Can you find the flag? [shark1.pcapng](https://mercury.picoctf.net/static/ae5b2bc07928fca272ff3900dc9a6cef/shark1.pcapng).
```
## Solucion
``` shell 
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/Forensic]
└─$ cd wireshark
                                                                           
┌──(anitars㉿kali)-[~/…/hacking/picoCTF/Forensic/wireshark]
└─$ ls
shark1.pcapng
                                                                           
┌──(anitars㉿kali)-[~/…/hacking/picoCTF/Forensic/wireshark]
└─$ wireshark shark1.pcapng 


'picoCTF{p33kab00_1_s33_u_deadbeef}'

Abrimos los paquetes con 'wireshark' seguimos el flujo de un paquete 'TCP' y en el paquete 5 encontramos algo con el formato parecido a la bandera, buscamos y encontramos que es rot13, lo convertimos y obtenemos la bandera.

```
## Referencias
```
https://rot13.com/
```
