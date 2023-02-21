# Retos Bandit

# Level 14 → Level 15

## Objetivo
The password for the next level can be retrieved by submitting the password of the current level to **port 30000 on localhost**.

## Datos de acceso al nivel
- **Usuario:** bandit14
- **Contraseña:** fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq

## Solución
```bash
bandit14@bandit:~$
bandit14@bandit:~$ nc localhost 30000
fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq
Correct!
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
^C
bandit14@bandit:~$
```
## Notas adicionales
| Comando | Descripcion |
|---------|-------------|
| ping -c3 | Para ver la direccion ip de un DNS como www.uaz.edu.mx |

## Referencias
- []()