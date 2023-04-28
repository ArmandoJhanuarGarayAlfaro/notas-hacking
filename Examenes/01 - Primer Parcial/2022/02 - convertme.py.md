# convertme.py

## Descripcion Reto
Run the Python script and convert the given number from decimal to binary to get the flag.
[Download Python script](https://artifacts.picoctf.net/c/30/convertme.py)

## Pistas
1. Look up a decimal to binary number conversion app on the web or use your computer's calculator!
2. The `str_xor` function does not need to be reverse engineered for this challenge.
3. If you have Python on your computer, you can download the script normally and run it. Otherwise, use the `wget` command in the webshell.
4. To use `wget` in the webshell, first right click on the download link and select 'Copy Link' or 'Copy Link Address'
5. Type everything after the dollar sign in the webshell: `$ wget` , then paste the link after the space after `wget` and press enter. This will download the script for you in the webshell so you can run it!
6. Finally, to run the script, type everything after the dollar sign and then press enter: `$ python3 convertme.py`

## Solución
```bash
ajhagaal-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/30/convertme.py
--2023-03-05 01:29:35--  https://artifacts.picoctf.net/c/30/convertme.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.156.172.42, 108.156.172.120, 108.156.172.6, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.156.172.42|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1189 (1.2K) [application/octet-stream]
Saving to: 'convertme.py'

convertme.py                100%[========================================>]   1.16K  --.-KB/s    in 0s      

2023-03-05 01:29:35 (927 MB/s) - 'convertme.py' saved [1189/1189]

ajhagaal-picoctf@webshell:~$ ls
Addadshashanammu      README.txt    decode  flag      netcat    static
Addadshashanammu.zip  convertme.py  file    ltdis.sh  runme.py  warm
ajhagaal-picoctf@webshell:~$ python3 convertme.py 
If 42 is in decimal base, what is it in binary base?
Answer: ^CTraceback (most recent call last):
  File "/home/ajhagaal-picoctf/convertme.py", line 23, in <module>
    ans = input('Answer: ')
KeyboardInterrupt

ajhagaal-picoctf@webshell:~$ python3
Python 3.10.6 (main, Aug 10 2022, 11:40:04) [GCC 11.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> bin(42)
'0b101010'
>>> 
ajhagaal-picoctf@webshell:~$ python3 convertme.py 
If 25 is in decimal base, what is it in binary base?
Answer: 11001
That is correct! Here's your flag: picoCTF{4ll_y0ur_b4535_762f748e}
ajhagaal-picoctf@webshell:~$ 
```

## Bandera
* picoCTF{4ll_y0ur_b4535_762f748e}

## Notas adicionales
| Comando | Descripcion |
|---------|-------------|
| bin() | En python convierte el valor decimal a binario |

## Referencias
- [Conversor de decimal a binario](https://www.rapidtables.org/convert/number/decimal-to-binary.html)