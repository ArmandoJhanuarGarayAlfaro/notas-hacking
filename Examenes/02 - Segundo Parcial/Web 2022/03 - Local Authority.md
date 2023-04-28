# Local Authority

## Descripcion Reto
Can you get the flag? Go to this [website](http://saturn.picoctf.net:55983/) and see what you can discover.

## Pistas
1. How is the password checked on this website?

## Solución
```bash
```
![[Pasted image 20230416160923.png]]

![[Pasted image 20230416160944.png]]
Inspeccionar la página
![[Pasted image 20230416161037.png]]
```js
function checkPassword(username, password)
{
  if( username === 'admin' && password === 'strongPassword098765' )
  {
    return true;
  }
  else
  {
    return false;
  }
}
```
![[Pasted image 20230416161142.png]]
![[Pasted image 20230416161200.png]]

## Bandera
* picoCTF{j5_15_7r4n5p4r3n7_a8788e61}

## Notas adicionales
| Comando | Descripcion |
|---------|-------------|
|  |  |

## Referencias
- []()