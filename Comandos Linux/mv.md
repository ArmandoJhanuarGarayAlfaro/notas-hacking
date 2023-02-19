#mv

Opciones del comando ***mv***:
| Opcion | Opcion larga | Descripcion |
|--------|--------------|-------------|
| -i | --interactive | Antes de sobrescribir un archivo existente, solicite confirmación al usuario. Si no se especifica esta opción, mv sobrescribirá los archivos de forma silenciosa. |
| -u | --update | Al mover archivos de un directorio a otro, solo mueva los archivos que no existen o que son más nuevos que los archivos correspondientes existentes en el directorio de destino. |
| -v | --verbose | Mostrar mensajes informativos a medida que se realiza el movimiento. |

Ejemplo comandos ***mv***:
| Comando | Resultado |
|---------|-----------|
| mv file1 file2 | Mover archivo1 a archivo2. Si el archivo2 existe, se sobrescribe con el contenido del archivo1. Si el archivo2 no existe, es creado. En cualquier caso, file1 deja de existir. |
| mv -i file1 file2 | Igual que el comando anterior, excepto que si archivo2 existe, se le pregunta al usuario antes de que se sobrescriba. |
| mv file1 file2 dir1 | Mueva file1 y file2 al directorio dir1. El directorio dir1 ya debe existir. |
| mv dir1 dir2 | Si el directorio dir2 no existe, cree el directorio dir2 y mueva el contenido del directorio dir1 a dir2 y elimine el directorio dir1. Si el directorio dir2 existe, mueva el directorio dir1 (y su contenido) al directorio dir2. |
