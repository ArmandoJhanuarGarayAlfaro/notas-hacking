# SQL Direct

## Descripcion Reto
Connect to this PostgreSQL server and find the flag! `psql -h saturn.picoctf.net -p 53921 -U postgres pico` Password is `postgres`

## Pistas
1. (None)

## Solución
```bash
┌──(kali㉿kali)-[~/hacking/localAuthority]
└─$ psql -h saturn.picoctf.net -p 53921 -U postgres pico
Contraseña para usuario postgres: 
psql (15.2 (Debian 15.2-2))
Digite «help» para obtener ayuda.

pico=# \dt
        Listado de relaciones
 Esquema | Nombre | Tipo  |  Dueño   
---------+--------+-------+----------
 public  | flags  | tabla | postgres
(1 fila)

pico=# SELECT * FROM flags;

	id | firstname | lastname  |                address                 
	----+-----------+-----------+----------------------------------------
	  1 | Luke      | Skywalker | picoCTF{L3arN_S0m3_5qL_t0d4Y_21c94904}
	  2 | Leia      | Organa    | Alderaan
	  3 | Han       | Solo      | Corellia
	(3 filas)
pico=# 

```

## Bandera
* picoCTF{L3arN_S0m3_5qL_t0d4Y_21c94904}

## Notas adicionales
| Comando | Descripcion |
|---------|-------------|
| psql | Es un comando que nos permite acceder mediante una consola de comandos a la base de datos PostgreSQL para hacer las gestiones oportunas. |

## Referencias
- [psql](https://ayuda.guebs.com/usar-psql-conectar-base-datos-postgresql/)