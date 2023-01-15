---
title: "Personaliza tu perfil de GitHub y aprovecha GH Actions"
date: 2023-01-14T20:45:17-04:00
showtoc: true
tocopen: true
---

Si tienes un perfil en GitHub seguro que querrás configurarlo para que pueda mostrar toda tu información de una forma sencilla pero completa, no busques más que has llegado al lugar correcto porque te voy a contar como lo hice y además de todas las referencias y fuentes que usé para lograrlo. Vamos a ello

## Resumen

Para configurar nuestro perfil en GitHub basta con un repositorio con tu nombre de usuario, luego dentro de un archivo `README.md` puedes poner toda tu información en markdown, sobre ti, tus redes sociales y tus seguidores, tu contenido como; publicaciones de tu blog, videos, etc. Pero lo mas interesante y loco es que también puedes hacer que la información sea dinámica, como actualizar las publicaciones que hiciste de forma completamente automática!

## Contexto

Si se han fijado hay muchos perfiles de GitHub que tienen cosas bastante interesantes, por ejemplo [github.com/midudev](http://github.com/midudev), además de ser desarrollador hace contenido en internet y bueno, me preguntaba como lo hace. También hay otros perfiles, pero digamos que ese fue el que me motivo a personalizar mi perfil.

Por si acaso te dejo como quedo mi [perfil de github](https://github.com/doneber)

Claro que hay otras configuraciones que puedes hacer en el perfil, pero en esta ocación nos vamos a concentrar en lo que podemos hacer en un archivo tipo markdown de nuestro perfil

## Personalización básica

### Crear un repositorio “especial”

Así es, debemos crear un repositorio que se llame igual a nuestro nombre de usuario en GitHub, para esto podemos ir a [repo.new](http://repo.new) y crear nuestro repositorio público. Dentro de este debes tener al menos un archivo `README.md`, y su contenido será de tipo [markdown](https://markdown.es/) y todo lo que pongas ahí se mostrará en tu perfil de GitHub

Nota: Por si te preguntas ¿como edito y/o previsualizo como va quedando mi archivo? puedes editar y visualizar los cambios en el mismo editor de github.

### Información básica

En esta parte empieza a llenar de contenido tu archivo `README.md`. Puedes hacer volar tu imaginación y poner toda la información que quieras, tus redes sociales, que te gusta, que te disgusta, tus metas, tus mascotas, absolutamente todo (en formato Markdown). Pero si no la tienes puedes inspirarte de [este sitio](https://zzetao.github.io/awesome-github-profile/) o usar este [generador online](https://rahuldkjain.github.io/gh-profile-readme-generator/). muy clara puedes usar algunos generadores de plantillas

En mi caso lo puse sencillo:

```markdown
### Hey!👋
**Sobre mí:**
- Hago como que le sé a la Programación 🤓 
- Se puede decir que soy "creador de contenido" 😅
```

### Redes sociales e íconos

Hay algo que se llama “badge” (creo) que al final resultan ser una imagen que puede mostrar diferentes cosas, como tus redes sociales, repositorios o videos en concreto, entre otros. Estos puedes encontrarlos en [shields.io](http://shields.io), donde podrás encontrar diferentes categorias, yo usé su apartado de [/social](https://shields.io/category/social).

```markdown
[![YouTube channel](https://img.shields.io/youtube/channel/subscribers/UCKMWXwHYoy920OFEN_BM5VQ?style=social)](https://www.youtube.com/@doneberdev)
 . [![TikTok account](https://img.shields.io/endpoint?logo=TikTok&style=social&url=https%3A%2F%2Fdoneber.dev%2Ftiktok-counter%2F)](https://www.tiktok.com/@doneberdev)
 . [![Twitter account](https://img.shields.io/twitter/follow/doneberdev?label=Followers&style=social)](https://twitter.com/doneberdev)
```

[![YouTube channel](https://img.shields.io/youtube/channel/subscribers/UCKMWXwHYoy920OFEN_BM5VQ?style=social)](https://www.youtube.com/@doneberdev)
 . [![TikTok account](https://img.shields.io/endpoint?logo=TikTok&style=social&url=https%3A%2F%2Fdoneber.dev%2Ftiktok-counter%2F)](https://www.tiktok.com/@doneberdev)
 . [![Twitter account](https://img.shields.io/twitter/follow/doneberdev?label=Followers&style=social)](https://twitter.com/doneberdev)

Seguro también querrás añadir iconos de las herramientas y/o lenguajes que domines, para esto puedes usar el buscador de GitHub e inspeccionar la imágen de la tecnología en cuestion. Por ejemplo si buscas JavaScript en el buscador de GitHub encontrarás un repositorio especial, solo dale click derecho y copiar URL de la imagen.

```html
<img align="left" alt="HTML5" width="26px" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/html5/html5-original.svg" style="padding-right:10px;" />
<img align="left" alt="CSS3" width="26px" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/css3/css3-original.svg" style="padding-right:10px;" />
<img align="left" alt="JavaScript" width="26px" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg" style="padding-right:10px;" />
```

<img align="left" alt="HTML5" width="26px" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/html5/html5-original.svg" style="padding-right:10px;" />
<img align="left" alt="CSS3" width="26px" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/css3/css3-original.svg" style="padding-right:10px;" />
<img align="left" alt="JavaScript" width="26px" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg" style="padding-right:10px;" />
<img align="left" alt="Typescript" width="26px" src="https://raw.githubusercontent.com/github/explore/80688e429a7d4ef2fca1e82350fe8e3517d3494d/topics/typescript/typescript.png" style="padding-right:10px;" />
<img align="left" alt="Node.js" width="26px" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/nodejs/nodejs-original.svg" style="padding-right:10px;" />
<img align="left" alt="Vue" width="26px" src="https://raw.githubusercontent.com/github/explore/80688e429a7d4ef2fca1e82350fe8e3517d3494d/topics/vue/vue.png" style="padding-right:10px;" />
<img align="left" alt="Git" width="26px" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/git/git-original.svg" style="padding-right:10px;" />
<img align="left" alt="Terminal" width="26px" src="https://raw.githubusercontent.com/github/explore/d92924b1d925bb134e308bd29c9de6c302ed3beb/topics/terminal/terminal.png" style="padding-right:10px;" />
<img align="left" alt="Visual Studio Code" width="26px" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/vscode/vscode-original.svg" style="padding-right:10px;" />

</br>
</br>


Excelente!

## Personalización avanzada

En este punto haremos que nuestro perfil se actualice automáticamente con la ayuda de **GitHub Actions**, aquí debe ir información que va cambiando con el tiempo, como publicaciones recientes

Para esta sección aprovecharemos lo que es la **Marketplace** de GitHub donde podremos usar diferentes **Workflows** que se encargarán de hacer todo esto automaticamente.

Nota: Quizás si estas empezando con esto, no hay de que preocuparse, estamos casi igual. Así que solo sigue los pasos y trata de abstraer todo lo que puedas. También puedes profundizar en los temas que te confundan, hay mucho contenido en internet 🙂

### Actualizar últimos posts automáticamente (con Actions)

El punto es que yo últimamente estoy escribiendo artículos en mi blog (si si, este blog) así que quiero que se muestre en mi perfil. Para esto debo buscar algún flujo de trabajo automático (workflow) que haga esto. Para esto seguiremos los siguientes pasos:

- Ir a la marketplace de GitHub en [este enlace](https://github.com/marketplace).
- Buscar el actions que dice **[Blog Post Workflow](https://github.com/marketplace/actions/blog-post-workflow)**
- Y una vez ahí debemos seguir las instrucciones que dicen en  [el enlace](https://github.com/marketplace/actions/blog-post-workflow)
    - Esto básicamente es crear un archivo `.github/workflows/blog-post-workflow.yml`
    - Hacer unos comentarios en nuestro archivo `README.md` del estilo:
    
    ```markdown
    <!-- BLOG-POST-LIST:START -->
    <!-- BLOG-POST-LIST:END -->
    ```
    
    - Y hacer correr los actions

### Actualizar videos de YouTube

Muy parecido al anterior pero aquí podemos elegir como queremos que se vea nuestro video, bueno para eso en el marketplace podemos buscar YouTube y ver que opciones hay ya quie ví un par de opciones más, y lo que yo hice fue algo así:

- Ir a la marketplace de GitHub en [este enlace](https://github.com/marketplace).
- Buscar el actions que dice **[GitHub Readme YouTube Cards](https://github.com/marketplace/actions/github-readme-youtube-cards)**
- Seguir sus instrucciones

Y listo, espero te funcione de maravilla!

Nota: Usar los actions de la marketplace de GitHub es muy útil, pero aún puedes personalizarlo mas creando tus propios workflows, para esto puedes también crear algún script con NodeJs, Python o el lenguaje que tu quieras, pero considero que este es un buen punto de inicio si estas empezando.


## Fuentes y recursos:
Aquí algunos recursos que me ayudaron a personalizar mi perfil

- [https://www.youtube.com/watch?v=ECuqb5Tv9qI](https://www.youtube.com/watch?v=ECuqb5Tv9qI) | Video en inglés pero me ayudo mucho
- [https://www.youtube.com/watch?v=n6d4KHSKqGk](https://www.youtube.com/watch?v=n6d4KHSKqGk) | Otro video También en inglés pero interensante
- [https://midu.dev/como-crear-tu-perfil-de-github-con-readme/](https://midu.dev/como-crear-tu-perfil-de-github-con-readme/) | Sorprendentemente midu hizo un post e incluso tiene video
