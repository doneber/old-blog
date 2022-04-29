---
title: "Como crear tu blog con hugo y GitHub Pages"
date: 2022-04-28T09:47:22-04:00
draft: false
hidemeta: false
comments: false
description: "Crea tu blog en pocos minutos con estas herramientas"
canonicalURL: "https://canonical.url/to/page"
disableHLJS: true # to disable highlightjs
disableShare: false
disableHLJS: false
hideSummary: false
searchHidden: true
ShowReadingTime: true
ShowBreadCrumbs: true
ShowPostNavLinks: true
---

Hoy en día crear un blog no tiene para nada que ser complicado y podemos hacerlo en unos simples pasos.

Si no dominas herramientas como `git`, `GitHub` o `Hugo` no te preocupes, pero para este artículo necesito que tengas las nociones básicas y tener una cuenta de git y GitHub y ya lo demás te lo explicamos aquí.

### ¿Por que usar un generador de sitios estáticos como Hugo?

Para empezar crear un blog desde cero puede tomar bastante tiempo y considerando que este tipo de proyectos es tan repetitivo a menos que simplemente sea para practicar o que se trate de algo muy personalizado, no vale la pena reinventar la rueda. 

En mi caso me dio flojera hacer todo el proceso es algo largo.

A continuación haremos lo siguiente:

1. Instalar Hugo

    ¿Como instalar Hugo en windows con Chocolatey?
    
2. Crear un blog con Hugo
3. Elige una plantilla para tu blog
4. Crea tu primer blog
5. Corre tu blog en tu maquina local
6. Sube tu blog a internet con GitHub Pages

## 1. Instalar Hugo

Para empezar a usar Hugo debemos tenerlo instalado, esto funcionara como un programa a través de la linea de comandos (la terminal pues). Y para poder instalar Hugo podemos usar [brew](https://brew.sh/index_es) (mac) o [Chocolatey](https://chocolatey.org/install#individual) (windows) dependiendo del sistema operativo que uses.

### ¿Como instalar Hugo en windows con Chocolatey?

Debemos ir rápidamente al sitio de [Chocolatey](https://chocolatey.org/install#individual) y seguir los pasos para el plan individual que básicamente es correr un comando que muestran en su documentación en una terminal con acceso como administrador, una vez terminado esto ya tendremos el comando `choco` disponible.

Y puedes ejecutar en tu terminal:

```
choco install hugo
```

### 2. Crear un blog con Hugo

Esto puede es bastante sencillo ya que tenemos el comando `hugo` en la terminal, el nombre de nuestro proyecto se llamará “quickstart” y solo debemos ejecutar el siguiente comando:

```
hugo new site quickstart
```

Y se te creara una carpeta con el nombre de “quickstart”. Dentro tendras un folder llamado **themes** en donde dentro debes copiar un “template” o “plantilla”. 

## 3. Elije una plantilla para tu blog

Podemos elegir una plantilla en [themes.gohugo.io](https://themes.gohugo.io/). 

En mi caso elegí PaperMod. Para aplicar este tema tenemos diferentes opciones, pero el camino que elegí fue usar `git modules` con `git`

La estructura de carpetas se deberá ver algo así:

```
.(site root)
├── config.yml
├── content/
├── themes/hugo-PaperMod/
└── layouts/
```

Tambien algo que debes hacer es modificar el archivo `config.yml`, si solo tienes el `config.toml` puedes renombrarlo a `config.yml` y de ahí lo personalizas, puedes copiar la la configuración de ejemplo que nos brinda el autor en su [repositorio](https://github.com/adityatelange/hugo-PaperMod/wiki/Installation#sample-configyml). Esto variará un poco dependiendo de la plantilla que elegiste.

## 4. Crea tu primer blog

Ahora podemos crear un archivo .md dentro de la carpeta `content/posts/...` o podemos correr el siguiente comando en una terminal ubicada en la raiz principal del proyecto

```bash
hugo new posts/my-first-post.md
```

Y dentro de este archivo tendremos una cabecera en este formato:

```markdown
---
title: "Canva for Students"
date: 2022-04-29T14:42:32-04:00
draft: true
---

Here goes my awesome content
```

## 5. Corre tu blog en tu maquina local

Para poder ver como nuestra simplemente debemos ejecutar el comando:

```markdown
hugo server
```

Y ya tendremos nuestro blog corriendo posiblemente en [http://localhost:1313/](http://localhost:1313/)

## 6. Sube tu blog a internet con GitHub Pages

Todo muy bonito pero ahora queremos subirlo a internet. Hay varios servicios que nos pueden ayudar a hace esto y también podemos verlo en la [documentación de Hugo](https://gohugo.io/hosting-and-deployment).

Para usar [GitHub Pages con Hugo](https://gohugo.io/hosting-and-deployment/hosting-on-github/) hacemos lo siguiente:

1. Crea un proyecto en [GitHub](https://github.new)
2. Vincula tu repositorio con tu proyecto Blog
3. Agrega los siguientes archivos a la raíz de tu proyecto:
    - `.gitmodules` donde tendrá este formato pero debes remplazar el repositorio con el del template que elegiste:
        
        ```markdown
        [submodule "path_to_submodule"] 
            path = themes/PaperMod
            url = https://github.com/adityatelange/hugo-PaperMod.git
        ```
        
    - `.github/workflows/gh-pages.yml` donde contendrá exactamente este contenido:
        
        ```yaml
        name: github pages
        
        on:
          push:
            branches:
              - main  # Set a branch to deploy
          pull_request:
        
        jobs:
          deploy:
            runs-on: ubuntu-20.04
            steps:
              - uses: actions/checkout@v2
                with:
                  submodules: true  # Fetch Hugo themes (true OR recursive)
                  fetch-depth: 0    # Fetch all history for .GitInfo and .Lastmod
        
              - name: Setup Hugo
                uses: peaceiris/actions-hugo@v2
                with:
                  hugo-version: 'latest'
                  # extended: true
        
              - name: Build
                run: hugo --minify
        
              - name: Deploy
                uses: peaceiris/actions-gh-pages@v3
                if: github.ref == 'refs/heads/main'
                with:
                  github_token: ${{ secrets.GITHUB_TOKEN }}
                  publish_dir: ./public
        ```
        

Ten en cuenta que en tu configuración de github actions `https://github.com/<tu-usuario>/<tu-repo>/settings/actions` en la parte de *Worflow permissions* debes tener la opcion de lectura y escritura activada

---

Happy Day! 💛

Estaremos actualizando este post, incluso tal vez hagamos un video para explicarlo mejor. Considera compartirlo en las tus redes sociales y contactos: