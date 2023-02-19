#wildcard #characterClass #pattern

| Wildcard | Descripcion |
|---------|-------------|
| * |  Coincidencias con cualquier carácter |
| ? | Coincidencia con cualquier caracter unico |
| \[characters\] | Coincide con cualquier carácter que sea miembro del conjunto de caracteres |
| \[!characters\] | Coincide con cualquier carácter que no sea miembro del conjunto caracteres |
| \[[:class:\]] | Coincide con cualquier carácter que sea miembro del especificado clase |

| Character Class | Descripcion |
|---------|-------------|
| [:alnum:] | Coincide con cualquier carácter alfanumérico |
| [:alpha:] | Coincide con cualquier carácter alfabético |
| [:digit:] | Coincide con cualquier número |
| [:lower:] | Coincide con cualquier letra minúscula |
| [:upper:] | Coincide con cualquier letra mayúscula |

| Pattern | Descripcion |
|---------|-------------|
| * | Todos los archivos |
| g* | Cualquier archivo que comience con “g” |
|b*.txt | Cualquier archivo que comience con "b" seguido de cualquier carácter y terminando con “.txt” |
| ¿¿¿Datos??? Cualquier archivo que comience con "Data" seguido por exactamente tres caracteres [abc]* Cualquier archivo que comience con una "a", una “b”, o una “c” BACKUP.[0-9][0-9][0-9] Cualquier archivo que comience con “BACKUP”. seguido de exactamente tres números [[:upper:]]* Cualquier archivo que comience con una letra mayúscula [![:digit:]]* Cualquier archivo que no comience con un número *[[:lower:]123] Cualquier archivo que termine con una letra minúscula o los números “1”, “2” o “3”