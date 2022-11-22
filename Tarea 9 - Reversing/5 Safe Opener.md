# Nombre del reto
### Safe Opener	
## Objetivo
```
Can you open this safe? I forgot the key to my safe but this [program](https://artifacts.picoctf.net/c/463/SafeOpener.java) is supposed to help me with retrieving the lost key. Can you help me unlock my safe? Put the password you recover into the picoCTF flag format like: `picoCTF{password}`
```
## Solucion
``` shell 
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/reversing_tarea]
└─$ wget https://artifacts.picoctf.net/c/463/SafeOpener.java
--2022-11-20 22:12:09--  https://artifacts.picoctf.net/c/463/SafeOpener.java
Resolviendo artifacts.picoctf.net (artifacts.picoctf.net)... 54.230.225.100, 54.230.225.122, 54.230.225.11, ...
Conectando con artifacts.picoctf.net (artifacts.picoctf.net)[54.230.225.100]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 1258 (1.2K) [application/octet-stream]
Grabando a: «SafeOpener.java»

SafeOpener.java    100%[==============>]   1.23K  --.-KB/s    en 0.001s  

2022-11-20 22:12:09 (1.96 MB/s) - «SafeOpener.java» guardado [1258/1258]

                                                                          
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/reversing_tarea]
└─$ cat SafeOpener.java 
import java.io.*;
import java.util.*;  
public class SafeOpener {
    public static void main(String args[]) throws IOException {
        BufferedReader keyboard = new BufferedReader(new InputStreamReader(System.in));
        Base64.Encoder encoder = Base64.getEncoder();
        String encodedkey = "";
        String key = "";
        int i = 0;
        boolean isOpen;
        

        while (i < 3) {
            System.out.print("Enter password for the safe: ");
            key = keyboard.readLine();

            encodedkey = encoder.encodeToString(key.getBytes());
            System.out.println(encodedkey);
              
            isOpen = openSafe(encodedkey);
            if (!isOpen) {
                System.out.println("You have  " + (2 - i) + " attempt(s) left");
                i++;
                continue;
            }
            break;
        }
    }
    
    public static boolean openSafe(String password) {
        String encodedkey = "cGwzYXMzX2wzdF9tM18xbnQwX3RoM19zYWYz";
        
        if (password.equals(encodedkey)) {
            System.out.println("Sesame open");
            return true;
        }
        else {
            System.out.println("Password is incorrect\n");
            return false;
        }
    }
}                                                                          

┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/reversing_tarea]
└─$ java SafeOpener
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true
Enter password for the safe: pl3as3_l3t_m3_1nt0_th3_saf3
cGwzYXMzX2wzdF9tM18xbnQwX3RoM19zYWYz
Sesame open
                                                                          
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/reversing_tarea]
└─$ 


Descargamos el programa que nos da, revisamos su contenido y vemos que valida una contraseña que esta en base64, la decodificamos y es la bandera, corremos el programa, ponemos la bandera y confirmamos que si sea.

FLAG: 'picoCTF{pl3as3_l3t_m3_1nt0_th3_saf3}'
```
## Referencias
```

```
