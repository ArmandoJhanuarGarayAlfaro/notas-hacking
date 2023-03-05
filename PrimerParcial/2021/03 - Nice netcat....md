# Nice netcat...

## Descripcion Reto
There is a nice program that you can talk to by using this command in a shell: $ nc mercury.picoctf.net 22902, but it doesn't speak English...

## Pistas
1. You can practice using netcat with this picoGym problem: [what's a netcat?](https://play.picoctf.org/practice/challenge/34)
2. You can practice reading and writing ASCII with this picoGym problem: Let's Warm Up

## Solución
```bash
ajhagaal-picoctf@webshell:~$ nc mercury.picoctf.net 22902
112 
105 
99 
111 
67 
84 
70 
123 
103 
48 
48 
100 
95 
107 
49 
116 
116 
121 
33 
95 
110 
49 
99 
51 
95 
107 
49 
116 
116 
121 
33 
95 
100 
51 
100 
102 
100 
54 
100 
102 
125 
10
ajhagaal-picoctf@webshell:~$ python3
Python 3.10.6 (main, Aug 10 2022, 11:40:04) [GCC 11.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>>  n = [112, 105, 99, 111, 67, 84, 70, 123, 103, 48, 100, 95, 107, 49, 116, 121, 33, 95, 110, 49, 99, 107, 49, 116, 116, 121, 33, 95, 100, 102, 100, 54, 100, 102, 125, 10]
>>> cadena = ""
>>> for x in n: cadena += chr(x)
... 
>>> print(cadena)
picoCTF{g0d_k1ty!_n1ck1tty!_dfd6df}
```

## Bandera
* picoCTF{g0d_k1ty!_n1ck1tty!_dfd6df}

## Notas adicionales
| Comando | Descripcion |
|---------|-------------|
| chr en python | Convertir a caracteres |

## Referencias
- [Conversor CyberChef](https://gchq.github.io/CyberChef/)