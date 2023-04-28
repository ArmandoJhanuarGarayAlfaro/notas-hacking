# Mind your Ps and Qs

## Descripcion Reto
In RSA, a small `e` value can be problematic, but what about `N`? Can you decrypt this? [values](https://mercury.picoctf.net/static/38f30029ab93478310e906d3d084a4c1/values)

## Pistas
1. Bits are expensive, I used only a little bit over 100 to save money

## Solución
```bash
┌──(kali㉿kali)-[~/hacking/Mind]
└─$ wget https://mercury.picoctf.net/static/38f30029ab93478310e906d3d084a4c1/values               
--2023-04-26 20:45:36--  https://mercury.picoctf.net/static/38f30029ab93478310e906d3d084a4c1/values
Resolviendo mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Conectando con mercury.picoctf.net (mercury.picoctf.net)[18.189.209.142]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 205 [application/octet-stream]
Grabando a: «values»

values               100%[====================>]     205  --.-KB/s    en 0s      

2023-04-26 20:45:41 (74.1 MB/s) - «values» guardado [205/205]

┌──(kali㉿kali)-[~/hacking/Mind]
└─$ ls            
values
                                                                                  
┌──(kali㉿kali)-[~/hacking/Mind]
└─$ cat values    
Decrypt my super sick RSA:
c: 240986837130071017759137533082982207147971245672412893755780400885108149004760496
n: 831416828080417866340504968188990032810316193533653516022175784399720141076262857
e: 65537
```

Se obtiene **p** y **q** en la página [factordb](http://factordb.com/index.php?query=831416828080417866340504968188990032810316193533653516022175784399720141076262857) donde se uso **n** para obtener los valores

![Pasted image 20230426214855.png](https://github.com/ArmandoJhanuarGarayAlfaro/notas-hacking/blob/main/Crypto/img/Pasted%20image%2020230426214855.png)

```bash
┌──(kali㉿kali)-[~/hacking/Mind]
└─$ python3 
```
```python
>>> from Crypto.Util.number import long_to_bytes
>>> from Crypto.Util.number import inverse
>>> p = 1593021310640923782355996681284584012117
>>> q = 521911930824021492581321351826927897005221
>>> e = 65537
>>> n = 831416828080417866340504968188990032810316193533653516022175784399720141076262857
>>> c = 240986837130071017759137533082982207147971245672412893755780400885108149004760496
>>> tn = (p-1) * (q-1)
>>> d = inverse(e, tn)
>>> m = pow(c,d,n)
>>> >>> m
13016382529449106065927291425342535437996222135352905256639592405461024281868413
>>> long_to_bytes(m)
b'picoCTF{sma11_N_n0_g0od_23540368}'
```

## Bandera
* picoCTF{sma11_N_n0_g0od_23540368}

## Notas adicionales
| Comando | Descripcion |
|---------|-------------|
|  |  |


| Variable | Descripcion |
|---------|-------------|
| c | texto cifrado |
| m | mensaje texto plano |
| p | primo 1 |
| q | primo 2 |
| n | modulo |
| tn | totient n (euler) |
| e | exponente (llave publica) 2^16+1 = 65537 |

n = p \* q
tn = (p-1) \* (q-1)
d = e mod   inv   tn   /   inverse(e,tn)

|  |  |
|---------|-------------|
| Encriptar | c = m^e mod n   \|   pow(m,e,n) |
| Desencriptar | m = c^d mod n   \|   pow(c,d,n) |


## Referencias
- []()
