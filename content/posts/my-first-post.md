---
title: "Creación de un Blog Web"
date: 2021-05-10T14:22:24-05:00
draft: false
---

### [Nota para usuarios que no son de git:]()
- Si no tiene git instalado, puede descargar el archivo de la última versión de este tema desde: https://github.com/theNewDynamic/gohugo-theme-ananke/archive/master.zip
- Extraiga ese archivo .zip para obtener un directorio **"gohugo-theme-ananke-master".**
- Cambie el nombre de ese directorio a "ananke" y muévalo al directorio **"themes /".**

```html
▶ cd quickstart
~/quickstart
▶ git init
Initialized empty Git repository in /Users/bep/quickstart/.git/.
```
# Instalación de hugo.io

Para poder crear tu sitio web o en este caso un blog te recomiendo usar hugo.io que seria lo que yo use para crear lo mío y para crear tu blog sería lo siguiente (recomendación tener instalado git en tu equipo):

### 1. Instalar hugo.io
Homebrewy MacPorts, los administradores de paquetes para macOS, se pueden instalar desde [brew.sh]() o [macports.org]() respectivamente. Consulte la [instalación]() si está ejecutando Windows, etc.

para la instalación pondremos los siguientes comandos ya sea en cmd o en powershell

- [***brew install hugo***]()

- [***port install hugo***]()

- [***choco install hugo***]()

En mi caso yo instale hugo con [choco install hugo](), para saber que la  instalación se hizo con éxito ponemos [hugo version]()

### 2. Crear un sitio nuevo
Lo crearemos con el siguiente comando hugo new site quickstart (Lo anterior creará un nuevo sitio de Hugo en una carpeta llamada quickstart)

nos tendría que salir esto para saber que si se creo

![](/img1.jfif)

### 3. Agregar un tema 
Para elegir un tema a nuestro gusto podríamos buscar en [**themes.gohugo.io**]() (para obtener una lista de temas a considerar. Esta guía de inicio rápido utiliza el hermoso [tema de Ananke]())
antes de agregar el tema nos vamos a nuestro cmd o powershell y tenemos que estar cd de donde esta nuestra pagina que se creo para poder poner el tema por ejemplo yo utilice lo siguiente:

![](/ima2.png)

Aquí yo me estoy colocando donde tengo o mas bien donde cree mi [quickstart]()
ya que eligimos nuestro tema le damos click y nos saldrá esto.

![](/ima3.png)

Le damos en descargar y nos va a mandar a Git Hub, ya solo le damos en code  en mi caso soy Windows y elijo HTTPS y copiamos la URL

![](/ima4.png)

### Ponemos los siguientes comandos:

```html
cd quickstart (si no estas en tu ruta ).
git init (se encarga de iniciar un repositorio).
git submodule addgit submodule add https://github.com/theNewDynamic/gohugo-theme-ananke.git themes/ananke 
(aquí agregamos nuestra ruta copiada en mi caso use la que esta ahí).
y adrarle enter nos empezara a crear todo y a insertar nuestro tema en nuestro quickStart.
```
### IMPORTATENTE
themes/ananke ( Estar al pendiente con esto ya que ananke cambia por si elejimos un tema que nos guste por ejemplo el mio cambia)
#### ejemplo: 
Git submodule add  https://github.com/vaga/hugo-theme-m10c.git themes/m10c (este es el que cambia ya que si no lo ponemos nos aparecerá en blanco nuestro blog y es en la siguiente imagen donde se cambiara el theme si lo tenemos con [theme="anaka"](), cambiarlo al m10c que sería nuestro tema que queremos en nuestro blog web)

 **Antes:** 
 
 ![](/img.jpg)  
 
 **Despues:** 
 
 ![](/ima5.png)

Ya cambiándolo nos saldría nuestro blog Web con el diseño que le demos.

![](/ima6.png)

