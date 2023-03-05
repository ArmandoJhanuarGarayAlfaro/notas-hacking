# PW Crack 1

## Descripcion Reto
Can you crack the password to get the flag?
Download the password checker [here](https://artifacts.picoctf.net/c/51/level1.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/51/level1.flag.txt.enc) in the same directory too.

## Pistas
1. To view the file in the webshell, do: `$ nano level1.py`
2. To exit `nano`, press Ctrl and x and follow the on-screen prompts.
3. The `str_xor` function does not need to be reverse engineered for this challenge.

## Solución
```bash
ajhagaal-picoctf@webshell:~$ mkdir pw1
ajhagaal-picoctf@webshell:~$ cd pw1
ajhagaal-picoctf@webshell:~/pw1$ wget https://artifacts.picoctf.net/c/51/level1.py
--2023-03-05 01:59:37--  https://artifacts.picoctf.net/c/51/level1.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.156.172.74, 108.156.172.6, 108.156.172.120, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.156.172.74|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 876 [application/octet-stream]
Saving to: 'level1.py'

level1.py                   100%[========================================>]     876  --.-KB/s    in 0.001s  

2023-03-05 01:59:37 (841 KB/s) - 'level1.py' saved [876/876]

ajhagaal-picoctf@webshell:~/pw1$ ls
level1.py
ajhagaal-picoctf@webshell:~/pw1$ wget https://artifacts.picoctf.net/c/51/level1.flag.txt.enc
--2023-03-05 01:59:51--  https://artifacts.picoctf.net/c/51/level1.flag.txt.enc
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.156.172.120, 108.156.172.74, 108.156.172.42, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.156.172.120|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 30 [application/octet-stream]
Saving to: 'level1.flag.txt.enc'

level1.flag.txt.enc         100%[========================================>]      30  --.-KB/s    in 0s      

2023-03-05 01:59:51 (121 KB/s) - 'level1.flag.txt.enc' saved [30/30]

ajhagaal-picoctf@webshell:~/pw1$ nano level1.py

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
		
		
		flag_enc = open('level1.flag.txt.enc', 'rb').read()
		
		
		
		def level_1_pw_check():
		    user_pw = input("Please enter correct password for flag: ")
		    if( user_pw == "691d"):
		        print("Welcome back... your flag, user:")
		        decryption = str_xor(flag_enc.decode(), user_pw)
		        print(decryption)
		        return
		    print("That password is incorrect")
		
		
		
		level_1_pw_check()

ajhagaal-picoctf@webshell:~/pw1$ python3 level1.py 
Please enter correct password for flag: 691d
Welcome back... your flag, user:
picoCTF{545h_r1ng1ng_56891419}
```

## Bandera
* picoCTF{545h_r1ng1ng_56891419}

## Notas adicionales
| Comando | Descripcion |
|---------|-------------|
|  |  |

## Referencias
- []()