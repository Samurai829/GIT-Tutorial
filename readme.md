# Tutorial de Git

Aqui aprenderas como usar GIT de forma sencilla..

GIT funciona en conjunto con GitHub y GitLab los cuales serian entornos de pruebas 
descentralizado, el cual se encargara de controlar las versiones de codigo ademas de 
verificar nuestro codigo e indicarnos si hay algun error dentro del mismo, si los 
cambios no causan errores lanza el Deploy y los aplica.

## Los Estados de Git.

Git tiene 3 estados los cuales son:

**Working dir / Workdir - Area de Trabajo**:
Conocido como el area de trabajo, el cual es el entorno local, donde
podemos cambiar, **eliminar** o **modificar** un codigo o crear un nuevo 
codigo.

**Staging / Stage - Escenario de Confirmacion**:
Conocido como area de preparacion, aqui van los archivos que serian parte
de su proxima confirmacion, estos son los cambios que se aplicaran en el 
**REPOSITORIO**. Asi Git sabe que cambiara entre la confirmacion 
actual y la siguiente.

**Repository - Repositorio**:
Aqui es donde tienes todas las confirmaciones, donde Git tiene los archivos
que realmente conoce. Y la confirmacion es una instantanea de como se ve su 
area de trabajo y preparacion en el momento de la confirmacion.

La comunicacion entre estos 3 estados es crucial ya que como indicamos en 
el area de trabajo se procede a llevar al area de preparacion donde luego 
realizamos un comando llamado `commit` para subir al deposito o repositorio.

## Git en el uso diario.

Para iniciar el area de trabajo utiliza

1- `git init` - Se usa para indicar que en el directorio donde nos localizamos 
se subira o se creara un **REPOSITORIO**.

Luego de esto **GIT** creara en la carpeta del codigo una carpeta llamada 
`.git` en esta carpeta va ha**Recopilar** toda la informacion de su repositorio 
o los cambios que se han realizado anteriormente, ademas de tener un control 
indicando cual es el error pero esto seria mas adelante que lo veremos. 

Vamos a probar subiendo este archivo ignorando el archivo **TEXT** llamado 
secret, para hacerlo seria con:

2- `.gitignore`: Para hacer esto seria de la siguiente manera creamos un 
archivo llamado `.gitignore` y dentro del archivo indicamos cuales son los 
archivos o carpetas que no queremos subir o que **Git** va ha ignorar.

**Ejemplo:**
Mira el archivo `secret.txt` y la carpeta ha ignorar que ya creamos que 
luego introducimos en `.gitignore` para que git no los agregue al 
repositorio.

Aqui luego veras que no solo queda en esto tambien puedes indicarle que 
ignore cualquier archivo `.txt` o cualquier otro archivo al igual que los 
directorios que le indiquemos el nombre, mira el archivo `.gitignore` y 
veras que tambien va ha ignorar el archivo `main.tf` que indicamos en 
`.gitignore` ya con esto concluimos esta parte.


3- `git status`: Con este comando podemos ver el estado de nuestos archivos, 
nos indica si estan en el **"Branch master o Rama Maestra"**, ademas nos indica 
si no estan en el **Stages area**.

4- `git add`: Con este comando indicamos que queremos **AGREGAR** en el area de
preparacion, para agregar todo podemos usar `-A` para indicarle que agregue 
todos los archivos que no se encuentran en el area de preparacion o solo 
indicando el nombre del archivo que deseas subir.

5- `git rm`: Con este hacemos lo contrario **ELIMINAMOS** un archivo que no 
deseamos agregar en el area de trabajo, para esto seria de la siguiente 
manera:

`git rm --cached .gitignore` --> Indicandole que no queremos que agregue 
el archivo `.gitignore` al repositorio.


6- `git commit`: Podemos con este comando agregar **COMENTARIOS** a nuestros 
archivos antes de subirlos en nuestro repositorio o deposito. Para utilizarlo 
seria asi:

`git commit -m "Actualizacion de codigo"` --> De esta manera crea el **COMMIT** 
para indicar porque agregamos o modificamos este archivo del repositorio.

Luego de que hagamos esto confirmamos de subir los cambios, entonces si hacemos 
`git status` no veras los archivos ya que **Git** entiende que los archivos que 
fueron confirmados estan bien y no van aparecer a menos que hagas otro cambio 
adicional.

