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
