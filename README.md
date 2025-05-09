# Curso-de-GitHub

## 🐈‍⬛ INTRODUCCIÓN 🐈‍⬛(Conceptos básicos)

### **Git y GitHub. ¿Son lo mismo?**

Cuando recién comenzamos a usar estas herramientas, es normal confundirse, pero *no*, no son lo mismo, sin embargo están fuertemente relacionados. 

|                | Git                  | GitHub               |
|----------------|----------------------|----------------------|
| Tipo           | Sistema de control de versiones | Plataforma de alojamiento en la nube, basado en Git |
| Instalación    | Trabajar de forma local (en nuestra PC) (SOFTWARE)   | Online, crear una cuenta y registrarse (SERVICIO) |
| Colaboración   | Repositorios locales | Repositorios remotos, ideal para trabajar en grupo |

### Control de versiones

Nos pasó un montón de veces: hacemos un proyecto, pero seguimos realizando más y más cambios, sin darnos cuenta terminamos con archivos como *trabajo1*, *trabajo1ver1*, *trabajo1FINAL*. Un control de versiones soluciona este problema, registra cada cambio que se realza en nuestro código, quién lo hizo y cuando. 

Entre sus ventajas están que es flexible, seguro, trabajas en equipo, sin riesgos y con mejor organización. 
---
# GIT
![Logo de Git](images/g.png) 

Una vez descargado este software (segun tu sistema operativo), podemos administrar una copia alojada de nuestro repositorio localmente en nuestra máquina. 

## Repositorio : 
Es una carpeta en la que almacenaremos todo lo que nuestro proyecto necesita, versiones de ficheros, imagenes, documentos; recuerda cada cambio que haces. Es un pilar fundamental tanto de Git como de GitHub.
![como un cofre](images/chest.png) 

 Git utiliza la terminal, desde ella puedes ejecutar comandos para interactuar con el sistema, pero antes debemos registrarnos: Configurar nuestro usuario y gmail que será con los que crearemos nuestra cuenta en GitHub. 

 ```bash
$ git config --global user.name "tu user, sé creativo"
$ git config --global user.email "tu correo personal" 

```
Si necesitas otra configuración para algun repositorio (asegurate de estar en su directorio) solo omite el *--global*

```bash
$ git config user.name "tu user"
$ git config  user.email "tu correo" 

```
### Algunos comandos de configuración extra 
```bash
$ git config --global core.editor "editor de texto de tu elección"  //cambiar vim que viene por default

$ git config --list  //muestra toda tu configuración
$ git config --global --list //muestra la configuración global
$ git config --local --list  //muestra configuración del repositorio local 
$ git config --system --list //muestra configuracion del git del sistema
```
---
## Iniciando un nuevo proyecto 🏁🏎️
Para crear un repositorio local tenemos algunos comandos 
```bash
$ git init nuevo-proyecto //usar guiones en lugar de espacios al indicar el nombre
$ cd nuevo-proyecto //change directory a nuestro proyecto

// o si ya tienes una carpeta existente
$ cd <directorio de tu carpeta del proyecto>
$ git init

```
Luego se creará una **rama** principal llamada *main* o *master* (definición más adelante)
---
# States & Commits 
## Los tres estados de Git
| Estado       | Descripción                                                                 | Comando clave          |
|--------------|-----------------------------------------------------------------------------|------------------------|
| **Modified** 🖊️  | Archivo modificado/creado/eliminado, pero *no preparado* para guardar.       | (Editas el archivo)    |
| **Staged**   📦  | Cambios marcados para el próximo *commit*, preparado para ser aceptado en el repositorio local                | `git add archivo.txt`  |
| **Committed** 💾 | Cambios guardados *permanentemente* en el historial del repositorio local.   | `git commit -m "mensaje"`  |

Explicandolo con ejemplos podemos decir que:
- **Modified** : como cuando haces cambios en cualquier documento
- **Staged**: como cuando seleccionas páginas antes de imprimir
- **Commited**: cuando ahora sí guardas los cambios en tu documento

  Para restaurar cambios se usan
  
```bash
  
$ git restore index.html //restora un archivo
$ git restore //restaura todo el directorio
$ git restore '*.js' //restaura todos los archivos terminados en .js

$ git reset index.html //deshacer del estado STAGED al MODIFIED
```

## ⭐COMMITS ⭐
Esta es l aparte importante, los commits son los que registran los cambios producidos en el repositorio. Como fotografías firmadas por el autor, con fecha, localización y más. También puede ser entendido como un *checkpoint* en los videojuegos ya que:
- Guarda el estado actual de tu proyecto (código, archivos, estructura).
- Te permite volver atrás si algo sale mal.
- Marca progreso en el desarrollo.

