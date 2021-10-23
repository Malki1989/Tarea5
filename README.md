# Tarea 5 #

### Pasos a realizar una subida a una rama "Portada" de Github ###

- Utilizamos el comando **git clone** con el repositorio correspondiente. Una vez clonada, podemos entrar en ella con el comando **cd nombre-del-repositorio**.
   ![Clonar tarea](img/portada/1.png)

- Ahora creamos una nueva Rama que se va llamar Portada con el comando **git branch portada**.
   ![Creación rama](img/portada/2.png)

- Nos ubicamos en la nueva rama que hemos creado con el comando **git checkout**.
   ![Cambio rama](img/portada/3.png)

- Una vez dentro, crearemos el archivo con el comando de nuestra preferencia **touch/nano/vi** y lo llamaremos portada.html.

- Para añadir el archivo al proyecto tenemos que usar el comando **git add**.
   ![Añadir archivo](img/portada/4.png)

- Ejecutamos **git status** para comprobar que si se ha sincronizado correctamente. Si aparece en verde, está todo correcto.
   ![Comprobar sincronizado](img/portada/5.png)

- Ahora pasamos a registrar cambios en el historial con el comando **git commit -m "Comentario que queramos poner** y vemos que se ha realizado correctamente 
   ![Comando commit](img/portada/6.png)

- Ahora toca subir el archivo a Github a través del comando **git push --set upstream origin portada**.
   ![Comando push](img/portada/7.png)

- Ahora tenemos que hacer 4 commit más:

   - El primero será la modificación del archivo portada.html poniendo una estructura básica de una página html.
      ![Estructura HTML](img/portada/8.png)

   - Creamos la carpeta portada para las imágenes. 
      ![Creación carpeta imágenes](img/portada/9.png)

   - Colocamos las imágenes dentro de la carpeta creada anteriormente 
      ![Subida imágenes](img/portada/10.png)

### Clonación tarea ###

Realizamos un Fork del proyecto principal y descargamos dicho repositorio a nuestra máquina local

```
$ git clone https://github.com/Malki1989/Tarea5.git
Cloning into 'Tarea5'...
remote: Enumerating objects: 31, done.
remote: Counting objects: 100% (31/31), done.
remote: Compressing objects: 100% (23/23), done.
remote: Total 31 (delta 6), reused 18 (delta 1), pack-reused 0
Receiving objects: 100% (31/31), 5.39 KiB | 788.00 KiB/s, done.
Resolving deltas: 100% (6/6), done.

```

### Importación y configuración de ramas ###

- Primero de todo importamos las ramas y los cambios de la estructura con el comando **fetch**:

```
$ git fetch
```

- Hacemos una comprobación de las ramas del proyecto y que no haya ficheros nuevos que puedan entrar en conflicto.

```
$ git branch -va
* main                   5d51307 Merge pull request #2 from Malki1989/Test
  remotes/origin/Content 3c4cab6 Initial commit
  remotes/origin/HEAD    -> origin/main
  remotes/origin/Portada bd534e0 Escritira documento
  remotes/origin/Test    5418743 Segundo comment
  remotes/origin/header  3c4cab6 Initial commit
  remotes/origin/main    5d51307 Merge pull request #2 from Malki1989/Test

$ git pull
remote: Enumerating objects: 4, done.
remote: Counting objects: 100% (4/4), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (3/3), 753 bytes | 25.00 KiB/s, done.
From https://github.com/Malki1989/Tarea5      
   5d51307..7fe3a6a  main       -> origin/main
Updating 5d51307..7fe3a6a
Fast-forward
 index.html | 4 ++++
 1 file changed, 4 insertions(+)
 create mode 100644 index.html
```

- Nos movemos a la rama de trabajo con el comando **git switch** y apuntamos a la rama del repositorio remoto correspondiente con el comando **git branch --set-upstream-to**

```
$ git switch -c Content
Switched to a new branch 'Content'

$ git branch --set-upstream-to origin/Content
Branch 'Content' set up to track remote branch 'Content' from 'origin'.
```

### Creación, edición y puesta a producción de archivos ###

Creamos y editamos los archivos necesarios para que el proyecto siga adelante. Una vez realizados los cambios, vamos realizando los commit de cada uno de ellos.

- Archivo *content.html*

```
$ touch content.html

$ vsc content.html

$ git add content.html

$ git commit -m "Añadimos el content.html"
[Content ea2fa5a] Añadimos el content.html
 1 file changed, 14 insertions(+)
 create mode 100644 content.html
```
 
- Archivo *content.css*

```
$ touch content.css

$ vsc content.css

$ git add css/content.css 

$ git commit -m "Añadir content.css"
[Content f3dfa41] Añadir content.css
 1 file changed, 3 insertions(+)    
 create mode 100644 css/content.css
```