7- `git log`: Este comando podemos ver un historial de registros de todos los 
**COMMIT** realizados en este repositorio, indicando el autor y la fecha.

8- `git clone`: Se usa para clonar un repositorio y usarlo en el area local, de 
esta manera **DESCARGAMOS Y USAMOS** un repositorio externo que alguien ya creo o 
que teniamos en nuestra pagina de **GitHub**, todo esto se utiliza con el fin 
para crear algo con ese codigo ya existente o modicar el mismo.

Para usarlo seria de la siguiente manera:

`git clone https://github.com/Samurai829/GIT-TUTORIAL.git` --> indicando la url 
del repositorio. 


9- `git diff`: Este comando muestra las diferencias y cambios que tiene los 
archivos que tienes en el repositorio y los que tienes de manera local.

Este ultimo comando es muy interesante ya que de esta manera si compartes un 
repositorio o estas trabajando con alguien para la creacion de un nuevo codigo 
ambos pueden ver los cambios realizados anteriormente.

10- `git push`: Este comando se utiliza para subir nuestro codigo o archivos 
que esten creados y agregados para confirmacion.

11- `git pull`: Con este comando podemos descargar cualquier archivo o codigo 
con la ultima actualizacion o el original sin cambios, si queremos descargar el 
archivo o codigo original sin los cambios realizados podemos hacer de la 
siguiente manera:

`git pull origin master` --> Asi descargamos el codigo o archivo origen

## Ramas de Git o Branch.

### Que es un Branch?

Un Branch es una rama se podria decir de la siguiente manera: En un arbol de 
creacion de apps o codigos podemos crear una rama donde realizamos nuestros 
cambios y luego la agregamos a la **RAMA PRINCIPAL**, esto en cierto punto es 
arriesgado ya que en un departamento o un equipo de implementacion y desarrollo 
podria haber choques donde tu creas una rama y otro crea una distinta y podrian 
tener los mismos cambios. Esto tambien se podria usar de la siguiente manera que 
cada uno implemente una rama de una app determinando la tarea que realizara cada 
uno y luego de tener todos los cambios y codigos testeados se aplican a la 
**RAMA PRINCIPAL** o **BRANCH MASTER**.

Para crear una Rama o Branch seria de la siguiente manera:

`git branch prueba1` --> Este branch se uilizaria de manera local en tu PC para 
cuando vayas a subir algun cambio en el repositorio.

Ahora para utilizar esta Rama seria de la siguiente manera:

`git checkout prueba1` --> Asi cambiamos de branch, ademas podemos ver cuales son 
las creadas con el comando `git branch` y asi muestra todas las ramas 
creadas aparte de la rama master.

Hay una manera de subir un archivo indicando que subiremos al repositorio con una
branch distinta seria de esta manera:

`git push -u origin prueba1` --> Asi indicamos al repositorio y servidor que subimos 
unos cambios o archivos con una Branch distinta. 

Ahora para confirmar luego de subir se puede usar:

`git log` --> Nos mostrara los registros y desde que branch subimos el archivo

Ahora tambien podemos ver todas las Branch locales o remotas (las que se han usado
y estan registradas en el repositorio) para eso seria:

`git branch -a` 

Ahora para subir todos los cambios hechos en la **Rama Master** luego de crear todo 
en una rama distinta como por ejemplo prueba1, se haria de la siguiente manera:

Primero **Merged - Combinamos** la Rama Master que es la rama donde queremos aplicar
los cambios creados.

`git branch --merged master`

Segundo hacemos uso de merged para el branch que creamos que seria **prueba1** de la
siguiente manera:

`git merge prueba1`

Ahora solo seria subir los cambios en el **Branch Master** para que otro tenga la 
version final o ultima version con los cambios aplicados. Para hacer esto seria asi:

`git push origin master`

Ahora como ya subimos todo a la **Rama Principal** seria borrar la rama creada ya 
que como no se haran mas cambios o no la vas a volver a utilizar  lo ideal seria 
borrarla ya que esto seria una buena practica.

Para hacerlo seria de esta manera:

`git push origin --delete prueba1`

Asi como viste seria la manera para borrar la Branch usada de manera remota osea la 
que usamos y que Github tiene los datos.

Ahora para eliminarla de manera local seria asi:

`git branch -d prueba1`

Esto se podria hacer si ya no deseas utilizarla

Por ultimo seria ya poner en practica todo lo explicado, paso por paso.
