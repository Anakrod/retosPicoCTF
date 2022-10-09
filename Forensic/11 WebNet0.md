# Nombre del reto
### WebNet0
## Objetivo
```
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/capture.pcap) and [key](https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/picopico.key). Recover the flag.

HINT1: Try using a tool like Wireshark.
HINT2: How can you decrypt the TLS stream?
```
## Solucion
``` shell 
picoCTF{nongshim.shrimp.crackers}

┌──(anitars㉿kali)-[~/hacking/hacking]
└─$ file capture.pcap.1
capture.pcap.1: pcap capture file, microsecond ts (little-endian) - version 2.4 (Ethernet, capture length 65535)
                                                                           
┌──(anitars㉿kali)-[~/hacking/hacking]
└─$ wireshark capture.pcap.1
ICE default IO error handler doing an exit(), pid = 28109, errno = 32
                                                                           
┌──(anitars㉿kali)-[~/hacking/hacking]
└─$ wireshark capture.pcap.1
 ** (wireshark:28456) 22:52:35.791648 [GUI WARNING] -- FIX Add drag reordering to UAT dialog
 ** (wireshark:28456) 23:04:00.800258 [GUI WARNING] -- FIX Add drag reordering to UAT dialog


Hacemos usos de wireshark para poder encontrar la llave.
```
## Referencias
```

```
