# Command Line Cheat Sheet

### Descriptores de rutas:

```shell
#Ruta raíz del sistema
/ 
#Directorio actual
. 
#Directorio anterior
.. 
#Directorio home del usuario
~ 
```

### Atajos de teclado:

```shell
# CTRL-C Termina el proceso de un comando en la terminal
# CTRL-D Termina el input de un comando
# CTRL-A Avanza al inicio de línea
# CTRL-E Avanza al final de línea
# CTRL-L Limpia la pantalla de la terminal
```

### Operaciones con directorios:

```bash
# Imprime el directorio actual
pwd 
# Crea el directorio con nombre dir1
mkdir dir1 
# Cambia al directorio con nombre dir1
cd dir1 
# Cambia dos directorios anteriores del actual
cd ../.. 
# Cambia al directorio home del usuario
cd 
# Muestra archivos y directorios
ls 
# Muestra todos los archivos y directorios anidados dentro de la ruta a cualquier nivel de profundidad
tree /ruta 
# Muestra todos los archivos y directorios anidados dentro de la ruta actual a dos niveles de profundidad.
tree -L 2 . 
```

### Operaciones de ls:

```bash
# Muestra todo (incluyendo archivos ocultos)
-a 
# Muestra una lista de manera recursiva
-R 
# Muestra listando de forma inversa
-r 
# Muestra los últimos modificados
-t 
# Muestra ordenando por tamaño
-S 
# Muestra usando un formato largo
-l 
```

### Manipulación de archivos y directorios:

```bash
# Crea un nuevo archivo llamado newFile
touch newFile 
# Muestra las características de mi_archivo
file mi_archivo 
# Copia el archivo file1 a la ruta /destino
cp file1 /destino 
# opia el directorio dir1 y su contenido a uno nuevo llamado dir1_cp
cp -r dir1 dir1_cp C
# Mueve el archivo file1 a la ruta /destino
mv file1 /destino 
# Renombra el archivo file1 al nombre ok_file
mv file1 ok_file 
# Elimina el archivo file1
rm file1 
# Elimina el directorio dir1 y su contenido de forma interactiva
rm -ri dir1 
# Elimina el directorio dir1 y su contenido de forma directa
rm -r dir1 
# Crea un link simbólico al archivo
ln -s file link_name 
# Abre el archivo con el programa predeterminado (MacOS)
open filename
# Abre el archivo con el programa predeterminado (mayoría de sistemas Linux)
xdg-open filename 
```

### Manipulación de archivos de texto:

```bash
# Muestra las primeras 10 líneas de texto del archivo file.txt
head file.txt 
# Muestra las primeras 20 líneas de texto del archivo file.txt
head -n 20 file.txt 
# Muestra las últimas 10 líneas de texto del archivo file.txt
tail file.txt 
# Muestra las últimas 20 líneas de texto del archivo file.txt
tail -n 20 file.txt 
# Explora el contenido de archivo con paginación
less file.txt 
# Concatena el contenido de file1 y file2 a la salida de la terminal
cat file1 file2 
```

### Exploración de comandos y ayuda dentro de la terminal:

```bash
# Muestra el manual de usuario del comando
man command 
# Muestra ayuda para el comando (solo funciona si la shell es Bash)
help command 
# Muestra la ruta de donde se encuentra el ejecutable del comando
which command 
# Muestra brevemente la función del comando
whatis command 
# Crea un alias para el comando
alias aliasname=”command” 
# Crea un alias para el comando ls con opciones llamado l
alias l=”ls -la” 

Wildcards
* # Coincide con cualquier carácter
? # Coincide con cualquier carácter individual
# Coincide con cualquier carácter que sea miembro del conjunto caracteres
[caracteres] 
# Coincide con cualquier carácter que no sea miembro del conjunto caracteres
[!caracteres] 
# Coincide con cualquier carácter de la clase
[[:clase:]] 
```

### Clases dentro de los Wildcards:

```bash
[:alnum:] # Coincide con cualquier carácter alfanumérico

[:alpha:] # Coincide con cualquier carácter alfabético

[:digit:] # Coincide con cualquier número

[:lower:] # Coincide con cualquier letra minúscula

[:upper:]#  Coincide con cualquier letra mayúscula
```

### Redirecciones I/O y operadores de control:

