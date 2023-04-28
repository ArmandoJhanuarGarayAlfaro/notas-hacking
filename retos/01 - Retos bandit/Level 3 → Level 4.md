# Retos Bandit

# Level X

## Objetivo
The password for the next level is stored in a hidden file in the **inhere** directory.

## Datos de acceso al nivel
- **Usuario:** bandit3
- **Contraseña:** aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG

## Solución
```bash
bandit3@bandit:~$ ls
inhere
bandit3@bandit:~$ cd inhere/
bandit3@bandit:~/inhere$ ls
bandit3@bandit:~/inhere$ ls -la
total 12
drwxr-xr-x 2 root    root    4096 Jan 11 19:19 .
drwxr-xr-x 3 root    root    4096 Jan 11 19:19 ..
-rw-r----- 1 bandit4 bandit3   33 Jan 11 19:19 .hidden
bandit3@bandit:~/inhere$ cat .hidden
2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe
```
## Notas adicionales
| Comando | Descripcion |
|---------|-------------|
| ls -la | Lista los archivos de forma larga con sus prefijos |

## Referencias
- []()
