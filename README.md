# Tarea5

## Pasos a realizar una subida a una rama "Portada" de Github 
- Usando el comando git clone https://github.com/Malki1989/Tarea5.git y entramos en la caprpeta con el comando cd Tarea5![GitHub Logo](img/portada/1.png)
- Ahora creamos una nueva Rama que se va llamar Portada  con el comando **git branch portada**![GitHub Logo](img/portada/2.png)
- Nos ubicams en la nueva rama que hemos creado con el comando **git checkout**![GitHub Logo](img/portada/3.png)
- Una vez dentro crearemos con el comando sudo **touch / nano /vi** y lo llamaremos Portada.html 
- Para añadir el archivo al proyecto tenemos que usar el comando **git add Portada.html** ![GitHub Logo](img/portada/4.png)
- Volvemos a hacer un **git status** y vemos que se ha sincronizado correctamente si aparece en verde![GitHub Logo](img/portada/5.png)
- Ahora pasamos a registrar cambios en el historial con el comando **git commit -m "Comentario que queramos poner** y vemos que se ha realizado correctamente ![GitHub Logo](img/portada/6.png)
- Ahora toca subir el archivo a gitlab a traves del comando **git push --set  upstream origin Portada** ![GitHub Logo](img/portada/7.png)
- Ahora tenemos que hacer 4 comit mas en este caso sera la modificacion del README.md subida de varias imagenens y creacion de carpeta donde se guarda las imagenes 
- El primero sera la modificaccion del archivo portada.html poniendo una estructura basica de  una pagina  html ![GitHub Logo](img/portada/8.png)
- Creamos la carpeta portada para las imagenes ![GitHub Logo](img/portada/9.png)
- Colocamos las imagenes detro de esa carpeta ![GitHub Logo](img/portada/10.png)

$ git clone https://github.com/Malki1989/Tarea5.git
Cloning into 'Tarea5'...
remote: Enumerating objects: 31, done.
remote: Counting objects: 100% (31/31), done.
remote: Compressing objects: 100% (23/23), done.
remote: Total 31 (delta 6), reused 18 (delta 1), pack-reused 0
Receiving objects: 100% (31/31), 5.39 KiB | 788.00 KiB/s, done.
Resolving deltas: 100% (6/6), done.

# importamos las ramas i los cambios de la estructura
$ git fetch

# Comprovamos las ramas que hay

$ git branch -va
* main                   5d51307 Merge pull request #2 from Malki1989/Test
  remotes/origin/Content 3c4cab6 Initial commit
  remotes/origin/HEAD    -> origin/main
  remotes/origin/Portada bd534e0 Escritira documento
  remotes/origin/Test    5418743 Segundo comment
  remotes/origin/header  3c4cab6 Initial commit
  remotes/origin/main    5d51307 Merge pull request #2 from Malki1989/Test
  
# Comprovamos que no haya ficheros nuevos

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
 
# Nos movemos a nuestra rama.

$ git switch -c Content
Switched to a new branch 'Content'

# Hacemos que los cambios de nuestra nueva rama apunten al remoto correspondiente.

$ git branch --set-upstream-to origin/Content
Branch 'Content' set up to track remote branch 'Content' from 'origin'.

# Creamos los cambios del projecto

$ touch content.html

# Editamos el content con la información principal
$ vsc content.html

# Añadimos al stage
$git add content.html

# Hacemos el commit
$ git commit -m "Añadimos el content.html"
[Content ea2fa5a] Añadimos el content.html
 1 file changed, 14 insertions(+)
 create mode 100644 content.html
 
 # Creamos los estilos del content.html
 $ touch content.css

# Añadimos los estilos del content
$ vsc content.css

# Añadimos al stage
$ git add css/content.css 

# Hacemos el commit
$ git commit -m "Añadir content.css"
[Content f3dfa41] Añadir content.css
 1 file changed, 3 insertions(+)    
 create mode 100644 css/content.css 

# Abrimos el fichero principal
$ vsc index.html

# Añadimos al stage
$ git add index.html

# Hacemos el commit
$ git commit -m "Incluimos el nuestro fichero en el index"
[Content 8c0e9b6] Incluimos el nuestro fichero en el index
 1 file changed, 5 insertions(+)
 
# Comprovamos i actualizamos los cambios de la rama
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

# Editamos el content para incluir los css
$ vsc content.html

# Añadimos al stage
$ git add content.html

# Hacemos el commit
$ git commit -m "Incluimos el css que no incluimos antes en el content.html"
[Content a4f3978] Incluimos el css que no incluimos antes en el content.html
 1 file changed, 1 insertion(+)

# Añadimos las instruccions de funcionamiento
$ vsc README.md

# Añadimos al stage
$ git add README.md

# Hacemos el commit
$ git commit -m "Añadimos instruccions al README.md"
[Content 2967631] Añadimos instruccions al README.md
 1 file changed, 1 insertion(+), 2 deletions(-)

# Subimos los cambios a la rama
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
 # Creamos un pull request, corregimos los conflictos i hacemos el merge.


