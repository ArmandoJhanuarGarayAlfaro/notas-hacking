# Lets Warm Up

## Descripcion Reto
If I told you a word started with 0x70 in hexadecimal, what would it start with in ASCII?

## Pistas
1. Submit your answer in our flag format. For example, if your answer was 'hello', you would submit 'picoCTF{hello}' as the flag.

## Solución
```python
>>> chr(0x70)
'p'
>>> 
```

## Bandera
* picoCTF{p}

## Notas adicionales
| Comando | Descripcion |
|---------|-------------|
| chr | Convierte un valor Hexadecimal a ASCII |

## Referencias
- [Conversion Hexadecimal a ASCII](https://www.rapidtables.com/convert/number/hex-to-ascii.html)