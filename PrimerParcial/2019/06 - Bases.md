#chef
# Bases

## Descripcion Reto
What does this `bDNhcm5fdGgzX3IwcDM1` mean? I think it has something to do with bases.

## Pistas
* Submit your answer in our flag format. For example, if your answer was 'hello', you would submit 'picoCTF{hello}' as the flag.

## Solución
```bash
ajhagaal-picoctf@webshell:~$ echo -ne 'bDNhcm5fdGgzX3IwcDM1' \n | base64 --decode
l3arn_th3_r0p35base64: invalid input
ajhagaal-picoctf@webshell:~$ 
```
```python
ajhagaal-picoctf@webshell:~$ python3
Python 3.10.6 (main, Aug 10 2022, 11:40:04) [GCC 11.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> import base64
>>> base64.b64decode('bDNhcm5fdGgzX3IwcDM1').decode('utf-8')
'l3arn_th3_r0p35'
>>> 
```

## Bandera
* picoCTF{l3arn_th3_r0p35}

## Notas adicionales
| Comando | Descripcion |
|---------|-------------|
| base64 --decode | Decodifica string de base64 a un string normal |

## Referencias
- [CyberChef](https://gchq.github.io/CyberChef/)
- [Convertir un base64 a string en python](https://stackoverflow.com/questions/13262125/how-to-convert-from-base64-to-string-python-3-2)
- [Convertir un base64 a string en comando de Linux](https://www.serverlab.ca/tutorials/linux/administration-linux/how-to-base64-encode-and-decode-from-command-line/)