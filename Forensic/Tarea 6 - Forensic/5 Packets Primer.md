# Nombre del reto
	
## Objetivo
```
Download the packet capture file and use packet analysis software to find the flag.

-   [Download packet capture](https://artifacts.picoctf.net/c/201/network-dump.flag.pcap)

HINT: Wireshark, if you can install and use it, is probably the most beginner friendly packet analysis software product.
```
## Solucion
``` shell 
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/Forensic]
└─$ mkdir packets 
                                                                           
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/Forensic]
└─$ cd packets 
                                                                           
┌──(anitars㉿kali)-[~/…/hacking/picoCTF/Forensic/packets]
└─$ wget https://artifacts.picoctf.net/c/201/network-dump.flag.pcap
--2022-10-23 19:52:34--  https://artifacts.picoctf.net/c/201/network-dump.flag.pcap
Resolviendo artifacts.picoctf.net (artifacts.picoctf.net)... 54.230.202.68, 54.230.202.24, 54.230.202.94, ...
Conectando con artifacts.picoctf.net (artifacts.picoctf.net)[54.230.202.68]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 778 [application/octet-stream]
Grabando a: «network-dump.flag.pcap»

network-dump.flag. 100%[===============>]     778  --.-KB/s    en 0.009s  

2022-10-23 19:52:35 (81.2 KB/s) - «network-dump.flag.pcap» guardado [778/778]

                                                                           
┌──(anitars㉿kali)-[~/…/hacking/picoCTF/Forensic/packets]
└─$ wireshark network-dump.flag.pcap                               

Abrimos la captura de paquetes con wireshark, seguimos un paquete 'TCP' y lo primero que nos dara sera la bandera.
```
## Referencias
```

```
