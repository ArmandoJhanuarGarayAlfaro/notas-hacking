#comandos #descripcion
## Tabla de comandos con descripciones

| ----- Comando ----- | Descripcion |
|------------------------|-------------|
| \[me@linuxbox ~]# | Al terminar con # tiene permisos de superusuario |
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