```bash
# Redirige el input de un comando hacia un archivo
comando < archivo
# Redirige la salida de un comando a un archivo (usarse con cuidado porque sobrescribe el sistema)
comando > archivo 
# Concatena la salida de un comando a un archivo. Si no existe lo crea.
comando >> archivo
# Redirige la salida de error de un comando al archivo error.txt
comando 2> error.txt
# Redirige la salida del comando1 a la entrada del comando2
comando1 | comando2
# Ejecuta de manera consecutiva
comando1; comando2
#Ejecuta de manera asíncrona
comando1 & comando2
# Ejecuta el comando2 si y solo si el comando1 se ejecutó de manera exitosa
comando1 && comando2
# Ejecuta el comando1 o el comando2
comando1 || comando2
```

### Manejo de permisos y usuarios:

#### Tipo de modo:

<table>
    <tr>
        <td colspan = "3">Diseño</td>
        <td colspan = "3">Grupo</td>
        <td colspan = "3">World</td>
    </tr>
    <tr>
        <td colspan = "3">rwx</td>
        <td colspan = "3">r-x</td>
        <td colspan = "3">r-x</td>
    </tr>
    <tr>
        <td>1</td>
        <td>1</td>
        <td>1</td>
        <td>1</td>
        <td>0</td>
        <td>1</td>
        <td>1</td>
        <td>0</td>
        <td>1</td>
    </tr>
</table>

#### Modo octal:

<table>
  <tr>
    <td>Octal</td><td>Binario</td><td>Permisos</td>
  </tr>
  <tr>
    <td>0</td><td>000</td><td>---</td>
  </tr>
  <tr>
    <td>1</td><td>001</td><td>--x</td>
  </tr>
  <tr>
    <td>2</td><td>010</td><td>-w-</td>
  </tr>
  <tr>
    <td>3</td><td>011</td><td>-wx</td>
  </tr>
  <tr>
    <td>4</td><td>100</td><td>r--</td>
  </tr>
  <tr>
    <td>5</td><td>101</td><td>r-x</td>
  </tr>
  <tr>
    <td>6</td><td>110</td><td>rw-</td>
  </tr>
  <tr>
    <td>7</td><td>111</td><td>rwx</td>
  </tr>
</table>

#### Modo simbólico:

<table>
  <tr>
    <td>Simbolo</td><td>Significado</td>
  </tr>
  <tr>
    <td>u</td><td>Solo para el usuario</td>
  </tr>
  <tr>
    <td>g</td><td>Solo para el grupo</td>
  </tr>
  <tr>
    <td>o</td><td>Solo para otros (es el world)</td>
  </tr>
  <tr>
    <td>a</td><td>Aplica para todos</td>
  </tr>
</table>

```bash
# mitexto Cambia los permisos del archivo a 755
chmod 755 
# Quita el permiso de lectura al archivo
chmod u-r mitexto 
# Agrega permiso de lectura, escritura y
ejecución al usuario y solo de lectura al grupo y otros.
chmod u=rwx,go=r mitexto 
# Muestra el ID del usuario
id 
# Muestra el nombre del usuario logueado
whoami 
# Cambia de usuario
su username 
# Ejecuta un comando como superusuario
sudo comando 
```

### Variables de entorno:

```bash
# Imprime las variables de entorno actuales
env 
# Imprime la variable de entorno VAR
echo $VAR 
# Variable donde están las rutas de los ejecutables
$PATH 
# Directorio home del usuario
$HOME 
# Asigna la variable $VAR con el valor val
export $VAR=val 
```

### Comandos de búsqueda:

```bash
# Busca en una ruta y con un nombre de archivo
find <ruta> -name <nombre> 
# Busca el archivo con el nombre agenda en el directorio actual
find . -name agenda 
# Busca con expresiones regulares dentro de un archivo o salida de terminal
grep <regex> file 
# Busca la palabra hola ignorando minúsculas y mayúsculas
grep -i hola mensaje.txt 

```

### Utilidades de red:

```bash
# Muestra información de red
ifconfig 
# Consulta la disponibilidad del recurso
ping ip_domain 
# Consulta un recurso ya sea por dirección IP o por dominio y lo y lo muestra en terminal
curl ip_domain 
# Descarga un recurso ya sea por dirección IP o por dominio traceroute ip_domain Muestra la ruta del paquete a una IP o dominio
wget ip_domain 
# Muestra las interfaces de red y su estado
netstat -i 
```

### Comprimir archivos:

```bash
tar -czvf <nombre>.tar.gz <nombre_directorio>
```

#### Ejemplo:

```bash
tar -czvf mis_archivos.tar.gz Documentos
```

### Descomprimir archivos:

```bash
tar -xzvf <nombre>.tar.gz <nombre_directorio>
```

#### Ejemplo:

```bash
tar -xzvf mis_archivos.tar.gz Documentos
```
