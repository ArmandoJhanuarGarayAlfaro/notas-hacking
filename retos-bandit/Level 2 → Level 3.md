Retos Bandit

Para documentar los retos bandit usaremos la siguiente plantilla

# Level 2 → Level 3

## Objetivo
The password for the next level is stored in a file called **spaces in this filename** located in the home directory

## Datos de acceso al nivel
- bandit2
- rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi

## Solución
```bash
bandit2@bandit:~$ cat spaces in this filename
cat: spaces: No such file or directory
cat: in: No such file or directory
cat: this: No such file or directory
cat: filename: No such file or directory
bandit2@bandit:~$ cat spaces\ in\ this\ filename
aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG
bandit2@bandit:~$ cat "spaces in this filename"
aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG
bandit2@bandit:~$
```
## Notas adicionales
| Comando | Descripcion |
|---------|-------------|
| cat diagonal invertida  | Sirve para evitar problemas con los espacios |
| cat "" | Sirve para evitar problemas con los espacios |
| \\ | Permite que los nombres de los archivos con espacios no causen problemas |

## Referencias
- []()