- Inclusión del archivo content.html al archivo index.html.

```
$ vsc index.html

$ git add index.html

$ git commit -m "Incluimos el nuestro fichero en el index"
[Content 8c0e9b6] Incluimos el nuestro fichero en el index
 1 file changed, 5 insertions(+)
```


- Comprobación de actualizaciones en la rama.

```
$ git pull
remote: Enumerating objects: 28, done.
remote: Counting objects: 100% (28/28), done.
remote: Compressing objects: 100% (18/18), done.
remote: Total 24 (delta 5), reused 24 (delta 5), pack-reused 0
Unpacking objects: 100% (24/24), 240.12 KiB | 1.33 MiB/s, done.
From https://github.com/Malki1989/Tarea5
   2d00370..d8631e8  Portada    -> origin/Portada
Your configuration specifies to merge with the ref 'refs/heads/Content'
from the remote, but no such ref was fetched.
```

- Modificación del archivo content.html para añadir incluya el archivo css correspondiente.

```
$ vsc content.html

$ git add content.html

$ git commit -m "Incluimos el css que no incluimos antes en el content.html"
[Content a4f3978] Incluimos el css que no incluimos antes en el content.html
 1 file changed, 1 insertion(+)
```

- Edición del archivo README.md para incluir las instrucciones de funcionamiento.

```
$ vsc README.md

# Añadimos al stage
$ git add README.md

# Hacemos el commit
$ git commit -m "Añadimos instruccions al README.md"
[Content 2967631] Añadimos instruccions al README.md
 1 file changed, 1 insertion(+), 2 deletions(-)
```

### Subida de archivos a producción ###

Una vez realizados todos nuestros cambios, realizamos un **git push** para que los suba a nuestra rama.

```
$ git push 
Enumerating objects: 19, done.
Counting objects: 100% (19/19), done.
Delta compression using up to 4 threads
Compressing objects: 100% (13/13), done.
Writing objects: 100% (16/16), 1.72 KiB | 294.00 KiB/s, done.
Total 16 (delta 5), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (5/5), done.
remote: 
remote: Create a pull request for 'Content' on GitHub by visiting:
remote:      https://github.com/Malki1989/Tarea5/pull/new/Content
remote:
remote: Heads up! The branch 'Content' that you pushed to was renamed to 'Malki-features'.
remote:
To https://github.com/Malki1989/Tarea5.git
 * [new branch]      Content -> Content
```

Una vez subidos los cambios, creamos un *pull request* para que se puedan corregir los conflictos surgidos y poder realizar correctamente el *merge*


### Footer - Vicente

- Git clone
En esta Tarea debemos trabajar en equipo, por lo tanto la manera en la que lo vamos a hacer va a ser clonando el reposotorio remoto original. Con el comando ***git clone***.

![Imagen1](./img/footer1)

- Git branch & git checkout
Una vez clonado el repositorio local cambiamos de directorio a este. Una vez estemos dentro del directorio debemos crear una rama nueva con el comando ***git branch nombre_de la_rama***, esto lo hacemos para ir subiendo los cambios y trabajando en un lugar distinto del mismo proyecto que los demás, esto lo hacemos para no pisarnos el trabajo los unos a los otros. Para hacer esto efectivo debemos cambiar de la rama main en la que nos encontramos a la nueva que acabamos de crear con el comando ***git checkout nombre_de la_rama***.

![Imagen2](./img/footer2)

- Git branch -va
Podemos usar el comando ***git branch -va*** para listar todas las ramas, tanto remotas como locales. Y cómo vemos las locales serían la main y footer_vicente.

![Imagen3](./img/footer3)

- Git add y git commit
Después de realizar los cambios que requería la práctica y he realizado en el vídeo debemos hacer ***git add .***  y después ***git commit*** para dejar estos cambios preparados para subir.

![Imagen4](./img/footer4)

- Git push
Una vez ya tengamos todos los cambios necesarios y estemos preparados para hacer el push, vamos a lanzarlo con el comando ***git push origin nombre_de la_rama_nueva*** para, de esta manera subir los cambios a nuestra rama y crearla en remoto, ya que recordemos que de momento sólo la teniamos en local. Y así cómo está indicado en la segunda captura vemos que los cambios efectivamente se suben a nuestra rama.

![Imagen5](./img/footer5)

![Imagen6](./img/footer6)

En esta captura vemos que aparece en el repositorio de GitHub aparece que se ha creado una rama nueva.

![Imagen7](./img/footer7)

- Pull request y merge

Para finalizar, lo que debemos hacer es solicitar un pull request y esperar a que el propietario o encargado del proyecto revise y acepte los cambios que queremos incorporar y fusionar a la rama principal.

![Imagen8](./img/footer8)
![Imagen9](./img/footer9)

> Revisión y edición final del archivo README hecha por Toni Gomila :v:
