# vault-door-training

## Descripcion Reto
Your mission is to enter Dr. Evil's laboratory and retrieve the blueprints for his Doomsday Project. The laboratory is protected by a series of locked vault doors. Each door is controlled by a computer and requires a password to open. Unfortunately, our undercover agents have not been able to obtain the secret passwords for the vault doors, but one of our junior agents obtained the source code for each vault's computer! You will need to read the source code for each level to figure out what the password is for that vault door. As a warmup, we have created a replica vault in our training facility. The source code for the training vault is here: [VaultDoorTraining.java](https://jupiter.challenges.picoctf.org/static/1afdf83322ee9c0040f8e3a3c047e18b/VaultDoorTraining.java)

## Pistas
1. The password is revealed in the program's source code.

## Solución
```bash
┌──(kali㉿kali)-[~/hacking/vault_training]
└─$ wget 'https://jupiter.challenges.picoctf.org/static/1afdf83322ee9c0040f8e3a3c047e18b/VaultDoorTraining.java'
--2023-05-01 12:03:19--  https://jupiter.challenges.picoctf.org/static/1afdf83322ee9c0040f8e3a3c047e18b/VaultDoorTraining.java
Resolviendo jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Conectando con jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)[3.131.60.8]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 943 [application/octet-stream]
Grabando a: «VaultDoorTraining.java»

VaultDoorTraining.ja 100%[====================>]     943  --.-KB/s    en 0.004s  

2023-05-01 12:03:25 (248 KB/s) - «VaultDoorTraining.java» guardado [943/943]

                                                                                  
┌──(kali㉿kali)-[~/hacking/vault_training]
└─$ cat VaultDoorTraining.java 
import java.util.*;

class VaultDoorTraining {
    public static void main(String args[]) {
        VaultDoorTraining vaultDoor = new VaultDoorTraining();
        Scanner scanner = new Scanner(System.in); 
        System.out.print("Enter vault password: ");
        String userInput = scanner.next();
        String input = userInput.substring("picoCTF{".length(),userInput.length()-1);
        if (vaultDoor.checkPassword(input)) {
            System.out.println("Access granted.");
        } else {
            System.out.println("Access denied!");
        }
   }

    // The password is below. Is it safe to put the password in the source code?
    // What if somebody stole our source code? Then they would know what our
    // password is. Hmm... I will think of some ways to improve the security
    // on the other doors.
    //
    // -Minion #9567
    public boolean checkPassword(String password) {
        return password.equals("w4rm1ng_Up_w1tH_jAv4_eec0716b713");
    }
}

┌──(kali㉿kali)-[~/hacking/vault_training]
└─$ java --version
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true
openjdk 17.0.6 2023-01-17
OpenJDK Runtime Environment (build 17.0.6+10-Debian-1)
OpenJDK 64-Bit Server VM (build 17.0.6+10-Debian-1, mixed mode, sharing)
                                                                                  
┌──(kali㉿kali)-[~/hacking/vault_training]
└─$ javac --version
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true
javac 17.0.6

┌──(kali㉿kali)-[~/hacking/vault_training]
└─$ ls -laa
total 8
drwxrwx--- 1 root vboxsf    0 may  1 12:03 .
drwxrwx--- 1 root vboxsf 4096 may  1 12:02 ..
-rwxrwx--- 1 root vboxsf  943 oct 26  2020 VaultDoorTraining.java
                                                                                   
┌──(kali㉿kali)-[~/hacking/vault_training]
└─$ javac VaultDoorTraining.java 
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true
                                                                                   
┌──(kali㉿kali)-[~/hacking/vault_training]
└─$ ls -la 
total 12
drwxrwx--- 1 root vboxsf    0 may  1 12:05 .
drwxrwx--- 1 root vboxsf 4096 may  1 12:02 ..
-rwxrwx--- 1 root vboxsf 1106 may  1 12:05 VaultDoorTraining.class
-rwxrwx--- 1 root vboxsf  943 oct 26  2020 VaultDoorTraining.java

┌──(kali㉿kali)-[~/hacking/vault_training]
└─$ java VaultDoorTraining      
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true
Enter vault password: picoCTF{qjifpasmfsa}
Access denied!

┌──(kali㉿kali)-[~/hacking/vault_training]
└─$ javac VaultDoorTraining.java
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true
```

Se toma la llave que da el codigo .java que se proporciona ya que en 
el código da la contraseña

![Pasted image 20230501131018.png](https://github.com/ArmandoJhanuarGarayAlfaro/notas-hacking/blob/main/retos/05%20-%20Reversing/img/Pasted%20image%2020230501131018.png)

```bash
┌──(kali㉿kali)-[~/hacking/vault_training]
└─$ java VaultDoorTraining      
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true
Enter vault password: picoCTF{w4rm1ng_Up_w1tH_jAv4_eec0716b713}
Access granted.
```

## Bandera
* picoCTF{w4rm1ng_Up_w1tH_jAv4_eec0716b713}

## Notas adicionales
| Comando | Descripcion |
|---------|-------------|
|  |  |

## Referencias
- []()
