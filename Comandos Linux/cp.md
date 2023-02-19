#cp

# Copia archivos y directorios

Opciones del comando ***cp***:
| Opcion | Opcion larga | Descripcion |
|--------|--------------|-------------|
| -a | --archive | Copie los archivos y directorios y todos sus atributos, incluidas las propiedades y los permisos. Normalmente, las copias toman los atributos predeterminados del usuario que realiza la copia. |
| -i | --iteractive | Antes de sobrescribir un archivo existente, solicite confirmación al usuario. Si no se especifica esta opción, cp sobrescribirá los archivos de forma silenciosa (lo que significa que no habrá advertencia). |
| -r | --recursive | Copia recursivamente de directorios y sus contenidos. Esta opción (o la opción -a) es necesaria al copiar directorios |
| -u | --update | Al copiar archivos de un directorio a otro, solo copie los archivos que no existen o que son más nuevos que los archivos correspondientes existentes en el directorio de destino. Esto es útil cuando se copian grandes cantidades de archivos, ya que omite los archivos que no necesitan copiarse. |
| -v | --verbose | Mostrar mensajes informativos a medida que se realiza la copia. |

Ejemplo comandos ***cp***:
| Comando | Resultado |
|---------|-----------|
| cp archivo1 archivo2 | Copie el archivo1 al archivo2. Si el archivo2 existe, se sobrescribe con el contenido del archivo1. Si el archivo2 no existe, se crea. |
| cp -i archivo1 archivo2 | Igual que el comando anterior, excepto que si archivo2 existe, se le pregunta al usuario antes de que se sobrescriba. |
| cp archivo1 archivo2 dir1 | Copie archivo1 y archivo2 en el directorio dir1. El directorio dir1 ya debe existir.|
| cp dir1/* dir2 | Usando un comodín, copie todos los archivos en dir1 en dir2. El directorio dir2 ya debe existir. |
| cp -r dir1 dir2 | Copia el contenido del directorio dir1 al directorio dir2. Si el directorio dir2 no existe, se crea y, después de la copia, tendrá el mismo contenido como directorio dir1. Si el directorio dir2 existe, entonces el directorio dir1 (y su contenido) se copiará en dir2. |