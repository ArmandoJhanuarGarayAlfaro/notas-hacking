#comandos #descripcion

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
| file *filename* | Determinar el tipo de archivo. El comando imprimirá una breve descripción del contenido del archivo.| 
| less | Observa el contenido de los archivos |
| cp | Copia archivos y directorios |
| mv | Mueve/renombre archivos y directorios |
| mkdir | Crea directorios |
| rm | Elimina archivos y directorios |
| ln | Crea hard y Symbolic links |


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

| Comando | Descripcion |
|---------|-------------|
| ln *file link* | Crea un Hard link. Un enlace duro no puede hacer referencia a un fichero fuera de su propio sistema de ficheros. Esto significa que un enlace no puede hacer referencia a un archivo que no esté en la misma partición de disco que el propio enlace. Un enlace duro no puede hacer referencia a un directorio.|
| ln -s *item link* | Crea un Symbolic link. Los enlaces simbólicos se crearon para superar las limitaciones de los enlaces duros. Se parecen a los accesos directos. |
| type | Indicar cómo se interpreta el nombre de un comando |
| which | Mostrar qué programa ejecutable se ejecutará |
| help | Ayuda para shell buildins |
| man | Mostrar la página del manual de un comando |
| apropos | Mostrar una lista de comandos apropiados |
| info | Mostrar la entrada de información de un comando |
| whatis | Mostrar descripciones de página de manual de una línea |
| alias | Crear un alias para un comando |
| *command* --help | Mostrar información de uso |
| unalias | Usado para remover alias |

