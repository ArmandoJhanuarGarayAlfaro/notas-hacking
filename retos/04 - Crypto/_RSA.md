# \_Rsa

| Variable | Descripcion |
|---------|-------------|
| c | texto cifrado |
| m | mensaje texto plano |
| p | primo 1 |
| q | primo 2 |
| n | modulo |
| tn | totient n (euler) |
| e | exponente (llave publica) 2^16+1 = 65537 |

n = p \* q
tn = (p-1) \* (q-1)
d = e mod   inv   tn   /   inverse(e,tn)

|  |  |
|---------|-------------|
| Encriptar | c = m^e mod n   \|   pow(m,e,n) |
| Desencriptar | m = c^d mod n   \|   pow(c,d,n) |

Despejar encriptado (c = m^e mod n) cuando:
* e demasiado pequeña
* n demasiado grande
* m demasiado corto
c = m^e mod n
c = m^e
m = e raiz c