# Safe Opener 2

## Descripcion Reto
What can you do with this file? I forgot the key to my safe but this [file](https://artifacts.picoctf.net/c/288/SafeOpener.class) is supposed to help me with retrieving the lost key. Can you help me unlock my safe?

## Pistas
1. Download and try to decompile the file.

## Solución
```bash
┌──(kali㉿kali)-[~/hacking/picoCTF_Reversing/safe_o2]
└─$ wget 'https://artifacts.picoctf.net/c/288/SafeOpener.class'
--2023-05-09 22:38:13--  https://artifacts.picoctf.net/c/288/SafeOpener.class
Resolviendo artifacts.picoctf.net (artifacts.picoctf.net)... 18.154.132.108, 18.154.132.74, 18.154.132.32, ...
Conectando con artifacts.picoctf.net (artifacts.picoctf.net)[18.154.132.108]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 2036 (2.0K) [application/octet-stream]
Grabando a: «SafeOpener.class»

SafeOpener.class     100%[=====================>]   1.99K  --.-KB/s    en 0s      

2023-05-09 22:38:19 (92.9 MB/s) - «SafeOpener.class» guardado [2036/2036]


┌──(kali㉿kali)-[~/hacking/picoCTF_Reversing/safe_o2]
└─$ strings SafeOpener.class | grep pico
,picoCTF{SAf3_0p3n3rr_y0u_solv3d_it_5bfbd6f1}
```

Usamos un [decompilador](http://www.javadecompilers.com/) de Java para obtener la bandera del codigo .class

```bash
┌──(kali㉿kali)-[~/hacking/picoCTF_Reversing/safe_o2]
└─$ cd SafeOpener.class_source_from_Procyon 
                                                                                   
┌──(kali㉿kali)-[~/hacking/picoCTF_Reversing/safe_o2/SafeOpener.class_source_from_Procyon]
└─$ ls
SafeOpener.java
                                                                                   
┌──(kali㉿kali)-[~/hacking/picoCTF_Reversing/safe_o2/SafeOpener.class_source_from_Procyon]
└─$ cat SafeOpener.java                     
import java.io.IOException;
import java.util.Base64;
import java.io.Reader;
import java.io.BufferedReader;
import java.io.InputStreamReader;

// 
// Decompiled by Procyon v0.5.36
// 

public class SafeOpener
{
    public static void main(final String[] args) throws IOException {
        final BufferedReader keyboard = new BufferedReader(new InputStreamReader(System.in));
        final Base64.Encoder encoder = Base64.getEncoder();
        String encodedkey = "";
        String key = "";
        for (int i = 0; i < 3; ++i) {
            System.out.print("Enter password for the safe: ");
            key = keyboard.readLine();
            encodedkey = encoder.encodeToString(key.getBytes());
            System.out.println(encodedkey);
            final boolean isOpen = openSafe(encodedkey);
            if (isOpen) {
                break;
            }
            System.out.println("You have  " + (2 - i) + " attempt(s) left");
        }
    }
    
    public static boolean openSafe(final String password) {
        final String encodedkey = "picoCTF{SAf3_0p3n3rr_y0u_solv3d_it_5bfbd6f1}";
        if (password.equals(encodedkey)) {
            System.out.println("Sesame open");
            return true;
        }
        System.out.println("Password is incorrect\n");
        return false;
    }
}

┌──(kali㉿kali)-[~/hacking/picoCTF_Reversing/safe_o2/SafeOpener.class_source_from_Procyon]
└─$ cat SafeOpener.java | grep pico
        final String encodedkey = "picoCTF{SAf3_0p3n3rr_y0u_solv3d_it_5bfbd6f1}";
```

## Bandera
* picoCTF{SAf3_0p3n3rr_y0u_solv3d_it_5bfbd6f1}

## Notas adicionales
| Comando | Descripcion |
|---------|-------------|
|  |  |

## Referencias
- []()