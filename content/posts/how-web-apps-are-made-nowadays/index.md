---
title: "How Web Apps Are Made Nowadays"
date: 2022-07-28T23:40:48-04:00
draft: true
---

## Páginas web estáticas y dinámicas

Antes de comenzar necesitamos saber la diferencia entre las páginas web estáticas y dinámicas.

### Páginas web estáticas

Aquí nos referimos sobre todo a los sitios web que tienen el principal objetivos informativos, como puede ser una página web personal, un sitio de presentación de alguna entidad gubernamental (misión, vision, etc.) y de algunos sitios web de museos o lugares turísticos; es decir que prácticamente no cambiarán con el tiempo.

### Páginas web dinámicas

Aquí empezamos a hablar sitios donde el contenido varíen frecuentemente. De esto podemos mencionar por ejemplo un portal de noticias

## Como empezamos a hacer nuestras páginas web

Cuando empezamos a estudiar desarrollo web lo primero que nos aprendemos es a crear un archivo `index.html` y quizas un poco de CSS y Javascript. Y tambien en nuestra misma carpeta podemos tener otros archivos como un apartado de `nosotros.html` o uno de `contactos.html` 

## Como se crean las páginas web hoy en día

La forma de desarrollar páginas y aplicaciones web han cambiando bastante en los últimos años. Cada día salen nuevas herramientas para desarrollar mejores y mas rápidas aplicaciones. Tenemos frameworks como Vuejs, Angular o React entre las mas populares. Sin embargo también tenemos otras herramientas como Hugo, Gatsby o Nuxt/Next entre otras, claro, cada una con objetivos diferentes pero todas nos ayudan a hacer nuestro trabajo de una forma más fácil

Sin embargo de lo que hoy vamos a hablar son de la forma en que las páginas web se renderizan en nuestro navegador

## Tipos de renderizado

Entre las mas importantes podemos destacar 3:

- Client-Side Rendering (CSR)
- Server-Side Rendering (SSR)
- Static Site Generator (SSG)

### Client Side Rendeing

O CSR por sus siglas, básicamente en nuestro proyecto/aplicación web es que el resuntado final de nuestro proyecto es un archivo index.html un varios de javascript y nuestro index se ve así:

```html
<body>
	<div id="app">
	<!--la app va aquí :D -->
	</div>
</body>
```

Así que la construccion del DOM de nuestro proyecto esta echa por el javascritp, esto reduce el CEO, pero para aplicaciones web esta genial

### Server-Side Rendering

Renderizado por el lado del servidor básicamente el trabajo que se hacia el CSR pero el trabajo lo hará el servidor

### Static Site Generator

Esta forma de hacer webs nos genera archivos .html, y se puede decir que ya no hace nada de lo que hace Client Side Rendering.

## Source:

[Tipos de Renderizado - CSR & SSR & SSG & ISR - con Next.js](https://www.stewartgf.com/blog/tipos-de-renderizado-en-2021-con-next-js)

[Client-side vs. Server-side vs. Pre-rendering for Web Apps](https://www.toptal.com/front-end/client-side-vs-server-side-pre-rendering)