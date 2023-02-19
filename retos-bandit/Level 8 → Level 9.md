# Retos Bandit

# Level 8 → Level 9

## Objetivo
The password for the next level is stored in the file **data.txt** in one of the few human-readable strings, preceded by several ‘=’ characters.

## Datos de acceso al nivel
- bandit8
- TESKZC0XvTetK0S9xNwm25STk5iWrBvP

## Solución
```bash
bandit8@bandit:~$ ls
data.txt
bandit8@bandit:~$ wc data.txt
 1001  1001 33033 data.txt
bandit8@bandit:~$ sort data.txt | uniq -u
EN632PlfYiZbn3PhVK3XOGSlNInNE00t
```
## Notas adicionales
| Comando | Descripcion |
|---------|-------------|
| sort | Ordena, es un comando que ordena las lineas de archivos de texto. Permite ordenar alfabeticamente, inverso, numero, mes y puede eliminar duplicados |
| uniq | Ayuda a detectar las líneas duplicadas adyacentes y también elimina las líneas duplicadas |
| wc | Hace conteos de entradas estandar como palabras, caracteres o saltos de linea |

## Referencias
- []()