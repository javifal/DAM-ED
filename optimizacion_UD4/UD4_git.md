# El control de versiones mediante git

## Introducción

*Se llama control de versiones a la gestión de los diversos cambios que se realizan sobre los elementos de algún producto o una configuración del mismo. Una versión, revisión o edición de un producto, es el estado en el que se encuentra el mismo en un momento dado de su desarrollo o modificación.* [Fuente](https://es.wikipedia.org/wiki/Control_de_versiones).

[Git](https://git-scm.com) es un sistema de control de versiones cuyo cometido es tener controlados los cambios que se producen en los ficheros. Para ello, podemos decir que cuando se lo indicamos va tomando [_fotografías_](https://git-scm.com/book/es/v1/Empezando-Fundamentos-de-Git) de los ficheros y nos muestra qué cosas han cambiado en los ficheros desde la anterior fotografía a la actual.

Hay que familiarizarse con el concepto de repositorio de código.


## Configuración en Windows

[Instalación de git en Windows](http://www.programandoapasitos.com/2016/08/instalacion-y-configuracion-de-git-en.html)

## Estados de los ficheros en git

*Esto es lo más importante a recordar acerca de Git si quieres que el resto de tu proceso de aprendizaje prosiga sin problemas. Git tiene tres estados principales en los que se pueden encontrar tus archivos: confirmado (committed), modificado (modified), y preparado (staged). Confirmado significa que los datos están almacenados de manera segura en tu base de datos local. Modificado significa que has modificado el archivo pero todavía no lo has confirmado a tu base de datos. Preparado significa que has marcado un archivo modificado en su versión actual para que vaya en tu próxima confirmación.*

*Esto nos lleva a las tres secciones principales de un proyecto de Git: el directorio de Git (Git directory), el directorio de trabajo (working directory), y el área de preparación (staging area).*

![Estados de git](https://git-scm.com/figures/18333fig0106-tn.png "Estados de los ficheros en git. Fuente: https://git-scm.com")

### Comandos básicos

* git presenta multitud de comandos para los propósitos más diversos. Sin embargo, la mayoría de nuestro trabajo con él puede hacerse con menos de 10 comandos. 

	* init
	* add
	* checkout
	* commit
	* pull
	* merge
	* push
	* clone

[Guía de comandos básicos](https://www.hostinger.es/tutoriales/comandos-de-git#gref)

### Etiquetar las versiones

*Los tag son una manera de etiquetar estados de tu repositorio, que se usa comúnmente para indicar las versiones o releases de un proyecto.*

*Git tiene la posibilidad de marcar estados importantes en la vida de un repositorio, algo que se suele usar habitualmente para el manejo de las releases de un proyecto. A través del comando "git tag" lo podemos hacer, en una operación que se conoce comúnmente con el nombre de "tagging". Es una operativa que tiene muchas variantes y utilidades, nosotros veremos las más habituales que estamos seguros te agradará conocer.* [Fuente](https://desarrolloweb.com/articulos/especificar-versiones-git-tag.html)

#### Etiquetas ligeras vs Etiquetas anotadas

*Git usa dos tipos principales de etiquetas: ligeras y anotadas. Una etiqueta ligera es muy parecida a una rama que no cambia —un puntero a una confirmación específica—.* 

*Sin embargo, las etiquetas anotadas son almacenadas como objetos completos en la base de datos de Git. Tienen suma de comprobación; contienen el nombre del etiquetador, correo electrónico y fecha; tienen mensaje de etiquetado; y pueden estar firmadas y verificadas con GNU Privacy Guard (GPG). Generalmente se recomienda crear etiquetas anotadas para disponer de toda esta información; pero si por alguna razón quieres una etiqueta temporal y no quieres almacenar el resto de información, también tiene disponibles las etiquetas ligeras.*

[Más info ES](https://git-scm.com/book/es/v1/Fundamentos-de-Git-Creando-etiquetas)

### Qué es el archivo .gitignore, para qué sirve, cómo implementar el gitignore en un repositorio Git.


*Git tiene una herramienta imprescindible casi en cualquier proyecto, el archivo "gitignore", que sirve para decirle a Git qué archivos o directorios completos debe ignorar y no subir al repositorio de código.*

*Su implementación es muy sencilla, por lo que no hay motivo para no usarlo en cualquier proyecto y para cualquier nivel de conocimientos de Git que tenga el desarrollador. Únicamente se necesita crear un archivo especificando qué elementos se deben ignorar y, a partir de entonces, realizar el resto del proceso para trabajo con Git de manera habitual.* [Fuente](https://desarrolloweb.com/articulos/archivo-gitignore.html)


### El stash. Cuando queremos esconder nuestros cambios.

Hay ocasiones en las que tenemos cosas en una rama sin commitear y surge la necesidad urgente de cambiar a otra rama. Si el proceso del commit en ese caso es tedioso: Hay que seleccionar qué ficheros se añaden y cuales no, etc. hay una alternativa para guardar de forma rápida nuestros cambios para:

1. Poder recuperarlos después
2. Poder cambiar a otra rama o crearla sin que estén presentes los cambios actuales.

[Doc oficial](https://git-scm.com/book/es/v1/Las-herramientas-de-Git-Guardado-rápido-provisional)

### Fetch

* ```git fetch``` Sirve para recuperar los cambios del repositorio remoto al local pero dejándolos en otra rama. Hay que recordar que al hacer pull sí se trae a la rama actual. Hay clientes de git, que al hacer pull hacen también fetch de forma automática.

[Más sobre fetch](https://es.stackoverflow.com/questions/245/cuál-es-la-diferencia-entre-pull-y-fetch-en-git)

* [git rebase vs git pull rebase](http://cambrico.net/git-control-de-versiones/rebase-en-git)

### Pull Request

*La traducción directa sería algo así como "Petición de Validación". Una Pull Request es la acción de validar un código que se va a mergear de una rama a otra. En este proceso de validación pueden entrar los factores que queramos: Builds (validaciones automáticas), asignación de código a tareas, validaciones manuales por parte del equipo, despliegues, etc.* [Fuente](http://www.nocountryforgeeks.com/pull-requests/)

### Versatilidad de los comandos en git. Ejemplo de checkout.

* La función principal es para cambiar de rama ```git checkout nombreRama```
* También permite crearlas ```git checkout -b```
* Es posible deshacer los cambios ```git checkout -- ficheros```

### git reset y git revert. Borrando o Deshaciendo cosas

Si ```git add``` es el comando habitual para decir que los ficheros están listos para ser commiteados, ```git reset``` lo es para decir que los ficheros que habíamos señalado como listos, no lo están. Puede ser porque se nos ha olvidado poner algo en el fichero o quitar algo que sobra, etc. Antes de hacer el commit, es posible quitar esos ficheros del commit. Lo que aparece a continuación se muestra siempre en el terminal cuando se ven los ficheros añadidos.

```
Changes to be committed:
#   (use "git reset HEAD <file>..." to unstage)
#
```

[Borrar el último commit con reset y revert](https://www.solucionex.com/blog/borrar-ultimo-commit-con-reset-y-revert-en-git)


## Recursos

* __Ayuda de git__. Prueba a escribir -h a continuación de cualquier comando git. Por ejemplo: ```git branch -h``` y observa la documentación que te muestra. Además, si te equivocas al escribir un comando porque te dejas una letra o lo escribes sin los modificadores adecuados, git *entiende* que es lo que quieres hacer y te ofrece sugerencias.


* [GIT cheat sheet[PDF EN]](https://services.github.com/on-demand/downloads/github-git-cheat-sheet.pdf)

* [Taller de GIT PDF ES](https://ingenieriainformatica.uniovi.es/c/document_library/get_file?uuid=bbd3510e-4a10-4842-a29f-2d75f4bf9c12&groupId=780436)

* [Píldora de GIT UV PDF ES](https://www.uv.es/capgeminiuv/documents/P%C3%ADldora%20de%20Git.pdf)

* [Guía sencilla de GIT](http://rogerdudler.github.io/git-guide/index.es.html)

* [gitignore.io](https://www.gitignore.io)

* [GIT en eclipse](https://www.arquitecturajava.com/eclipse-git-repositorios/)

