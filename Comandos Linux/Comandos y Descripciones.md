#comandos
| Comando | Descripcion |
|---------|-------------|
| [me@linuxbox ~]# | Al terminar con # tiene permisos de superusuario |
| date | Muestra la hora actual y la fecha |
| cal | Muestra el calendario del mes actual |
| df | Para ver la cantidad actual de espacio libre en nuestras unidades de disco |
| free | Para mostrar la cantidad de memoria libre |
| exit | Para salir de la sesión, o usar el comando **Ctrl-d** |
| pwd | Imprime el nombre del directorio actual de trabajo actual |
| cd /directorio/ | **Cambia de directorio.** Existen rutas absolutas y relativas, las absolutas tienen el nombre del directorio las relativas usan "." y "..", el "." se refire al directorio de trabajo, el ".." se refuere al directorio principal de trabajo|
|  cd | Solo este comando solitario cambia el dierctorio actual al directorio home |
| cd - | Cambia el directorio de trabajo actual al directorio de trabajo previo |
| cd ~user_name | Cambia el directorio de trabajo al directorio de inicio de nombre de usuario. Por ejemplo, cd ~bob cambiará el directorio a el directorio de inicio del usuario "bob". |
| ls | Muestra el contenido del directorio |
| ls -a | muestra los archivos ocultos por el -a |
| ls /usr | Lista los archivos del directorio especificado |
| ls ~ /usr | Enumeramos tanto el usuario directorio de inicio (simbolizado por el carácter "~") y el directorio /usr |
| ls -l | Se listan los archivos del directorio con el formato largo especificado por "-l" |
| ls -t | Ordena el listado de archivos por el tiempo de modificación del archivo |
| ls -lt --reverse | revierte el orden de clasificación |

Opciones comunes del comando ls que lo acompañan:
| Opcion | Opcion larga | Descripcion |
|--------|--------------|-------------|
| -a | --all | Enumere todos los archivos, incluso aquellos con nombres que comienzan con un período, que normalmente no se enumeran (es decir, oculto). |
| -A | --almost-all | Como la opción -a anterior, excepto que no lista . (directorio actual) y .. (padre directorio). |
| -d | --directory | Normalmente, si se especifica un directorio, ls enumerar el contenido del directorio, no el directorio en sí. Utilice esta opción junto con con la opción -l para ver detalles sobre el directorio en lugar de su contenido. |
| -F | --classify | Esta opción agregará un carácter indicador al final de cada nombre enumerado. por ejemplo, un barra diagonal (/) si el nombre es un directorio. |
| -h | --human-readable | En listados de formato largo, muestre los tamaños de archivo en formato legible por humanos en lugar de en bytes. |
| -l | |  Muestra el resultado en formato largo |
| -r | --reverse | Muestre los resultados en orden inverso. Normalmente, ls muestra sus resultados en orden ascendente orden alfabetico.