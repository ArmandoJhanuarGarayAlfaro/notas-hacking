# Retos Bandit

# Level 20 → Level 21

## Objetivo
There is a setuid binary in the homedirectory that does the following: it makes a connection to localhost on the port you specify as a commandline argument. It then reads a line of text from the connection and compares it to the password in the previous level (bandit20). If the password is correct, it will transmit the password for the next level (bandit21).

## Datos de acceso al nivel
- **Usuario:** bandit20
- **Contraseña:** VxCazJaVykI6W36BkBU0mJTCM8rR95XT

## Solución
```bash
bandit20@bandit:~$ nc -lnvp 2020 <<< VxCazJaVykI6W36BkBU0mJTCM8rR95XT &
[1] 3444802
bandit20@bandit:~$ Listening on 0.0.0.0 2020
bandit20@bandit:~$ ./suconnect 2020
Connection received on 127.0.0.1 48964
Read: VxCazJaVykI6W36BkBU0mJTCM8rR95XT
Password matches, sending next password
NvEJF7oVjkddltPSrdKEFOllh9V1IBcq
[1]+ Done nc -lnvp 2020 <<< VxCazJaVykI6W36BkBU0mJTCM8rR95XT
bandit20@bandit:~$ exit
```
## Notas adicionales
| Comando | Descripcion |
|---------|-------------|
| jobs | para ver si algun comando está corriendo en background |
| fg | traer a primer plano comandos en segundo plano |
| crom | Ejecuta en segundo plano a un horario establecido automaticamente por la computadora.Los asteriscos indican cada cuando se ejecutan cada segundo, minuto, dia, mes |


## Referencias
- []()