# Nombre del reto
### Wireshark twoo twooo...
## Objetivo
```
Can you find the flag? [shark2.pcapng](https://mercury.picoctf.net/static/719e81d6fbb6b3157624268588fc0de8/shark2.pcapng).

HINT1: Did you really find _the_ flag?
HINT2: Look for traffic that seems suspicious.
```
## Solucion
``` shell 
dns && ip.dst==18.217.1.57&&dns.qry.name contains local

cat bandera.csv | cut -d "," -f 7 | cut -d " " -f 5 | cut -d "." -f1 | base64 -d


┌──(anitars㉿kali)-[~/…/hacking/picoCTF/Forensic/wireshark_twoo]
└─$ cat data.csv 
"No.","Time","Source","Destination","Protocol","Length","Info"
"1637","9.440363","192.168.38.104","18.217.1.57","DNS","109","Standard query 0x1dd2 A cGljb0NU.reddshrimpandherring.com.windomain.local"
"2046","11.972605","192.168.38.104","18.217.1.57","DNS","109","Standard query 0xabb9 A RntkbnNf.reddshrimpandherring.com.windomain.local"
"2448","14.605726","192.168.38.104","18.217.1.57","DNS","109","Standard query 0x9e21 A M3hmMWxf.reddshrimpandherring.com.windomain.local"
"3153","16.506492","192.168.38.104","18.217.1.57","DNS","109","Standard query 0x2ee1 A ZnR3X2Rl.reddshrimpandherring.com.windomain.local"
"3442","18.340155","192.168.38.104","18.217.1.57","DNS","109","Standard query 0x2a4b A YWRiZWVm.reddshrimpandherring.com.windomain.local"
"3982","20.369626","192.168.38.104","18.217.1.57","DNS","105","Standard query 0x4068 A fQ==.reddshrimpandherring.com.windomain.local"
"4374","22.583745","192.168.38.104","18.217.1.57","DNS","105","Standard query 0x7418 A fQ==.reddshrimpandherring.com.windomain.local"
                                                                          
┌──(anitars㉿kali)-[~/…/hacking/picoCTF/Forensic/wireshark_twoo]
└─$ cat data.csv | cut -d "," -f 7 | cut -d " " -f 5 | cut -d "." -f1 | base64 -d   
base64: entrada inválida
                                                                          
┌──(anitars㉿kali)-[~/…/hacking/picoCTF/Forensic/wireshark_twoo]
└─$ cat data.csv | cut -d " " -f 5
"No.","Time","Source","Destination","Protocol","Length","Info"
cGljb0NU.reddshrimpandherring.com.windomain.local"
RntkbnNf.reddshrimpandherring.com.windomain.local"
M3hmMWxf.reddshrimpandherring.com.windomain.local"
ZnR3X2Rl.reddshrimpandherring.com.windomain.local"
YWRiZWVm.reddshrimpandherring.com.windomain.local"
fQ==.reddshrimpandherring.com.windomain.local"
fQ==.reddshrimpandherring.com.windomain.local"
                                                                          
┌──(anitars㉿kali)-[~/…/hacking/picoCTF/Forensic/wireshark_twoo]
└─$ nano data.csv 
                                                                          
┌──(anitars㉿kali)-[~/…/hacking/picoCTF/Forensic/wireshark_twoo]
└─$ cat data.csv | cut -d " " -f 5
cGljb0NU.reddshrimpandherring.com.windomain.local"
RntkbnNf.reddshrimpandherring.com.windomain.local"
M3hmMWxf.reddshrimpandherring.com.windomain.local"
ZnR3X2Rl.reddshrimpandherring.com.windomain.local"
YWRiZWVm.reddshrimpandherring.com.windomain.local"

                                                                          
┌──(anitars㉿kali)-[~/…/hacking/picoCTF/Forensic/wireshark_twoo]
└─$ cat data.csv | cut -d "," -f 7 | cut -d " " -f 5 | cut -d "." -f1 | base64 -d
picoCTF{dns_3xf1l_ftw_deadbeef                                                                          
┌──(anitars㉿kali)-[~/…/hacking/picoCTF/Forensic/wireshark_twoo]
└─$ nano data.csv                 
                                                                          
                                  
┌──(anitars㉿kali)-[~/…/hacking/picoCTF/Forensic/wireshark_twoo]
└─$ wireshark shark2.pcapng
^[[A

^Z
zsh: suspended  wireshark shark2.pcapng
                                                                          
┌──(anitars㉿kali)-[~/…/hacking/picoCTF/Forensic/wireshark_twoo]
└─$ nano data.csv          
                                                                          
┌──(anitars㉿kali)-[~/…/hacking/picoCTF/Forensic/wireshark_twoo]
└─$ wireshark shark2.pcapng
^Z
zsh: suspended  wireshark shark2.pcapng
                                                                          
┌──(anitars㉿kali)-[~/…/hacking/picoCTF/Forensic/wireshark_twoo]
└─$ nano data.csv          
                                                                          
┌──(anitars㉿kali)-[~/…/hacking/picoCTF/Forensic/wireshark_twoo]
└─$ 
[1]  + killed     wireshark shark2.pcapng
┌──(anitars㉿kali)-[~/…/hacking/picoCTF/Forensic/wireshark_twoo]
└─$ wireshark shark2.pcapng
 ** (wireshark:52483) 22:03:01.488944 [GUI WARNING] -- QXcbConnection: XCB error: 3 (BadWindow), sequence: 2927, resource id: 22366307, major code: 40 (TranslateCoords), minor code: 0
^Z
zsh: suspended  wireshark shark2.pcapng
                                                                          
┌──(anitars㉿kali)-[~/…/hacking/picoCTF/Forensic/wireshark_twoo]
└─$ nano data1.csv 
                                                                          
┌──(anitars㉿kali)-[~/…/hacking/picoCTF/Forensic/wireshark_twoo]
└─$ cat data1.csv | cut -d "," -f 7 | cut -d " " -f 5 | cut -d "." -f1 | base64 -d  
picoCTF{dns_3xf1l_ftw_deadbeef}                                                                          
┌──(anitars㉿kali)-[~/…/hacking/picoCTF/Forensic/wireshark_twoo]
└─$ 

```
## Referencias
```

```
