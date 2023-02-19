#rm

Opciones del comando ***rm***:
| Opcion | Opcion larga | Descripcion |
|--------|--------------|-------------|
| -i | --interactive | Antes de eliminar un archivo existente, solicite confirmación al usuario. Si no se especifica esta opción, rm eliminará los archivos de forma silenciosa. |
| -r | --recursive | Eliminar directorios recursivamente. Esto significa que si un directorio que se está eliminando tiene subdirectorios, elimínelos también. Para eliminar un directorio, se debe especificar esta opción. |
| -f | --force | Ignore los archivos inexistentes y no pregunte. Esto anula la opción --interactive. | 
| -v | --verbose | Mostrar mensajes informativos a medida que se realiza el borrado. |

Ejemplo comandos ***rm***:
| Comando | Resultado |
|---------|-----------|
| rm -i file1 |  Elimina el fichero1 de forma silenciosa. |
| rm -i file1 | Igual que el comando anterior, salvo que se pide confirmación al usuario antes de borrar el fichero. usuario se le pide confirmación antes de confirmación antes de borrar. |
| rm -r file1 dir1 |  Borrar file1 y dir1 y su contenido. |
| rm -rf file1 dir1 | Igual que el comando anterior, excepto que si archivo1 o dir1 no existen, rm continuará en silencio. |
