# Nombre Reto

## Descripcion Reto
Can you crack the password to get the flag?
Download the password checker [here](https://artifacts.picoctf.net/c/17/level2.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/17/level2.flag.txt.enc) in the same directory too.

## Pistas
1. Does that encoding look familiar?
2. The `str_xor` function does not need to be reverse engineered for this challenge.

## Solución
```bash
ajhagaal-picoctf@webshell:~$ ls
Addadshashanammu      README.txt  convertme.py  file       fixme2.py  ltdis.sh  pw1  runme.py  warm
Addadshashanammu.zip  codebook    decode        fixme1.py  flag       netcat    pw2  static
ajhagaal-picoctf@webshell:~$ cd pw2
ajhagaal-picoctf@webshell:~/pw2$ ls
level2.flag.txt.enc  level2.py
ajhagaal-picoctf@webshell:~/pw2$ nano level2.py

		  GNU nano 6.2                                      level2.py                                                
		### THIS FUNCTION WILL NOT HELP YOU FIND THE FLAG --LT ########################
		def str_xor(secret, key):
		    #extend key to secret length
		    new_key = key
		    i = 0
		    while len(new_key) < len(secret):
		        new_key = new_key + key[i]
		        i = (i + 1) % len(key)        
		    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])
		###############################################################################
		
		flag_enc = open('level2.flag.txt.enc', 'rb').read()
		
		
		
		def level_2_pw_check():
		    user_pw = input("Please enter correct password for flag: ")
		    if( user_pw == chr(0x34) + chr(0x65) + chr(0x63) + chr(0x39) ):
		        print("Welcome back... your flag, user:")
		        decryption = str_xor(flag_enc.decode(), user_pw)
		        print(decryption)
		        return
		    print("That password is incorrect")
		
		
		
		level_2_pw_check()

ajhagaal-picoctf@webshell:~/pw2$ python3
Python 3.10.6 (main, Aug 10 2022, 11:40:04) [GCC 11.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> pwd = chr(0x34) + chr(0x65) + chr(0x63) + chr(0x39)
>>> print(pwd)
4ec9
>>> 
ajhagaal-picoctf@webshell:~/pw2$ python3 level2.py 
Please enter correct password for flag: 4ec9
Welcome back... your flag, user:
picoCTF{tr45h_51ng1ng_9701e681}
ajhagaal-picoctf@webshell:~/pw2$ 
```

## Bandera
* picoCTF{tr45h_51ng1ng_9701e681}

## Notas adicionales
| Comando | Descripcion |
|---------|-------------|
|  |  |

## Referencias
- []()