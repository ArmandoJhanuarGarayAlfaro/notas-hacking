# Retos Bandit

# Level 9 → Level 10

## Objetivo
The password for the next level is stored in the file **data.txt** in one of the few human-readable strings, preceded by several ‘=’ characters.

## Datos de acceso al nivel
bandit9
EN632PlfYiZbn3PhVK3XOGSlNInNE00t

## Solución
```bash
bandit9@bandit:~$ ls
data.txt
bandit9@bandit:~$ file data.txt
data.txt: data
bandit9@bandit:~$ strings data.txt | grep ==
c========== the
h;========== password
========== isT
n.E========== G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s
bandit9@bandit:~$
```
## Notas adicionales
| Comando | Descripcion |
|---------|-------------|
| grep | Se usa como filtro, permite filtrar y eliminar la informacion inutil y se suele usar con "\|" |
| strings | Muestra las cadenas de caracteres imprimibles que contengan los ficheros, util para visualizar ficheros qu no sean, o que no se sepan de que son de texto plano |

## Referencias
- [Funcion comando string](https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=&cad=rja&uact=8&ved=2ahUKEwj0ooe63Zv9AhWZl2oFHRntDyMQFnoECA4QAw&url=https%3A%2F%2Ffrancisconi.org%2Flinux%2Fcomandos%2Fstrings%23%3A~%3Atext%3DMuestra%2520las%2520cadenas%2520de%2520caracteres%2Cque%2520son%2520de%2520texto%2520plano.&usg=AOvVaw0L5KILzOv5-5oZdyaNTXgg)