![Checkpoint](https://i.imgur.com/NGiUJ7S.png)

Cuando hagamos un commit, se guardarán todos los cambios que tenemos en staging. Para gacerlo tenemos el siguiente comando.

```bash
  
$ git commit //crea un commit en el repositorio y añade una referencia en la rama actual, se debe añadir un mensaje o añadirlo con
$ git commit -m "Add a feature" //este es el título 
$ $ git commit -m "Add a feature" -m "características o información extra

//todo se guarda en el repositorio local


```
### 📍 HEAD 📍 
Es un puntero que hace referencia a el lugar del historial de cambios en el que te encuentras ahora, solo puedes estar en un solo lugar.

![estás aquí](https://cdn-icons-png.flaticon.com/512/1559/1559160.png)
---
## 🌿 RAMAS  🌿
Una rama es una de las versiones de la colección de archivos y directorios del repositorio. Una instntánea de la división del estado del código. Permiten realizar un desarrollo *no lineal*. 

Es decir que cuando trabajas en grupo con un mismo código, cada uno trabajará dentro de una versión (evolución del código) en paralelo. 

Piensa en ellas como lineas de otros universos paralelos en el que se realizarán diferentes cambios, desde los más pequeños; estas se crea a partir de los commits y más adelante podrás fusionarlas para que tenga los cambios bien implementados. 

![multiversos](https://i.pinimg.com/736x/56/01/18/56011893ece6df292d8362c9978a8f5a.jpg)

### Comandos

```bash
  
$ git branch mi-primera-rama //creamos una rama mientras estamos en la rama main
//pero ahora queremos estar en nuestra nueva rama
$ git switch mi-primera-rama

//o puedes usar este comando y crear y cambiarte a la nueva rama al mismo tiempo
$ git switch -c mi-primera-rama //se nombra sin espacios como los repositorios

//no se podrán crear dos ramas con el mismo nombre

```
Para poder crear la rama necesitas crear al menos **un commit**.
Listar ramas:
- git branch
- git branch --show-current
- git branch --sort=-committerdate
---
###Fusionar ramas:
Nuestras ramas tendrán dos destinos: o son olvidadas o son fusionadas a nuestra rama principal.

```bash
  
$ git merge my-branch //la rama my-branch pasará a ser canon y crea un nuevo commit

$ git merge --edit //abre el editor primero

$ git merge --no-commit //no hará el commit automáticamente

```
### Eliminar Ramas 🌲🪚

Después de fusionarlas es normal querer eliminarlas, si se elimina una rama que no se fusionó nos saldrá un mensaje de errror.

```bash
  
$ git branch --delete mi-primera-rama

//para eliminar la rama sin importar que esté o no mergeada 
$ git branch -D mi-primera-rama

```
Ten cuidado de no eliminar las ramas que necesites, perderás horas de trabajo.

---
Eliminar ramas en repositorios locales: Hora de podar

$ git remote prune origin --dry-run

$ git remote prune origin

#### Merge Fast-Forward 
Ocurre cuando la rama de destino (ej. main) no tiene nuevos commits después de que creaste tu rama (ej. feature). Git simplemente mueve el puntero de main al último commit de feature, sin crear un commit de merge adicional. 
#### Merge No Fast-forward
Forza la creación de un nuevo commit de merge incluso si es posible un fast-forward. Esto sirve para mantener un historial explícito de que hubo una fusión, útil para rastreabilidad. Se usa con el flag --no-ff:

```bash
  
git checkout main
git merge feature  # Si es posible, hará fast-forward

//No fast forward
git merge --no-ff feature  # Siempre crea un commit de merge

```
### Conflictos


Ocurre cuando dos ramas modifican las mismas líneas en un archivo y Git no puede fusionarlas automáticamente.
git marcará las diferencias:
```bash
  <<<<<<< HEAD  
Código de la rama actual (ej. `main`)  
=======  
Código de la rama que intentas fusionar (ej. `changes`)  
>>>>>>> changes

```

#### ¿Cómo resolverlo? 

 Abre el archivo conflictivo y elige entre:
- Conservar los cambios de HEAD (tu rama actual).
- Conservar los cambios de la otra rama (changes).
- Combinar manualmente las partes útiles de ambos.

Elimina las marcas (<<<<<<<, =======, >>>>>>>) y guarda el archivo con el código final

---
# GITHUB 
![Logo de GitHub](https://i.pinimg.com/736x/dc/16/3b/dc163b42fb863411d390c6dfba7ebf73.jpg) 
