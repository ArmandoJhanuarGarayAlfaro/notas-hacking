# plumbing

## Descripcion Reto
Sometimes you need to handle process data outside of a file. Can you find a way to keep the output from this program and search for the flag? Connect to `jupiter.challenges.picoctf.org 7480`.

## Pistas
1. Remember the flag format is picoCTF{XXXX}
2. What's a pipe? No not that kind of pipe... This [kind](http://www.linfo.org/pipes.html)

## Solución
```bash
ajhagaal-picoctf@webshell:~$ nc jupiter.challenges.picoctf.org 7480
I don't think this is a flag either
This is defintely not a flag
Not a flag either
Again, I really don't think this is a flag
This is defintely not a flag
Not a flag either
Not a flag either
Not a flag either
This is defintely not a flag
Again, I really don't think this is a flag
This is defintely not a flag
This is defintely not a flag
Not a flag either
Again, I really don't think this is a flag
Again, I really don't think this is a flag
Not a flag either
Again, I really don't think this is a flag
Not a flag either
This is defintely not a flag
Not a flag either
ajhagaal-picoctf@webshell:~$ ^C
ajhagaal-picoctf@webshell:~$ nc jupiter.challenges.picoctf.org 7480 | grep picoCTF 
picoCTF{digital_plumb3r_06e9d954}
```

## Bandera
* picoCTF{digital_plumb3r_06e9d954}

## Notas adicionales
| Comando | Descripcion |
|---------|-------------|
|  |  |

## Referencias
- []()