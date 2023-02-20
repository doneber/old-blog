---
title: "Despliega tu Aplicación Monorepo (backend y frontend) con Vercel"
date: 2023-02-20T18:09:49-04:00
---

Si estás empezando un proyecto que utiliza tecnologías tanto para el backend como para el frontend, y quieres publicarlo en internet, hay varias opciones disponibles. Puedes comprar un servidor y configurarlo, utilizar herramientas como Docker para empaquetar el proyecto, o utilizar una plataforma como Vercel para simplificar el proceso. Vercel es especialmente útil para aquellos que no tienen experiencia en infraestructura o que no quieren pasar mucho tiempo configurando todo.

## Vercel

Si eres un desarrollador de aplicaciones modernas, Vercel es una plataforma que definitivamente debes considerar. Además de ser rápido y fácil de usar, Vercel te proporciona una amplia gama de herramientas y recursos para facilitar el despliegue de tus aplicaciones. Con Vercel, puedes estar seguro de que tu aplicación será desplegada de manera eficiente y sin problemas para que puedas enfocarte en crear la mejor experiencia para tus usuarios.

Desplegar una aplicación estática construida con vanilla o algún framework como Vue o React, así como desplegar la API de nuestro backend no es muy complicado. Los servicios de Vercel permiten desplegar tanto la aplicación frontend como la API del backend. Sin embargo, ¿se pueden desplegar ambos al mismo tiempo?

### ¿Que es un monorepositorio?

En el desarrollo de software que consiste en tener en un solo repositorio tanto el proyecto de Frontend como el de Backend. Esto significa que ambos proyectos se pueden gestionar y desplegar juntos. Es una opción conveniente para proyectos complejos que involucran múltiples componentes y dependencias.

Por fines prácticos tomaremos como monorepo un proyecto que tiene la carpeta del Frontend (Vue, React, etc.) y el de Backend (NodeJs, Flask, etc.), todo junto.

Para el ejemplo nuestro proyecto `awesome-project` tiene tanto el backend (`api`) como el frontend.

```markdown
/api-and-frontend-project
  api/*
  frontend/*
	package.json
  Readme.md
```

Puedes ver un ejemplo real en mi repositorio de GitHub siguiente este [enlace](https://github.com/doneber/yt-summarizer).

## Desplegando nuestro proyecto monorepo

Para desplegar el frontend y la API en Vercel, sigue estos pasos:

1. Ingresa a Vercel y crea una cuenta o inicia sesión si ya tienes una.
2. Importa tu monorepo a Vercel.
3. Configuración de Vercel.
    
    Para este tercer paso, en nuestro proyecto creado en Vercel, en la sección de Configuraciones, debemos seleccionar la opción raíz como `/` (por defecto, puede que se seleccione `/frontend`) y cambiar el directorio para la publicación a `frontend/dist`. Es importante tener en cuenta que la carpeta para nuestro backend debe llamarse obligatoriamente `api/`. También es necesario crear un archivo en la raíz llamado `vercel.json`.
    
    ```markdown
    /awesome-project
      api/*
      frontend/*
    	package.json
      Readme.md
    	vercel.json
    ```
    
    Y configuramos el archivo `vercel.json` de las siguiente manera:
    
    ```json
    {
      "functions": {
        "api/app.js": {
          "memory": 1024,
          "maxDuration": 10
        }
      },
      "routes": [
        {
          "src": "/",
          "dest": "frontend/dist"
        },
        {
          "src": "/.*",
          "dest": "api/app.js"
        }
      ]
    }
    ```
    
4. Finalmente hacemos un push a nuestro repositorio.

Ahora queda esperar que Vercel empiece a construir y publicar la aplicación.

Algo interesante que podríamos tomar en cuenta a futuro es  usar herramientas tipo [Turbo](https://turbo.build/) y pero sobre todo [Turborepo](https://turbo.build/repo)

Y listo, espero te haya ayudado, recuerda también leer la documentación oficial en [vercel.com](http://vercel.com) en caso de cualquier actualización.