Luego, agregue el tema a la configuración del sitio:
[echo theme = \"ananke\" >> config.toml]()


### 4.  Agregar contenido

Puede crear manualmente archivos por ejemplo dentro del directorio [content/post]() y proporcionar metadatos en ellos, sin embargo, pueden usar el **new comando** para hacer algunas cosas por usted **(como agregar título y fecha)**

Ponemos el siguiente código:
[hugo new posts/my-first-post.md]()

Si queremos editar el archivo recién creado (si lo desea), comenzara con algo así:
```html
title: "My First Post"
date: 2019-03-26T08:47:11+01:00
draft: true
```
**(En otro caso para hacer mas fácil la edición podemos abrir nuestro directorio con visual code (que es el que yo uso) ya solo seria buscar nuestro new-first-post (En mi caso lo encontré en content))** 

![](/ima7.png)

**Los borradores no se despliegan; una vez que termine una publicación, actualice el encabezado de la publicación para decir draft: false. [Más info aquí](https://gohugo.io/getting-started/usage/#draft-future-and-expired-content)**
### 5. Vamos a iniciar el servidor Hugo.io
#### Dato:
Si tenemos el parametro [draft]() como true, no nos dejara publicar los post así que es mejor tener los con false [Como saber si nuestro post es un borrador por el draft: false ]() recuerda debe de ser falso si quieres publicar tu post

Ahora, inicie el servidor Hugo con los borradores habilitados:
usamos el comando [hugo serve -D]() (nos ayudara a correr el servidor) 
![](/ima8.png)

Solo le damos a **ctrol + c** para deje de correr el servidor (**solo en el caso si lo queremos parar**) [Navegue a su nuevo sitio en: http: // localhost: 1313 /.]()
Siéntase libre de editar o agregar contenido nuevo y simplemente actualice en el navegador para ver los cambios rápidamente (**es posible que deba forzar la actualización en el navegador web, algo como Ctrl-R generalmente funciona**).

### 6. Personalizar el tema
Su nuevo sitio ya se ve muy bien, pero querrá modificarlo un poco antes de lanzarlo al público.
**vamos a configurar el sitio**
Para poder abrirlo en un editor de texto haces lo siguiente 
primero te vas cmd o al PowerShell, y te vas a tu directorio donde tengas tu pagina y solo le damos [codigo .]() por ejemplo:

![](/ima9.png)

Ahora si vamos a configurar el sitio

### Configuración del sitio
Abre [config.tomlen]() (puedes abrirlo con visual) un editor de texto y ponemos lo siguiente:
```html
baseURL = "https://example.org/"
languageCode = "en-us"
title = "My New Hugo Site"(aqui pueden cambiar el tittulo a su gusto)
theme = "ananke" (aqui es donde les digo que si quieren un tema personalizado cambiarle ananke por el que les de el tema que quieren)
```
Reemplaza el title anterior con algo más personal. Además, si ya tiene un dominio listo, configure el baseURL. Tenga en cuenta que este valor no es necesario cuando se ejecuta el servidor de desarrollo local.

#### Sugerencia:
Realice los cambios en la configuración del sitio o en cualquier otro archivo en su sitio mientras el servidor Hugo se está ejecutando, y verá los cambios en el navegador de inmediato, aunque es posible que deba [borrar su caché](https://kb.iu.edu/d/ahic).

Para mas opciones de configuración especificar del tema. consulte el 
[sitio del tema.](https://github.com/theNewDynamic/gohugo-theme-ananke) 
Para una mayor personalización del tema, consulte [Personalizar un tema.](https://gohugo.io/hugo-modules/theme-components/)
### 7. Crea Paginas Estáticas  
Es simple solo en tu ruta de tu directorio ponemos 
[hugo -D]()
La salida estará en el./public/directorio por defecto **(-d/--destinationbandera para cambiarla, o configuradapublishdiren el archivo de configuración).**
### 8. En cada tema hay una configuración en la cual te puedes ir basando para poder darle diseño a tu blog web por ejemplo este:
![](/ima10.png)

En este caso usamos este para cambiar los colores del tema.

**Nota: Recuerda que todo tipo configuracion que le quieras agregar va en config.toml**

### Markdown:
Aquí encontraras algo básico de como escribir en [Markdown Guide](https://www.markdownguide.org/basic-syntax/) que es lo que estaría echo nuestro Blog Web, y tambien como usar [html con Markdown](https://www.freecodecamp.org/news/how-to-format-code-in-markdown/#:~:text=There%20are%20two%20ways%20to,will%20apply%20syntax%20highlighting%20to.)

#### Bueno esto seria todo espero haberte ayudado, si funciono hazme lo saber con una follow  en [Mi Git Hub](https://github.com/Jovany-Vergara)