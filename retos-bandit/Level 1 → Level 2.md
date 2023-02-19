# Retos Bandit

# Level 1 → Level 2

## Objetivo
The password for the next level is stored in a file called **-** located in the home directory

## Datos de acceso al nivel
- bandit1
- NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL

## Solución
```bash
bandit1@bandit:~$ ls - 
bandit1@bandit:~$ cat - ^C 
bandit1@bandit:~$ cat ./- 
rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi 
bandit1@bandit:~$ pwd /home/bandit1 
bandit1@bandit:~$ cat /home/bandit1/- 
rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi 
bandit1@bandit:~$
```
## Notas adicionales
| Comando | Descripcion |
|---------|-------------|
| cat | Permite ver el contenido de un archivo |
| ./* | Indica el directorio actual |
## Referencias
- [Entrar a un archivo en mismo directorio](https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=&cad=rja&uact=8&ved=2ahUKEwihx53L1pr9AhWeN0QIHdDyC0cQFnoECAgQAQ&url=https%3A%2F%2Fstackoverflow.com%2Fquestions%2F42187323%2Fhow-to-open-a-dashed-filename-using-terminal&usg=AOvVaw1DWOaW6dQB70W6_VW1gcZu)

