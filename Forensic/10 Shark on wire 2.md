# Nombre del reto
### Shark on wire 2
## Objetivo
```
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/b506393b6f9d53b94011df000c534759/capture.pcap). Recover the flag that was pilfered from the network.
```
## Solucion
``` shell
**Codigo en python para recorrer los paquetes y encontrar la bandera**


from scapy.all import *

packets = rdpcap("capture.pcap")
flag = ''

for p in packets:
        if UDP in p and p[UDP].dport == 22:
                if p[UDP].sport > 5000:
                        flag +=chr(p[UDP].sport - 5000)
print(flag)

┌──(anitars㉿kali)-[~/hacking/hacking]
└─$ python3 sac.py
picoCTF{p1LLf3r3d_data_v1a_st3g0}
                                                                           
┌──(anitars㉿kali)-[~/hacking/hacking]
└─$ 

Utilizamos wireshark para revisar paquetes y despues hacemos un codigo (incado arriba) para recorrer los paquetes del puerto 22 y poder encontrar la bandera.

```
## Referencias
```

```
