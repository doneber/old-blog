---
title: "Como empezar tu blog con hugo"
date: 2022-04-28T09:47:22-04:00
draft: false
hidemeta: false
comments: false
description: "Crea tu blog en pocos minutos con esta asombrosa herramienta"
canonicalURL: "https://canonical.url/to/page"
disableHLJS: true # to disable highlightjs
disableShare: false
disableHLJS: false
hideSummary: false
searchHidden: true
ShowReadingTime: true
ShowBreadCrumbs: true
ShowPostNavLinks: true
cover:
    image: "<image path/url>" # image path/url
    alt: "<alt text>" # alt text
    caption: "<text>" # display caption under cover
    relative: false # when using page bundles set this to true
    hidden: true # only hide on current single page
---

### ¿Por que usar un generador de sitios estaticos como Hugo?

Para empezar crear un blog desde cero puede tomar bastante tiempo y considerando que este tipo de proyectos es tan repetitivo que nisiquiera vale la pena crear uno por ti mismo, a menos que simplemente sea para practicar o que se trate de algo demasiado personalizado, pero basicamente es porque me da flojera hacer todo el proceso de crear el proyecto por mi cuenta.

### ¿Como instalar Hugo?

Para esto primero necesitamos instalar hugo, esto se debe hacer a travez de un instalador como puede ser [Chocolately](https://chocolatey.org/install#individual)

Y puedes ejecutar en tu terminal: 

```
choco install hugo
```

### ¿Como generar tu primer Blog?

Esto puede es bastante sencillo si ya puedes usar el comando `hugo` en tu terminal, solo debes de usar
```
hugo new site quickstart
```

Y se te creara una carpeta con el nombre de **quickstart**. Dentro tendras un folder llamado **themes**, dentro debes copiar un template, template que puedes elegir en [themes.gohugo.io](https://themes.gohugo.io/). En mi caso yo elegí PaperMod, por lo que mi estructura de carpetas se ve algo así:

```
.(site root)
├── config.yml
├── content/
├── themes/hugo-PaperMod/
└── layouts/
```

Ah si, tambien algo que debes hacer es modificar el archivo `config.yml`, si solo tienes el `config.toml` puedes renombrarlo a `config.yml` y de ahí lo personalizas, puedes copiar la la configuración de ejemplo que nos brinda el autor en su [repositorio](https://github.com/adityatelange/hugo-PaperMod/wiki/Installation#sample-configyml)

---
Happy Day! 💛

Estaremos actualizando este post, incluso tal vez hagamos un video para explicarlo mejor. Considera compartirlo en las tus redes sociales y contactos: