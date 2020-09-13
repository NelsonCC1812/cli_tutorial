# Linea de comandos (CLI)
> shell: zsh

Como introduccion dejar claro que no estas usando los comandos de Mac, sino los comandos de Bash, que son los de linux, los mas usados en el mundo del desarrollo web ademas de los mas rapidos. Tambien tener en cuenta que hemos instalado el shell zsh que te permite autocompletar comandos y te ayuda a usar la linea de comandos de forma mas eficiente. A parte de otras cosas.

La linea de comandos nos permite hacer las cosas de forma mas rapida que por medios mas interactivos como el cursor, ademas que muchas de las tareas de un programador son por medio de linea de comandos, es importante familiarizarte con esta, cuando agarres soltura sera tu amiga.

Hay que entender que el sistema esta estructurado de cierta forma, y que hay que tener cuidado al hacer ciertas cosas, ya que es facil perderse en la linea de comandos. Nos vendra bien conocimientos en ingles, siempre intentaremos usar el ingles (tanto en el codigo como en nuestros archivos), de momento:

> ### Palabras en ingles y conceptos
> * **path**: ruta (`/Users/some/Desktop`)
> * **folder**: directorio quizas lo conozcas mas como carpeta
> * **file**: archivo (`texto.txt`)
> * **/**: slash
> * **root**: Raiz, el inicio de algo, la raiz de un proyecto es el directorio que lo contiene todo, y la raiz del sistema es (`/`)
> * **user**: Usuario, se referencia con este simbolo `~`.
> * **archivos ocultos**: Si ponemos un `.` delante del nombre del archivo este no se vera visualmente ni se listara por medios convencionales tambien lo podemos configurar con un archivo `.hidden`

# Como son las rutas
Las rutas estan compuestas de los nombres de las carpetas separados por "/" (`/Users/some/Desktop`) hay que tener en cuenta las mayusculas , los archivos suelen terminar con una extension (`.js`).

Hay dos tipos de rutas:
* **Absolutas**: Va desde la raiz del sistema en incluye todos los directorios hasta llegar al directorio o archivo que queremos referenciar
* **Relativas**: Son relativas al punto donde nos entontramos. 

## Como son los comandos
Los comandos tienen diferentes partes, pongamos como ejemplo el comando zip, (el $ significa que es una linea, cada $ indica que es otra linea), este comando no lo usaremos de momento, pero queda bien ejemplificado todas las partes de un comando estandar

```
$ zip -r folder.zip folder
```

* **zip**: Indica el comando o instruccion que usaremos, hay comandos que reciben comandos (`time`)
* **-r**: Las letras precedidas de un "-" son opciones (flags), distinguimos dos tipos de opciones, dependera tambien de lo que estemos usando, hay casos en las que existen ambas formas para la misma opcion
  * **-w**: Las que solo tienen un guion y una letra
  * **--watch**: Las que tienen dos guiones "--" y una palabra completa
  * > Algunas opciones pueden recibir por medio de un "=" un dato, valor, ruta... (`--prefix=server`)
* **file.zip / file** : Son parametros que recibe la instruccion, dependiendo de la instruccion necesitaremos mas o menos


## Comandos de movimiento
Estos comandos son para moverse por los directorios (carpetas).
Para entrar en un directorio puedes:
* Poner la ruta completa ()
```
cd /Users/some/Desktop
```
* Poner el nombre del directorio al que quieres ir, desde el que estas
```
cd Desktop
```
* Tambien puedes hacerlo sin usar el comando `cd`, esto gracias al shell, pero usarlo te facilita que funcione el autocompletado
  
## Comandos de listado

Estos comandos nos permiten ver que archivos y directorios hay en donde estamos referenciando:
* Para simplemente ver que archivos o directorios hay donde estamos
```
ls 
```
* Para ver con mas detalle:
```
l // Es lo mismo que poner ls -list (o -l) y -a
```
* Si queremos listar tambien los archivos ocultos podemos añadir la opcion `-a` a `ls`:
```
ls -a
```

* Podemos indicarle la ruta en la que lista, o añadirle `*` para que lo haga de forma recursiva:
```
ls stuff
```
```
ls *
```
## Añadir directorio
Para añadir un directorio usaremos el comando `md`:
```
md myfolder
```
Cabe resaltar que podemos crear varios a la vez, simplemente poniendo mas:
```
md directorio1 directorio2
```

## Añadir archivo
Para añadir un archivo usaremos el comando `touch`, al archivo que creemos podemos añadirle la extension
```
touch script.js
```

Podemos crear varios archivos a la vez, y tambien podemos crearlos dentro de archivos existentes
```
touch index.html scripts/script.js styles/style.css
```
## Comando para copiar
El comando `cp` nos permite copiar archivos de una ruta a otra
```
cp [origen] [destino]
```

## Comando para mover
```
mv [origen] [destino]
```
Un uso curioso de este comando es el de renombrar
```
mv [nombreAntiguo] [nombreNuevo]
```
## Comando para borrar
El comando `rm` nos permitira corrar archivos, para borrar un archivo:
```
rm file.txt
```
Para borrar directorios tendremos que usar las opciones: recursivo (`-r`)  y forzar `-r`:
```
rm -rf directorio
```

## WildCards, source, guion...

### Source (`.`)
Se utiliza en rutas relativas y hace referencia al directorio actual, si utilizamos dos hace referencia al directorio anterior en el arbol. A partir del segundo punto cada punto adicional hace referencia a un directorio anterior.

* Hace referencia al directorio actual
```
.
```
* Hace referencia al directorio anterior, si lo usamos como comando saltamos al directorio anterior
```
.. 
```

Esto haria saltar 3 directorios
```
...
```

> `...` = `../..`= `./../..`

### Guion  (`-`)

Hace referencia al directorio en el que nos encontrabamos anteriormente en orden cronologico, es decir, si saltamos varios directorios a la vez, nos lleva al directorio en el que nos encontrabamos antes del salto, no se puede encadenar con otras instrucciones


### Wildcards (`*`)

Nos permite seleccionar archivos, filtrar... Ademas los selecciona de forma unitaria, es decir, si por ejemplo usamos el comando `code` abrira todos los archivos que coicidan con la busqueda a la vez
La mejor forma de ver su uso es con ejemplos
```
ls * // Muestra todo lo que se encuentre en la carpeta actual con recursividad
```

```
ls ** /Hace lo mismo
```
```
ls *.js // lista todos los archivos de javascript que se encuentren en una carpeta
```

## Comandos varios

### Para saber que usuario estas utilizando
```
whoami
```
### Para saber la ruta (path) en donde estas
```
pwd
```

### Para abrir desde el Visual Studio Code (lo tienes que activar previamente)
```
code file.md
```
Para abrir la carpeta completa
```
code .
```

### Encadenar instrucciones

Puedes encadenar varias instrucciones utilizando ";" entre cada una de ellas:
```
md folder; touch folder/file.txt; open folder/file.txt
```

### Usar instrucciones anteriores

Puedes utilizar instrucciones anteriores seleccionandolas con las flejas (`upkey` y `downkey`)

### Autocompletado
El shell que estamos utilizando nos facilita mucho el trabajo, nos permite utilizar tabulaciones para autocompletar instrucciones, o incluso nos autocompleta los directorios y nos ayuda haciendolo case insensitive.

### Para visualizar archivos
```
cat file.txt
```
```
less file.txt
```
### Para modificar archivos
```
nano file.txt
```

### Abrir archivos
El comando open nos permite abrir archivos con la aplicacion predeterminada.
```
open index.html
```

Tambien podemos abrir paginas de internet en nuestro navegador
```
open https://github.com
```

### Para buscar palabras en archivos 
```
grep -rn "texto a buscar" .
```
* **grep**: Es la instruccion
* **-r**: Hace la busqueda recursiva
* **-n**: Muestra la linea donde se encontro la coincidencia dentro del archivo

### Cambiar los permisos
El comando `chmod` permite cambiar los permisos
* Tenemos tres clases que pueden recibir permisos : usuarios (u), grupos (g) y otros (o)
* Tenemos tres permisos: *read*(r), *write*(w) y *execute*(x)
* Tenemos tres operadores: añadir permiso (+), quitar permiso (-), establecer permisos (=)
* Podemos añadir la opcion `-R` para que sea recursivo.
```
chmod u=rmx g+r o-x dataFolder
```

### Superusuario
El famoso comando que nos permite hacer lo que queramos, debemos en la medida de lo posible no usar este comando, basicamente nos abre las puertas a hacer lo queramos, nos pedira la contraseña
```
sudo rm -rf stuff
```

### Ver opciones
El comando `man` nos permite ver lo que hace cierto comando
```
man ls
```

### Shutdown

Nos permite apagar despues de terminar los procesos (`-h`), sin terminar los procesos (`-p`), reiniciar (`r`) o suspender (`s`) el equipo. Nos permite programarlo para que los haga ahora (`now`), en un numero de minutos (`+numero`), o en una fecha(`yymmddhhmm`), una hora exacta (`23:00`). Podemos tambien especificar un mensaje que se mostrara a los usuarios antes de que se realice. Siempre tendremos que ejecutar este comando usando `sudo`.

Para cancelarlo tendremos que usar el comando
```
shutdown -c
```

### Buscar archivos

El comando `find` nos permite encontrar ficheros, tiene esta estructura:
```
find [path] [options]
```
#### Por nombre
```
find ~/Desktop/projects -name "myStuff.md"
```
```
find ~/Desktop/projects -name "*.js"
```
```
find . -name "*config*"
```

Si utilizas el comando `-iname` en vez de `-name` la busqueda sera case insensitive.

#### Buscar por tipo de fichero
Utiliza el flag `type` para indicar el tipo de fichero que quieres buscar: `d` (directorio), `f`(fichero regular) y `l` enlace simbolico.
```
find ~/Desktop/projects -iname "home" -type d
```

#### Buscar ficheros por fecha de modificacion
Utiliza los flags `-mmin` o `-mtime`, seguido de un valor numerico para especificar el tiempo de modificacion.

* `mmin`: Archivos modificados hace `n` minutos.
* `mtime`: Archivos modificados hace `n` dias.

Puedes añadir `+` para buscar mas antiguos que ese momento y `-` para que sea menor.
```
find ~/Desktop -mtime -2
```

#### Buscar ficheros por usuario y/o grupo
Utilizando el flag `-user` o el flag `group`.
```
find ~/Desktop -user some
```

### Buscar ficheros por tamaño
Usa el flag `-size` que recibe un valor numerico seguido de una unidad: `c`(bytes), `k`(kilobytes), `M`(megabytes) o `G`(Gigabytes)
```
find . -size 10k -type f
```

Tambien puedes especificar que sea mayor (`+`) o menor (`-`).


#### Excluir de la busqueda

Para excluir por ejemplo una ruta puedes usar:
```
find . -name "README.md" -not -path "*.git*"
```